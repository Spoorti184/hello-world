import requests

url = "https://api.github.com/gists"
headers = {"Authorization": "token YOUR_GITHUB_TOKEN"}

gist = {
    "description": "Example Gist",
    "public": True,
    "files": {
        "example.txt": {
            "content": "This is an example gist created using the API."
        }
    }
}

response = requests.post(url, json=gist, headers=headers)

if response.status_code == 201:
    print("Gist created successfully!")
else:
    print(f"Failed to create Gist: {response.status_code}")
