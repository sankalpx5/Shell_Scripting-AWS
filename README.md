# **Shell_Scripting-AWS**


 # 1. Github-api

**A simple shell script to list users with access (in this case read access) to a GitHub repository**

## Overview

This project contains a shell script, `list-user.sh`, that leverages the GitHub API to retrieve and display a list of users who have access to a specified GitHub repository using an EC2 VM on AWS. 

#### Key features:
- Utilize AWS EC2 instance to run shell script using SSH.
- Leverages the GitHub API to retrieve user information.  
- Filters collaborators based on read access (pull permission).  
- Displays a list of users with read access.  

## Installation

No installation is required. You only need a shell environment (e.g., Bash) and a way to make API calls (e.g., `curl` or `wget`).

## Usage

- Elevate script permissions and install necessary libraries.
  
   ```bash
   chmod 777 list-users.sh
   sudo apt install jq -y
   ```

 - **Run the script:**
   ```bash
   ./list-user.sh organization_name repository_name
   ```
   - Replace `organization_name` with the repository's organization username.
   - Replace `repository_name` with the name of the repository.

## Output

The script will output a list of usernames, one per line, representing those with access to the queried organization's repository.

<img width="646" alt="image" src="https://github.com/sankalpx5/Shell_Scripting-AWS/assets/115892823/92f8aa1f-977e-41b6-98e8-a1f49449fde7">
<br></br>
<img width="959" alt="image" src="https://github.com/sankalpx5/Shell_Scripting-AWS/assets/115892823/1791bffe-6765-4674-a642-bed72abb9b49">  
<br></br>  
<br></br>  

# 2. AWS S3 Event-Triggered Email Notification Workflow
**This project automates the creation of AWS resources and triggers email notifications whenever new objects are uploaded to an S3 bucket.**  

## Features
- Automatically creates:  
     - IAM role with appropriate permissions  
     - S3 bucket  
     - Lambda function triggered by object creation  
     - SNS topic for email notifications  
- Sends email notifications via SNS to a specified email address  
- Written in Python and Bash for platform-agnostic deployment  
## Technologies Used
- Python 3.8: Script execution and Lambda function
- Bash: Resource creation and script execution
- AWS CLI: Resource configuration and management
- boto3: AWS SDK for Python (used in Lambda function)

## Setup
### Prerequisites:
- AWS account
- AWS CLI installed and configured
- Python 3.8 and boto3 installed (in virtual environment recommended)

### Instructions:

1. Clone the repository:
```Bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
``` 

2. Run the setup script:
```Bash
 ./s3-notification-triggers.sh
```

 The script will prompt for the email address to receive notifications.
3. Upload files to the S3 bucket:
     - Any new object upload will trigger the Lambda function and send an email notification.  
     
## Scripts and Functionality

#### s3-notification-triggers.sh:

- Creates the necessary AWS resources:
     - IAM role with permissions for S3, Lambda, and SNS
     - S3 bucket
     - Lambda function (s3-lambda-function/s3-lambda-function.py)
     - SNS topic for email notifications
     - Email subscription to the SNS topic for the provided email address
- Uploads a sample file to the S3 bucket to demonstrate functionality
  
#### s3-lambda-function/s3-lambda-function.py:

- Python script triggered by object creation in the S3 bucket
- Parses the event data to extract bucket name and object key
- Logs a message about the uploaded file
- Publishes an SNS message with file details to the configured SNS topic
- Returns a success response

## Usage and Workflow
- Run the s3-notification-triggers.sh script to set up the resources.
- Upload files to the S3 bucket.
- The Lambda function will be triggered for each upload.
- The uploaded file's details will be published to the SNS topic.
- An email notification will be sent to the specified address.

 ![image](https://github.com/sankalpx5/Shell_Scripting-AWS/assets/115892823/f857ff0d-6469-46be-b41b-6368e1b8acd9)







