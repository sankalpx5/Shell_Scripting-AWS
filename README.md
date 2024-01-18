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







