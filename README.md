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

Code is written in VSCode and pushed to Github. Github actions automatically syncs the website to the S3 bucket and invalidates CloudFront on every push to ```main``` so that that updates appear immediately<br>

**Visitor Counter**<br>
- User loads website through CloudFront<br>
- JS in ```index.html``` calls the API Gateway endpoint<br>
- API Gateway triggers the Lambda function<br>
- Lambda updates DynamoDB visitor count<br>
- Lambda returns new count<br>
- Website displays count<br>

**AWS Services Summary**<br>
- S3<br>
- CloudFront<br>
- Route53<br>
- ACM<br>
- API Gateway<br>
- Lambda<br>
- DynamoDB<br>
- IAM<br>

**Github Repo Information**
Basic repo structure. with Lambda backed up in ```/backend``` and ```error.html``` to catch errors if CloudFront returns a 403/404.
Readme added in lieu of Blog

**Security**
AWS Credentials stored in Github Secrets
API throttled to minimise spam/spending
AWS Budgets used to alert any spending over budget

**Future Improvements**
- Restrict CORS to resume domain
- Convert infrastructure to IaC
- Add proper tests for Lambda
- Overall Polich (Hamburger menu in mobile view, more attention to aesthetics)

**Credits**
Cloud Resume Challenge: https://cloudresumechallenge.dev


