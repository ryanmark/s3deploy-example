# s3deploy-example
Example project that syncs an upload directory to a s3 bucket.

## Usage

Install the bundle to get started...

```shell
bundle install
```

You need to declare two environment variables with your S3 credentials...

```shell
export AWS_ACCESS_KEY_ID=blah
export AWS_SECRET_ACCESS_KEY=blah
```

You can then deploy the contents of `upload` to the root of a bucket...

```shell
bundle exec rake deploy bucket=www.mywebsite.com
```

## Details

The deploy task will automatically gzip the filetypes listed in the Rakefile, and it will
set all deployed files to public access. The task will only upload files that have changed
on the server. It will not delete anything outright, but it will overwrite files that have changed.
