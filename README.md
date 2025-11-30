# 🎨 **Artist Portfolio Static Website on AWS (S3 + Access Logging)**

A scalable, secure, and cost-efficient static website deployed using Amazon S3. This project demonstrates professional static hosting architecture, IAM security, S3 bucket policies, and server access logging designed to support real-world business needs for small creative entrepreneurs.

---

# **1. Business Problem: Artists Need an Affordable and Reliable Online Portfolio**

Independent artists often struggle with hosting platforms that are either too expensive, too complex, or too limited in customization.
They need a **simple, fast, low-maintenance website** where they can showcase their artwork professionally, without managing servers or paying for costly website builders.

If the website is insecure or lacks logging, they risk content theft, unauthorized access, or inability to monitor traffic.

---

# **2. Solution Overview**

This project implements a **static portfolio website** hosted entirely on **Amazon S3**, using:

* S3 Static Website Hosting
* S3 Bucket Policies for secure public access
* IAM security controls
* S3 Server Access Logging for monitoring
* Organized front-end structure (HTML + CSS)
* Professional documentation

This architecture allows artists to deploy fully customized websites with **global availability**, **near-zero cost**, and **complete visibility into access patterns**.

---

# **3. Architecture Diagram**

```
![Architecture Diagram](Architecture Diagram/S3 Static Website Architecture.png)
```

---

# **4. Components**

### **Storage Layer**

* **S3 Website Hosting Bucket**

  * Hosts `index.html`, `gallery.html`, `about.html`, `style.css`, and images
  * Public read-only access enabled through bucket policy

* **S3 Logging Bucket**

  * Stores S3 Server Access Logs
  * Versioning + prefix for organized log files

---

# **5. Website Structure**

### **Project Files**

```
index.html
about.html
gallery.html
style.css
/images
    - image1.jpg
    - image2.jpg
    - ...
```

### **GitHub Structure**

```
/screenshots            # Architecture + AWS screenshots
/index.html
/about.html
/gallery.html
/style.css
/README.md
/images (optional .gitignore if large)
```

---

# **6. Security**

### **Bucket Policy (Website Bucket)**

* Grants public **read-only** access to objects
* Blocks uploads/deletions from the public
* Enforces secure architecture without exposing the logging bucket

### **IAM**

* Least Privilege
* S3FullAccess only for the logged-in admin performing deployment

### **Logging Bucket**

* **Completely private**
* Only accessible by the Website bucket for logging delivery

---

# **7. S3 Website Hosting Configuration**

### **Hosting Enabled**

* Static website endpoint
* `index.html` as root
* `error.html` optional

### **Public Accessibility**

* Only the website bucket is public
* Logging bucket remains private

### **File Upload**

* HTML, CSS, and images uploaded into root + images folder

---

# **8. S3 Server Access Logging**

### **Configuration**

* Enabled on website bucket
* Target: Logging bucket
* Prefix: `logs/`

### **Purpose of Logging**

* Activity monitoring
* Traffic insights
* Security audits
* Troubleshooting unauthorized access

### **Verification**

Screenshots include:

* Logging enabled page
* Log bucket content
* Raw log file opened

---

# **9. Cost Considerations**

| Service                   | Cost                                |
| ------------------------- | ----------------------------------- |
| Amazon S3 Website Hosting | **Free tier eligible**              |
| S3 Storage                | Low-cost object storage             |
| S3 Logging                | Minimal cost for log objects        |
| CloudFront                | **Not used** (Account not verified) |
| IAM                       | Free                                |
| Browser testing           | Free                                |

Architecture is designed to be **as close to free as possible**, ideal for small creators.

---

# **10. Testing Performed**

### ✔ Website Rendering Test

* Tested website endpoint
* Verified correct loading of HTML, CSS, and all images

### ✔ Public Access Test

* Confirmed that bucket policy returns `200 OK`
* Verified that the logging bucket is not publicly accessible

### ✔ Logging Test

* Accessed site multiple times
* Confirmed log delivery in logging bucket
* Opened raw logs to validate entries

### ✔ File Consistency Test

* Ensured all linked images load correctly
* Validated CSS styling across all pages

Screenshots for all tests are included in:

```
/screenshots
```

---

# **11. What I Would Improve (Future Enhancements)**

To evolve this into a production-grade portfolio site:

* Add **CloudFront CDN** (after account verification)

  * Faster global performance
  * HTTPS
  * DDoS protection via AWS Shield
* Add **custom domain** via Route 53
* Add **contact form** using AWS Lambda + API Gateway
* Add **image optimization pipeline**
* Add **CI/CD deployment** via GitHub Actions
* Add **versioning** on the website bucket
* Automate architecture using **Terraform**

---

# **12. How to Reproduce This Architecture (Checklist)**

### **1. Create Website Bucket**

* Enable static hosting
* Upload HTML, CSS, images
* Add bucket policy for public read access

### **2. Create Logging Bucket**

* Keep private
* No public access

### **3. Enable Logging on Website Bucket**

* Set target bucket
* Add prefix

### **4. Test Website**

* Visit S3 endpoint
* Confirm rendering

### **5. Verify Logs**

* Check logging bucket
* Confirm delivered log files

---

# **13. Final Notes**

This project demonstrates practical AWS skills:

* Configuring S3 for website hosting
* Implementing access logging
* Designing a micro static-website architecture
* Writing clean documentation
* Organizing GitHub repos professionally

This is suitable for portfolio display and aligns with real client scenarios (artists, small businesses, photographers, personal brands).

---







