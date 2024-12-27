import requests

# Replace with your GitHub username and token
username = 'your-username'
token = 'your-token'
repo_name = 'my-repository'

url = f'https://api.github.com/repos/{username}/{repo_name}/issues'
headers = {
    'Authorization': f'token {token}'
}
issue_data = {
    'title': 'New Issue',
    'body': 'This is a test issue created through the GitHub API.'
}

response = requests.post(url, json=issue_data, headers=headers)

if response.status_code == 201:
    print('Issue created successfully!')
else:
    print(f'Failed to create issue: {response.status_code}')
