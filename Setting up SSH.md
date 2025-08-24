# Authenticate Via SSH

### Windows - Open Git bash

- `ssh-keygen -t ed25519 -C "your_email@example.com"` : Generate SSH key

- `eval "$(ssh-agent -s)"` : Start ssh-agent in the background

- `ssh-add ~/.ssh/id_ed25519` : Add key

- `cat ~/.ssh/id_ed25519.pub` : Copy your public key

## Add the key to GitHub

- Go to GitHub → Settings → SSH and GPG keys
- Click New SSH key
- Paste your copied key into the field.
- Give it a title like “My Laptop” & Save.

- `ssh -T git@github.com` : Test the Connection

### O/P

Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.

### Use SSH for GitHub repos

- `git clone git@github.com:USERNAME/REPO.git`
- `git remote set-url origin git@github.com:USERNAME/REPO.git` : if already cloned via HTTPS, switch it
