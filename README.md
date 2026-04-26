# AWS Security and Identity Assignment

## 📘 Overview
This project demonstrates AWS Identity and Access Management (IAM) features, including creating restricted users, enabling Multi-Factor Authentication (MFA), and creating roles with custom policies.

---

## 🎯 Objectives
- Create an IAM user with restricted permissions  
- Set up Multi-Factor Authentication (MFA) for the IAM user  
- Create and attach a custom policy to an IAM role  

---

## 🔐 1. Creating an IAM User with Restricted Permissions

### Steps Taken:
1. Logged into AWS Management Console  
2. Navigated to IAM → Users → Create user  
3. Created a user named `limited-user`  
4. Enabled AWS Management Console access  
5. Attached permission policy: `AmazonS3ReadOnlyAccess`  

### Testing:
- Logged out from admin/root account  
- Logged in using the IAM user credentials  

Verified:
- Able to view S3 buckets  
- Unable to create or delete buckets  

### Screenshots:
- IAM user creation  
- Permissions assigned  
- Access test results  

---

## 🔑 2. Setting Up Multi-Factor Authentication (MFA)

### Steps Taken:
1. Navigated to IAM → Users → limited-user  
2. Opened Security credentials tab  
3. Clicked Assign MFA device  
4. Selected Virtual MFA device  
5. Used Google Authenticator to scan QR code  
6. Entered two consecutive codes to complete setup  

### Testing:
- Logged out and logged back in  
- Confirmed MFA prompt during login  

### Screenshots:
- MFA device setup  
- Successful MFA verification  

---

## 📜 3. Creating and Attaching a Custom Policy to an IAM Role

### Custom Policy (JSON):

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances"
      ],
      "Resource": "*"
    }
  ]
}

### Steps Taken:
1. Navigated to IAM → Policies → Create policy  
2. Created a policy named EC2ReadOnlyPolicy  
3. Navigated to IAM → Roles → Create role  
4. Selected AWS service (EC2 use case)  
5. Attached the custom policy  
6. Named role EC2ReadOnlyRole  

---

## 🧪 Testing the IAM Role

Due to the absence of an EC2 instance, the role was not attached to a running service.

However:
- The policy was successfully created  
- The role was successfully created and configured  
- The setup is ready to be attached to an EC2 instance when available  

---

## 📂 Project Structure

aws-security-identity/  
│── README.md  
│── screenshots/  
│   ├── iam-user.png  
│   ├── permissions.png  
│   ├── mfa-setup.png  
│   ├── policy.png  
│   └── role.png  

---

## 🔍 Key Concepts

### Principle of Least Privilege
Users and roles were granted only the permissions necessary to perform specific tasks, reducing security risks.

### Multi-Factor Authentication (MFA)
MFA adds an extra layer of security by requiring a second verification step beyond passwords.

---

## ✅ Conclusion
This assignment demonstrated how to manage access securely using AWS IAM by creating restricted users, enabling MFA, and defining custom roles and policies.

---

## 🚀 Author
Name: [Your Name]  
Course: Cloud Computing  
Program: M4ACE 30 Days Challenge  
