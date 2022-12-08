require 'html-proofer'

task default: %w[build]

task :build do
    sh "bundle exec jekyll build"
end

task :serve do
    sh "bundle exec jekyll serve"
end

task :test do
    # this test runs HTMLProofer on your built site; find out more at https://github.com/gjtorikian/html-proofer
    HTMLProofer.check_directory("./_site").run
end
