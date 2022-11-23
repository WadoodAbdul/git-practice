# git-practice
Playground for learning git functionalities.


## Deleting files out of git history

Using git revert creates a new commit of your previous desired state. However, sensitive information would still exist in the git history. 
To remove files from git history completely,

Install the git-filter-repo functionality

```
sudo apt install git-filter-repo
```

In path, specify the path of the file you want to remove from git history
```
git filter-repo --invert-paths --path sensitive_data.txt --force
```

Add the path to .gitignore so that it doesn't get commited again

```
echo "sensitive_data.txt" >> .gitignore
git add .gitignore
git commit -m "adding sensitive data to git ignore"
```

add the link to your git repo and push the changes
```
git remote add origin <link-to-git-repo>
git push origin --force --all
```
