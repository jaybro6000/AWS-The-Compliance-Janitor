## The Compliance Janitor: Automated S3 Governance
Serverless Cloud Governance project focused on enforcing resource tagging policies across AWS environments. By leveraging AWS Lambda and Boto3, this system automatically audits S3 buckets for compliance tags, providing real-time visibility into "Shadow IT" and ensuring resources follow organizational standards. ✨

📸 Project Workflow
1. Defining the Governance Policy
The setup: Configuring an AWS Lambda function named Compliance-Janitor using Python 3.12 to act as the automated auditor for the S3 environment.
![The_Project_The_Compliance_Janitor_2.png]

2. Developing the Audit Logic (Boto3)
The "Brain": Developing Python logic that iterates through all S3 buckets and utilizes get_bucket_tagging to detect the required CheckedByJanitor compliance tag.
![The_Project_The_Compliance_Janitor_4.png]

3. Enforcing Least Privilege Access
Security-first architecture: Attaching a specific AmazonS3ReadOnlyAccess policy to the Lambda execution role, ensuring the Janitor can audit metadata without access to the data itself.
![The_Project_The_Compliance_Janitor_6.png]

4. Identifying Non-Compliance
The "Audit" in action: CloudWatch Logs capturing a high-risk alert when the Janitor discovers a bucket (compliance-audit-test-2026) missing the mandatory tags.
![The_Project_The_Compliance_Janitor_11.png]

5. Verified Remediation
The Proof of Concept: After applying the correct tag in the S3 console, the Janitor re-scans and confirms the resource is now "Compliant," closing the security gap.
![The_Project_The_Compliance_Janitor_15.png]

🛠️ Tech Stack
Cloud: AWS (S3, Lambda, IAM, CloudWatch)

Language: Python 3.12

Library: Boto3 (AWS SDK)

Security Principle: Infrastructure Governance & Automated Incident Response

Tips for your GitHub:
Filenames: Make sure when you upload your photos to your GitHub repository, the filenames match exactly what is in the brackets above (e.g., The_Project_The_Compliance_Janitor_2.png).

Folder Structure: If you put your images in a folder named images, change the syntax to ![images/The_Project_The_Compliance_Janitor_2.png]
