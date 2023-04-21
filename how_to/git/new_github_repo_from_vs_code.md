# How To Add a New Project Folder to Git and GitHub Using VS Code

{This is a temporary how-to. It combines what should probably be two guides: starting a git repo, and creating the GitHub repo with VS Code}

This guide only assumes that you have git and VS Code already installed, 
and have a GitHub account. 
It also assumes you can run basic commands from your terminal.

You can add plug-ins to VS code, 
or use other IDEs with version control tools,
to make this process even easier.
The workflow described below will work without any extra add-ons or configuration.

This guide also assumes you have not set up GitHub authentication using an ssh key. In the longer term, this is something that you want to do to make GitHub integration easier.

Most of the following steps can be done using VS Code's interface instead of the command line. For this guide, the command line is being used for all but GitHub authentication and the "create repository on GitHub and push" step, which VS Code does for you very nicely.

## 1. Check that your project's directory name matches the name you want for your GitHub repository 

How do you want yourself or others to see your repo listed?

## 2. From the command line, navigate to your project folder and check that you are inside it.

For example, if your folder named "my-new-repo" is found at `~/Projects/GitHub/my-new-repo`, and you use a bash terminal, you would run:
```bash
$ cd ~/Projects/GitHub/my-new-repo
$ pwd
/Projects/GitHub/my-new-repo
```

## 2. Initialize your git repository

From the command line 
(either your usual system terminal, or using VS Code's built-in terminal),
```bash
$ git init
Initialized empty Git repository in /Projects/GitHub/my-new-repo/.git/
```

## 3. Add files and folders to git version control

You can either add the entire contents of the folder at once using:
```bash
$ git add .
```
or add individual files and folders if you want more control:
```bash
$ git add {name_of_file}
```
where you would substitute `{name_of_file}` with the actual name of the file or folder you are adding. Advanced users could also create their .gitignore file at this point and add to it the names of locations that you *don't* want added to git version control.

To check what files are staged for commit, use:
```
$ git status
```

## 4. Make your first commit

From the command line, enter:

```bash
$ git commit -m "Initial commit"
``` 
The `-m` option allows you to enter the commit message directly. If this is omitted, git will pop open your default text editor and have you enter the message there.

## 5. In VS Code, use Accounts to sign in to GitHub

Look for the "person in a circle" icon near the bottom of the left sidebar in VS Code.
Follow the prompts to authenticate with GitHub 
(see [this page](https://code.visualstudio.com/docs/sourcecontrol/github) for more detail).

## 6. Publish to a new repository on GitHub

Press Ctrl + shift + P to open the command pallete in VS Code.
In the command search box, start typing "Publish to GitHub" until the option to select it appears,
then select it.
Choose whether you want a public or private repository.
VS Code will then push your commit to GitHub and also create the new repository.

Log in to GitHub and check that your repository has been created. Now is a good time to create a README, LICENSE and .gitignore, if you haven't already. The GitHub web interface makes adding these to your repository easy.

