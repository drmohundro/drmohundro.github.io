# cp ../mohundro.com/blog/articles/* _posts
# for file in *.md; do mv "$file" "${file/.md/.markdown}"; done

desc 'Convert old binary links over to s3 binary links'
task :convert_posts do
  Dir['_posts/*.markdown'].each do |f|
    contents = File.read f

    front_matter, post = parse_post(contents)

    File.open(f, 'w') do |out|
      out << front_matter
      out << post
    end
  end
end

def parse_post(contents)
  front_matter = "---\nlayout: post\n"
  front_matter_parsed = false
  first_line_parsed = false

  post = ''

  contents.each_line do |line|
    if !first_line_parsed
      first_line_parsed = true
      next
    end

    case line
    when /^title:\s+"?(.+?)"?$/
      front_matter << "title: \"#{$1.strip}\"\n"
    when /^date:\s+(.+?)$/
      front_matter << "date: #{$1.strip}\n"
    end

    if !front_matter_parsed && line.chomp == ''
      front_matter_parsed = true
    end

    if front_matter_parsed
      case line
      when /^```(.+)$/
        post << "{% highlight #{map_parsers($1)} %}\n"
      when /^```$/
        post << "{% endhighlight %}\n"
      else
        post << line.gsub("\t", "  ")
      end
    end
  end

  front_matter << "category: blog\n---\n"

  [front_matter, post]
end

def map_parsers(in_syntax)
  map = {
    cs: 'csharp',
    dos: 'batch',
    'no-highlight': 'text'
  }

  mapped = map[in_syntax.to_sym]
  mapped == nil ? in_syntax : mapped
end
