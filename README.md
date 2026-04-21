# 🚀 EC2 to S3 Access using IAM Role (Troubleshooting)

## 📌 Overview
This project demonstrates how an EC2 instance accesses a private S3 bucket using IAM Roles, and how different failures occur when identity or permissions are missing.

---

## 🪣 Setup
- S3 Bucket: ec2-s3-private (private)
- File uploaded to bucket
- EC2 instance launched (Ubuntu)

---

## 🔍 Phase 1: Verification
S3 file uploaded successfully  
EC2 instance running  

---

## ❌ Phase 2: Authentication Failure (No Identity)

Command:
aws s3 ls s3://ec2-s3-private

Error:
Unable to locate credentials

👉 Reason: No IAM Role attached to EC2 instance

---

## 🔧 Phase 3: Attach IAM Role

- Created IAM Role for EC2
- Attached role to instance

---

## ❌ Phase 4: Authorization Failure (No Permission)

Error:
Access Denied

👉 Reason: IAM Role had no S3 permissions

---

## 🔧 Phase 5: Attach Policy

- Attached:
AmazonS3ReadOnlyAccess

---

## ✅ Phase 6: Success

Command worked successfully:
aws s3 ls s3://ec2-s3-private

---

## 🧠 Key Learning

Access in AWS requires:

Identity (IAM Role) + Permission (Policy)

- No identity → No credentials  
- No permission → Access Denied  
- Both present → Access granted  

---

## 📸 Screenshots

1. S3 file upload  
2. EC2 running  
3. Credential error  
4. IAM role attached  
5. Access denied  
6. Policy attached  
7. Successful access  

---

## 🛠️ Tools Used
- AWS EC2
- AWS S3
- IAM Roles
- AWS CLI
