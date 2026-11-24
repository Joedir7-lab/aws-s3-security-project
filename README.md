# aws-s3-security-project
Securing Cloud storage using AWS S3 - Beginner Cloud security Project 
# Securing Cloud Storage Using AWS S3

## Project Overview
As a Junior Cloud Security Engineer, I was tasked with creating a secure cloud storage environment for a company to store business documents using Amazon S3. The goal was to implement basic security controls to prevent unauthorised access.

## Project Objectives
- Understand how cloud storage works
- Create an Amazon S3 bucket
- Configure basic cloud security settings
- Prevent unauthorised access
- Understand how encryption protects stored data
- Document a technical project using GitHub

## Tools Used
- **Platform:** Amazon Web Services (AWS)
- **Service:** Amazon S3 (Simple Storage Service)
- **Region:** -eu-north-1-an
- **Documentation:** GitHub
- **File Type:** Sample .txt file only (no real company data)

## Implementation Steps

### Task 1: AWS Account Setup
1. Created an AWS account
2. Logged into AWS Management Console
3. Searched for and opened Amazon S3

### Task 2: Create an S3 Bucket
1. Clicked "Create bucket"
2. Bucket name: `amabuckett-397303792858-eu-north-1-an ` (must be globally unique)
3. AWS Region: af-south-1 (Cape Town)
4. Kept **Block all public access** ENABLED
5. Created bucket

### Task 3: Implement Security Controls
- Confirmed Block Public Access is ON
- Enabled Default Encryption: **Server-Side Encryption with Amazon S3 managed keys (SSE-S3) - AES-256**
- Reviewed Bucket Policy: No public policy attached
- Reviewed Permissions: Only bucket owner has access
- Versioning: Reviewed (can be enabled for extra protection)

### Task 4: Upload a File
1. Created a sample file `sample-file.txt`
2. Uploaded it to the bucket
3. Verified upload was successful in Objects tab
4. Tested public URL - Access Denied (as expected, proving public access is blocked)

## Security Controls Applied
| Control | Status | Purpose |
| --- | --- | --- |
| Block Public Access | Enabled | Prevents anyone on the internet from accessing bucket |
| Server-Side Encryption (SSE-S3) | Enabled | Encrypts data at rest with AES-256 |
| Bucket Policy | No public access | Controls who can access the bucket |
| IAM Authentication | Enabled | Only authenticated AWS users can access |
| No Sensitive Data | Verified | Only sample files uploaded |

## Security Analysis Questions

### 1. What is Amazon S3?
Amazon S3 (Simple Storage Service) is a scalable cloud storage service from AWS used to store and retrieve any amount of data, such as documents, images, backups, and videos, from anywhere on the internet.

### 2. What is an S3 bucket?
An S3 bucket is a container for storing objects (files) in Amazon S3. Each bucket has a globally unique name and stores files with their metadata, similar to a folder on a computer but in the cloud.

### 3. Why should public access be blocked?
To prevent unauthorised users on the internet from viewing, downloading, or deleting company files. Public buckets are a major cause of data breaches.

### 4. What is encryption, and why is it important?
Encryption converts readable data into an unreadable coded format that can only be read with the correct key. It protects data at rest and in transit, so even if someone steals the files, they cannot read them without the key.

### 5. What could happen if a company accidentally exposes its S3 bucket?
- Sensitive data leak (customer info, passwords, financial documents)
- Identity theft and fraud
- Financial loss and legal fines (e.g. POPIA / GDPR)
- Loss of customer trust and company reputation
- Attackers could delete or ransomware the data

### 6. What is the difference between authentication and authorisation?
- **Authentication:** Verifying WHO you are (e.g. logging in with username/password)
- **Authorisation:** Verifying WHAT you are allowed to do (e.g. can you read, write, or delete files?)

### 7. Mention three ways to secure cloud storage
1. Enable Block Public Access and use private buckets by default
2. Enable encryption (SSE-S3 / SSE-KMS) for data at rest
3. Use strong IAM policies, MFA, and least-privilege access - only give users the minimum permissions they need

## Security Findings
# Security Findings

## Finding 1: Public Access Risk
- **Risk:** If Block Public Access is disabled, anyone can access files via a public URL.
- **Control Applied:** Block all public access enabled.
- **Result:** Tested object URL -> Access Denied. Secure.

## Finding 2: Unencrypted Data Risk
- **Risk:** Without encryption, stolen data can be read in plain text.
- **Control Applied:** SSE-S3 (AES-256) enabled by default.
- **Result:** All objects are automatically encrypted at rest.

## Finding 3: Over-Permissioned Access
- **Risk:** Giving too many users access increases breach risk.
- **Control Applied:** No bucket policy added, only bucket owner has access. Principle of least privilege applied.

## Finding 4: Human Error
- **Risk:** Accidentally uploading real/confidential files or AWS keys.
- **Control Applied:** Only sample .txt file uploaded. No credentials in GitHub or S3.

## Lessons Learned
# Lessons Learned

1. Cloud security starts during setup, not after. Enabling Block Public Access and encryption from the beginning is easier than fixing a breach.
2. I learned the difference between authentication (who you are) and authorisation (what you can do).
3. I learned that a bucket is just a container, but the security settings around it are what protect the data.
4. I learned to never upload real or sensitive data to a test environment, and never upload AWS keys to GitHub.
5. I learned how to document a technical project professionally using GitHub, README, screenshots, and structured findings.

## Conclusion
I successfully created a secure S3 bucket with Block Public Access enabled and server-side encryption. The project demonstrated that security must be configured by default, not added later. A private, encrypted bucket prevents unauthorised access and protects company data.
