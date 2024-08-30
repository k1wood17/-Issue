import requests

# Set the GitHub API endpoint and authentication token
endpoint = "https://api.github.com/repos/{owner}/{repo}/issues"
token = "your-github-token"

# Set the issue title and body
title = "New Issue"
body = "This is a new issue created using the GitHub API"

# Create the issue
response = requests.post(endpoint, headers={"Authorization": f"Bearer {token}"}, json={"title": title, "body": body})

# Check if the issue was created successfully
if response.status_code == 201:
    print("Issue created successfully")
else:
    print("Error creating issue")
