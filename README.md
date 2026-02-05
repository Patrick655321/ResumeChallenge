**ResumeChallenge**
Cloud Resume Challenge (AWS)

This project is my implementation opf the CLoud Resume Challenge using AWS.

It hosts my website as a statice website and includes a serverless visitor counter backed by AWS services

**Live Site**
[https://www.hamer-patrick-resume.com](https://www.hamer-patrick-resume.com)

**Architecture Overview**

**Frontend**
__S3__ Stores the static site files (HTML/CSS).
__Cloudfront__ serves the site globally with caching and HTTPS.
__Route 53__ points my custom domain to CloudFront
__ACM__ provides SSL/TLS certificate (enables HTTPS)

**Backend**
__API Gateway__ (HTTP API) exposes public endpoint (GET /count)
__Lambda__ increases and returns the visitor count value
__DynamoDB__ stores the count value.

Code is written in VSCode and pushed to Github. Github actions automatically deploys the website to the S3 bucket and invalidates CloudFront on every push to ```main```

