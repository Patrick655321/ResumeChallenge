**ResumeChallenge** <br>
Cloud Resume Challenge (AWS)<br>
<br>
This project is my implementation opf the CLoud Resume Challenge using AWS.<br>
<br>
It hosts my website as a statice website and includes a serverless visitor counter backed by AWS services<br>

**Live Site**<br>
[https://www.hamer-patrick-resume.com](https://www.hamer-patrick-resume.com)

**Architecture Overview**<br>

**Frontend**<br>
__S3__ Stores the static site files (HTML/CSS).<br>
__Cloudfront__ serves the site globally with caching and HTTPS.<br>
__Route 53__ points my custom domain to CloudFront.<br>
__ACM__ provides SSL/TLS certificate (enables HTTPS).<br>

**Backend**<br>
__API Gateway__ (HTTP API) exposes public endpoint (GET /count).<br>
__Lambda__ increases and returns the visitor count value.<br>
__DynamoDB__ stores the count value.<br>

Code is written in VSCode and pushed to Github. Github actions automatically deploys the website to the S3 bucket and invalidates CloudFront on every push to ```main```<br>

