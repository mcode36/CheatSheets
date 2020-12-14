# Create a local copy from github:
git clone https://github.com/mcode36/XXXXX.git

# Add files (to staging area) for commit
git add <file>
or, git add <folder>

# Commit changes to head (but not yet to the remote repository):
git commit -m "Commit message"

# Push local commit to remote repository
git push


# Continuing authentication with Git repositories

$ git config credential.helper store
$ git config --global credential.helper 'cache --timeout 86400'
$ git push <repo_url>
