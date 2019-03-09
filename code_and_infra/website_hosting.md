# Website Hosting
For simple websites, if they can be made mostly or entirely static, host them in AWS S3 (with Cloudfront if desired) until and unless you start building a lot of your own infrastructure (at which point you will have outgrown this guide). Even for complex websites, you can often still host most of them in S3 and have them do AJAX calls to live servers for variable data.

If the above solution won't work for you, nginx is a reasonable option; apache is also viable, but is more complex.
