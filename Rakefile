#!/usr/bin/env ruby

require 'html/proofer'

task :test do
  HTML::Proofer.new("./_site", {:href_ignore => ["#", "\\\"#\\\"", "https://www.linkedin.com/in/icarocaldeira"]}).run
end