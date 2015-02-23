require 'rubygems'
require 'bundler'
Bundler.setup

require 's3deploy/tasks'

S3deploy.configure do
  bucket ENV['bucket']
  app_path ''
  dist_dir 'upload'
  gzip [/\.js$/, /\.css$/, /\.json$/, /\.html$/, /\.csv$/,
        /\.eot$/, /\.svg$/, /\.ttf$/, /\.woff$/]

  access_key_id ENV['AWS_ACCESS_KEY_ID']
  secret_access_key ENV['AWS_SECRET_ACCESS_KEY']
end

task :deploy do
  Rake::Task['s3:deploy'].invoke
end
