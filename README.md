# Git Branching

Branching allows us to collaborate on projects and help keep our code base stable.

## Common Tasks

- `git branch BRANCH-NAME` - Create a branch with the name of **BRANCH-NAME**
- `git branch` - Display the branch you're currently on
- `git branch -a` - Show all available branches that have been created
- `git checkout BRANCH-NAME` - Switch to the branch with name **BRANCH-NAME**
- `git merge --no-ff BRANCH-NAME` - Merge **BRANCH-NAME** into the current branch (use `git branch` to determine the current branch)
- `git pull origin BRANCH-NAME` - Pull down changes from the remote
- `git checkout -b BRANCH-NAME` - Combines branch creation with checkout in one handy command


## Common Branches

### master

The **master** branch generally contains fully tested code that can be deployed. This is generally used as the starting point for individual projects. The **master** branch is what you have been working with to date, it's created by default.

### feature-NAME

When working on a task, you will want to create a branch for the feature that you are working on. The feature will be created using the branch you're currently on as a starting point. Let's assume we're on the master branch and creating a feature of **feature-login-html**.

**Create the feature-login-html branch**

```
git branch feature-login-html
```


```
⍟ master
|
|\
| o feature-login-html
```

**Switch to the feature-login-html branch**

```
git checkout feature-login-html
```

```
o master
|
|\
| ⍟ feature-login-html
```

**Make some changes and commit them**

Update the code in your files.

```
git add .
git commit -m "COMMIT MESSAGE"
git push origin feature-login-html
```

```
o master
|
|\
| o feature-login-html
| |
| ⍟ commit "COMMIT MESSAGE" (still on feature-login-html)
```

> At this point you can continue making commits.

**Merge your changes back into master (happy path)**

Go back to master

```
git checkout master
```

```
⍟ master
|
|\
| o feature-login-html
| |
| o commit "COMMIT MESSAGE" (still on feature-login-html)
```

Merge from feature-login-html into master

```
git merge --no-ff feature-login-html
```

```
o master
|
|\
| o feature-login-html
| |
| o commit "COMMIT MESSAGE" (still on feature-login-html)
|/
⍟ <- We are now here
```

![Git Branching Diagram](images/git-branching-diagram.jpg)

### develop

The **develop** branch gives us a safety net when working with teams. This is generally used as the starting point for group projects but for now we'll stick with **master**.

## VIM

To exit VIM, press `shift` and `:`, type `wq` and press `enter`.

You can configure git to use a different Terminal text editor if you get tired of this arcane editor.

`$ git config --global core.editor your-editor-here`

