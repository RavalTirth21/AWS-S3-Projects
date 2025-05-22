# 📸 AWS S3 Static Website Hosting (Screenshot-Based Tutorial)

This project provides a **step-by-step guide to hosting a static website on AWS S3**, using only screenshots to demonstrate the full process — from bucket creation to website access in the browser.

Each screenshot represents a major step in the setup process.

---

## 🧾 Screenshots Overview

| Screenshot File                  | Description |
|----------------------------------|-------------|
| **01-Static-Website-Bucket.png** | Step 1: Creating the S3 bucket for static website hosting. |
| **02-Object-Website-Bucket.png** | Step 2: Uploading website files (e.g., `index.html`, `error.html`) into the bucket. |
| **03-Enable-Static-Website.png** | Step 3: Enabling the static website hosting feature under bucket properties. |
| **04-Bucket-Policy.png**         | Step 4: Adding a bucket policy to allow public access to the website content. |
| **05-Static-Website-Browser.png**| Step 5: Viewing the hosted website via the static website endpoint in a browser. |

---

## 🪜 Project Steps (Visual Walkthrough)

### 🥇 1. Create an S3 Bucket
- Refer to `01-Static-Website-Bucket.png`.
- Name the bucket (must be globally unique).
- Disable **"Block all public access"** if prompted.

### 🥈 2. Upload Website Files
- Refer to `02-Object-Website-Bucket.png`.
- Upload your static files (`index.html`, `error.html`, CSS/JS files) into the bucket.

### 🥉 3. Enable Static Website Hosting
- Refer to `03-Enable-Static-Website.png`.
- Navigate to the **Properties** tab.
- Scroll to **Static Website Hosting** and enable it.
- Specify **index document** and **error document** (usually `index.html` and `error.html`).

### 🏅 4. Add Bucket Policy for Public Access
- Refer to `04-Bucket-Policy.png`.
- Add the following JSON policy to allow public read access:
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
      {
        "Sid": "PublicReadGetObject",
        "Effect": "Allow",
        "Principal": "*",
        "Action": "s3:GetObject",
        "Resource": "arn:aws:s3:::your-bucket-name/*"
      }
    ]
  }
