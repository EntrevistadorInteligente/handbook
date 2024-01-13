# clone all repos

Bash

```bash
repos=$(curl -s https://api.github.com/orgs/EntrevistadorInteligente/repos\?per_page\=100 | jq -r '.[].clone_url')

# Clone all repos
for repo in $repos; do
    git clone $repo
done
```

PowerShell

```powershell
$repos = (Invoke-WebRequest -Uri "https://api.github.com/orgs/EntrevistadorInteligente/repos?per_page=100" | ConvertFrom-Json).clone_url

# Clone all repos
foreach ($repo in $repos) {
    git clone $repo
}
```
