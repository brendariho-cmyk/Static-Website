# static-website-
Small businesses want to host lightweight websites (landing pages, portfolios, info pages) without paying for servers — securely and with fast global access.

1. Project Summary

Short description of the problem + solution.

2. Business Problem

Small businesses need reliable, fast-loading websites. Traditional hosting is slow, insecure, and doesn’t scale globally.

3. Solution Overview

One paragraph describing S3 hosting + CloudFront + HTTPS.

4. Architecture Diagram

📌 See diagram:
architecture-diagram/final-diagram.png

5. Components

S3 Static Website Bucket

Bucket Policy (public access locked down)

CloudFront Distribution (CDN + HTTPS + caching)

(Optional) Route 53 Domain

IAM Role for deployment

CloudWatch for access logs

6. Architecture Design

Explain bucket setup, CloudFront setup, caching behaviors.

7. Security

Bucket Public Access Block
Least-privilege IAM policy
CloudFront Origin Access Control (OAC)

8. Performance

Caching
Global edge distribution
Latency improvements

9. Cost Considerations

Everything is free-tier eligible.
CloudFront costs minimal for low traffic.

10. Testing

Links + screenshots

11. Future Improvements

Add CI/CD

Add WAF

Add Route 53 domain

Add versioned website pipeline

12. How to Reproduce

Short checklist with steps.

13. Contact

Your email + GitHub link.
