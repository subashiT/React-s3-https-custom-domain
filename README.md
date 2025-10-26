# Task 1 – Host a React Application on Amazon S3 with HTTPS and Custom Domain

### Objective
Host a simple React web application using **Amazon S3** static-website hosting, attach a **custom domain**, and enable **HTTPS** access.


## Current Progress
**React App Deployed**  
The React build is uploaded and publicly accessible via S3 static website hosting.  
> http://react-app-bucket-subas.s3-website-us-east-1.amazonaws.com

**Pending**  
Free domain + HTTPS setup will be completed after GitHub Student Pack activation (within 72 hours from 05/10).  
Once activated, CloudFront + ACM + custom domain integration will be added here.


## Implementation Plan

### Host React App on S3 (Completed)
1. Build the React app  
   ```bash
   npm run build

2. Create an S3 bucket (react-app-bucket-subas)

3. Enable Static Website Hosting

      Index document: index.html

      Error document: error.html

4. Upload contents of the /build folder to S3.

5. Set Bucket Policy for public read access.

Proof #1 - Static Hosting Setup
![Alt Text](./screenshots/S3%20Static%20Hosting%20Setup.png)

Proof #2 - React Application View
![Alt Text](./screenshots/Public%20React%20application%20Working.png)

### Enable HTTPS and Custom Domain (Completed)

1. **Registered free domain** via GitHub Student Pack: `reactrocket.codes`
2. **Requested SSL certificate** in AWS ACM (us-east-1 region)  
3. **Created CloudFront distribution**  
   - Origin: S3 static website endpoint  
   - Alternate domain: `reactrocket.codes`, `www.reactrocket.codes`  
   - SSL: ACM certificate  
   - Redirect HTTP → HTTPS  
4. **Updated DNS** (at domain registrar):  
   - `A` record → CloudFront distribution domain  
   - `CNAME` for `www` → CloudFront  

**Live HTTPS URL**: [https://yourdomain.com](https://reactrocket.codes)



