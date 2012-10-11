OUTPUT_DIRECTORY_NAME = 'pdf'
SOURCE_FILE_NAME = 'onboarding-packet.md'
OUTPUT_FILE_PATH = File.join('.', OUTPUT_DIRECTORY_NAME, 'onboarding-packet.pdf')

PANDOC_FLAGS = [
  '--latex-engine xelatex',
  '--template ./templates/pdf-template.tex',
  '--listings'
].join(' ')

PANDOC = ['pandoc', PANDOC_FLAGS].join(' ')

directory OUTPUT_DIRECTORY_NAME

desc "Regenerate the PDF."
task :regenerate => [:clean, OUTPUT_DIRECTORY_NAME] do
  `#{PANDOC} #{SOURCE_FILE_NAME} -o #{OUTPUT_FILE_PATH}`
end

desc "Remove the generated PDF"
task :clean do
  `rm -f #{OUTPUT_FILE_PATH}`
end

desc "Regenerate the PDF and push it to GitHub."
task :release => :regenerate do
  puts "Releasing new version to GitHub"
  `git commit -am 'New version of PDF'`
  `git push origin master`
end

desc "Default task: regenerate PDF."
task :default => :regenerate
