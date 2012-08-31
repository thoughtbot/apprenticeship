SOURCE_FILE_NAMES = ['onboarding-packet.md'].join(' ')
BOOK_FILE_NAME = 'onboarding-packet'

PDF_BUILDER = 'pandoc'
PDF_BUILDER_FLAGS = [
  '--latex-engine xelatex',
  '--template ./templates/pdf-template.tex',
  '--listings'
].join(' ')

directory 'book'

file 'onboarding.pdf' => [:clean, 'book']  do
  `#{PDF_BUILDER} #{PDF_BUILDER_FLAGS} #{SOURCE_FILE_NAMES} -o ./book/#{BOOK_FILE_NAME}.pdf`
end

task :clean do
  `rm -f #{BOOK_FILE_NAME}.pdf`
end

task :release => 'onboarding.pdf' do
  puts "Releasing new version to GitHub"
  `git commit -am 'New version of PDF'`
  `git push origin master`
end

task :default => 'onboarding.pdf'
