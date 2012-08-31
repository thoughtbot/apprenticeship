OUTPUT_DIRECTORY_NAME = 'pdf'
SOURCE_FILE_NAMES = ['onboarding-packet.md'].join(' ')
OUTPUT_FILE_PATH = File.join('.', OUTPUT_DIRECTORY_NAME, 'onboarding-packet.pdf')

PDF_BUILDER = 'pandoc'
PDF_BUILDER_FLAGS = [
  '--latex-engine xelatex',
  '--template ./templates/pdf-template.tex',
  '--listings'
].join(' ')

directory OUTPUT_DIRECTORY_NAME

task :regenerate => [:clean, OUTPUT_DIRECTORY_NAME] do
  `#{PDF_BUILDER} #{PDF_BUILDER_FLAGS} #{SOURCE_FILE_NAMES} -o #{OUTPUT_FILE_PATH}`
end

task :clean do
  `rm -f #{OUTPUT_FILE_PATH}`
end

task :release => :regenerate do
  puts "Releasing new version to GitHub"
  `git commit -am 'New version of PDF'`
  `git push origin master`
end

task :default => :regenerate
