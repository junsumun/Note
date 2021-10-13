# Git

Add a user name and a user email locally
```bash
  git config --local user.name <first name and last name>
  git config --local user.email <email address>
```

Remove a file after pushed to a remote repository
```bash
  # From a local repository
  git rm --cache /path/to/file
  git commit -m "<commit message>"
  git push origin <branch name>
```

Delete branch
```bash
  # delete remote branch
  git push -d <remote repo> <branch name>
  
  # delete local branch
  git branch -d <branch name>
```

