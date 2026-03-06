## The Compliance Janitor: Automated S3 Governance
Serverless Cloud Governance project focused on enforcing resource tagging policies across AWS environments. By leveraging AWS Lambda and Boto3, this system automatically audits S3 buckets for compliance tags, providing real-time visibility into "Shadow IT" and ensuring resources follow organizational standards. ✨

--
## Project Workflow
## 1. Defining the Governance Policy
The setup: Configuring an AWS Lambda function named Compliance-Janitor using Python 3.12 to act as the automated auditor for the S3 environment.
<img width="1920" height="851" alt="The_Project_The_Compliance_ Janitor_2" src="https://github.com/user-attachments/assets/99cf7ecb-ba1a-4c66-ae61-dae97dc50638" />

--
## 2. Developing the Audit Logic (Boto3)
The "Brain": Developing Python logic that iterates through all S3 buckets and utilizes get_bucket_tagging to detect the required CheckedByJanitor compliance tag.
<img width="1920" height="960" alt="The_Project_The_Compliance_ Janitor_4" src="https://github.com/user-attachments/assets/8a53bb47-f23a-4bed-851c-d1f377d24465" />

--
## 3. Enforcing Least Privilege Access
Security-first architecture: Attaching a specific AmazonS3ReadOnlyAccess policy to the Lambda execution role, ensuring the Janitor can audit metadata without access to the data itself.
<img width="1920" height="859" alt="The_Project_The_Compliance_ Janitor_6" src="https://github.com/user-attachments/assets/8b699779-1490-43fb-892c-b4f5aa4c9857" />

--
## 4. Identifying Non-Compliance
The "Audit" in action: CloudWatch Logs capturing a high-risk alert when the Janitor discovers a bucket (compliance-audit-test-2026) missing the mandatory tags.
<img width="1920" height="821" alt="The_Project_The_Compliance_ Janitor_11" src="https://github.com/user-attachments/assets/e43f41de-7220-4b8f-a3f7-b19595abf61c" />

--
## 5. Verified Remediation
The Proof of Concept: After applying the correct tag in the S3 console, the Janitor re-scans and confirms the resource is now "Compliant," closing the security gap.
<img width="1920" height="823" alt="The_Project_The_Compliance_ Janitor_15" src="https://github.com/user-attachments/assets/247bd36c-0f79-4a09-958c-0702763b49c5" />


## Tech Stack
Cloud: AWS (S3, Lambda, IAM, CloudWatch)

Language: Python 3.12

Library: Boto3 (AWS SDK)

Security Principle: Infrastructure Governance & Automated Incident Response
