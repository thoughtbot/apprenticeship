INPUT_DIRECTORY_NAME = 'markdown'
INPUT_FILE_EXTENSION = 'md'
OUTPUT_DIRECTORY_NAME = 'pdf'
OUTPUT_FILE_EXTENSION = 'pdf'

PANDOC_FLAGS = [
  '--latex-engine xelatex',
  '--template ./templates/pdf-template.tex',
  '--listings'
].join(' ')

PANDOC = ['pandoc', PANDOC_FLAGS].join(' ')

directory OUTPUT_DIRECTORY_NAME

desc "Regenerate the PDF."
task :regenerate => [:clean, OUTPUT_DIRECTORY_NAME] do
  input_files = Dir.glob("#{INPUT_DIRECTORY_NAME}/*.#{INPUT_FILE_EXTENSION}")

  input_files.each do |input_file_name|
    output_file_name = input_file_name.sub(
      INPUT_DIRECTORY_NAME,
      OUTPUT_DIRECTORY_NAME
    ).sub(
      INPUT_FILE_EXTENSION,
      OUTPUT_FILE_EXTENSION
    )
    `#{PANDOC} #{input_file_name} -o #{output_file_name}`
  end
end

desc "Remove the generated PDF"
task :clean do
  `rm -rf #{OUTPUT_DIRECTORY_NAME}`
  `mkdir #{OUTPUT_DIRECTORY_NAME}`
end

desc "Regenerate the PDF and push it to GitHub."
task :release => :regenerate do
  puts "Releasing new version to GitHub"
  `git commit -am 'New version of PDF'`
  `git push origin master`
end

desc "Default task: regenerate PDF."
task :default => :regenerate
