# **Shell_Scripting-AWS**


 # 1. Github-api

**A simple shell script to list users with access to a GitHub repository**

## Overview

This project contains a shell script, `list-user.sh`, that leverages the GitHub API to retrieve and display a list of users who have access to a specified GitHub repository. 

## Installation

No installation is required. You only need a shell environment (e.g., Bash) and a way to make API calls (e.g., `curl` or `wget`).

## Usage

 **Run the script:**
   ```bash
   ./list-user.sh owner_name repository_name
   ```
   - Replace `owner_name` with the repository owner's username.
   - Replace `repository_name` with the name of the repository.

## Output

The script will output a list of usernames, one per line, representing those with access to the repository.







