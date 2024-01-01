# Push Your Code to GitHub:

## 1. Stage the Changes:

Use git add to stage the changes for commit. You can add all changes with:
```
git add . 
```

or specific files with:

```
git add filename
```
## 2. Commit the Changes with a Comment:
When you commit these changes, you add a comment that describes what you did. 

This is done using the -m flag with the git commit command. 

```
git commit -m "Your detailed commit message here"
```

Here, "Your detailed commit message here" is your comment. 

It's best practice to make this message descriptive, so it's clear what changes were made when looking back at the commit history.

## 3. Push the Commits to the Remote Repository:

Finally, you use git push to send your commits to the remote repository. If it's your first time pushing to this repository, you use:

```
git push -u origin master
```

In this case, origin is the default name Git gives to the remote you cloned from, and master is the branch you're pushing to. 

The -u flag sets the upstream for your branch, so in subsequent pushes you can just use git push.
