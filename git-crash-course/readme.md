## Git hidden folder

There is a hidden folder called `.git` which tells you that our project is a git repo.

If we wanted to create a git repo in a new project we create the folder and then initalize that repo using `git init`

```sh
mkdir /workspaces/tmp/new-project
cd /workspaces/tmp/new-project
git init
touch Readme.md
code Readme.md
git status
git add Readme.md
# make changes to readme.md
git commit -a -m "add readme file"
```

## Commits

When we want to commit code we can write git commit which will open up the commit edit message in the editor of choice.

```sh
git commit
```

Set the global editor
```
git config --global core.editor
```

## Clone

We can clone three ways:
* HTTPS
* SSH
* GitHub CLI

Since we are using GitHub Codespaces we will create a temporary directory in our workspace.

```sh
mkdir /workspace/tmp
cd /workspace/tmp
```

### HTTPS

```sh
git clone https://github.com/joshua-experimental/GitHub-Examples.git
cd GitHub-Examples
```

### SSH

```sh
git clone https://github.com/joshua-experimental/GitHub-Examples.git
cd GitHub-Examples
```

We will need to create out own SSH rsa key pair

```sh
ssh-keygen -t -rsa
```

We can test our connection here:

```sh
ssh -T git@github.com
```

For WSL users and if you create a non default key you might need to add it

```sh
eval `ssh-agent`
ssh-add /home/.../.ssh/...id_rsa
```

### GitHub CLI

Install the CLI

e.g. Linux (ubuntu)
```sh
sudo apt update
sudo apt install gh

gh auth login
gh clone
```

## Branches

## Remotes

## Stashing

```sh
git stash list
git stash
git stash save my-name
git stash pop
```

## Merging

## Add

When we want to stage changes that will be included in the commit,
we can use the . to add all possible files.

```sh
git add Readme.md
git add .
```

## Reset

Reset allows you to move staged changes to be unstaged.
This is useful when you want to revert all files not to be commited

```sh
git add .
git reset
```

## Status

Git status show you what files will or will not be commited

```sh
git status
```

## Git config file

The git config file is what stores your global configurations for
git such as email, name, editor and more.

Showing the contents of our .gitconfig file
```sh
git config --list
```

When you first install git on a machine you are supposed to set up
your name and email.

```sh
git config --global user.name "John Doe"
git config --global user.email "johndoe@example.com"
```

## Git log

`git log` will show recent git commits to the git tree

## Push

When we want to push a repo to our remote origin

```sh
git push
```