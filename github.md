# Continuing authentication with Git repositories

$ git config credential.helper store
$ git config --global credential.helper 'cache --timeout 86400'
$ git push <repo_url>
