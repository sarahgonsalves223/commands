# github-commands
Follow along in this document to see the exact commands and URLs you need to use in this workshop. You can copy and paste commands you see `in gray` into the terminal or URLS into the browser. 

## Set-up: installing and configuring git (steps 0.1 through 0.5)
### Step 0.1: Registering a GitHub account
If you already have a GitHub account you'd like to use, log in to that account.
Otherwise, register a GitHub account at https://github.com/.

At the end of registration, it'll ask you to set up a new repo. You can stop there without setting one up yet.

Tip: If you're creating an account and don’t have a username in mind, use `gitisawesome` + a number.

![PACSPull Plugin](/images/set-up/github-join.png)



### Step 0.2: Opening a terminal

The terminal allows you to interact with programs on your computer in a precise and powerful way. We will use it for everything in this workshop.

![PACSPull Plugin](/images/set-up/cli-fun.png)

#### Linux
Use ctrl + alt + T to open a terminal or search for it in Apps.

#### MacOS
Go to Applications → Utilities → Terminal to open a terminal.

#### Windows
Use Windows + R to open “Run” box and type “cmd” to open a terminal.


### Step 0.3 Checking git version
On all operating systems, enter the following command in the terminal:  
`git --version`  

After you enter the above command, you should see something like (although the version number may differ):  
`git version 2.20.1`  

If you see this, it means git is installed and you can skip Step 0.4.  
If you see nothing, git is not installed and you should follow the instructions in Step 0.4.

### Step 0.4 Installing git (if not already installed)
#### Linux
```
sudo apt-get update
sudo apt-get install git
```

#### MacOS
If you have homebrew installed, you can issue:  
`$ brew install git`

Otherwise, you can either [install homebrew](https://brew.sh/) with   
```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```   
before entering the above command or you can download git with the [Git for Mac Installer](https://sourceforge.net/projects/git-osx-installer/files/).

#### Windows
Use the [Git for Windows installer](https://gitforwindows.org/).


### Step 0.5 Configure git (if not already configured)
Configure git with your name and email. The name can be fake, but the email must match your GitHub account! GitHub uses this for authentication.

On all operating systems, issue this command to check your current git configuration:  
`$ git config --list`  

If the command above doesn't show your name and email, you will need to configure git. To do so, issue the following (make sure to use your real email that was used to create your GitHub account):
```
$ git config --global user.name "Jane Doe"
$ git config --global user.email "jane@l337.com"

```

## Creating a repo
### Step 1.3 Cloning the repo locally
Tip: Right click on the terminal to paste the git URL. In most cases, you can’t use `Ctrl+V` in the terminal.  

#### MacOS and Linux
```
$ cd ~ && mkdir Repos && cd Repos
$ git clone https://github.com/github-fun/github-appendix.git && cd github-appendix
```

#### Windows
```
> cd C:\Users\gituser && mkdir Repos && cd Repos
> git clone https://github.com/github-fun/github-appendix.git && cd github-appendix
```


## Making changes and pushing to remote
### Step 2.0 Creating a file
Create a new file called "question.txt" in the root of your new repo directory and use a text editor to write a question in that file.
Some example text editors are listed below, but feel free to do this in whichever way is easiest for you, including graphical navigation or MS Word. If you use Word, make sure to save the file with a ".txt" extension.

#### Linux: common text editors include nano, gedit, vim, emacs
`$ touch question.txt && gedit question.txt`

#### Windows: common text editor is notepad
`> touch question.txt`

Use `git status` to check the status of your new file.

### Step 2.1 Tracking the file with git
`git add question.txt`  
 Use `git status` to check the status of your file again. What is different?
 
### Step 2.2 Committing changes
`git commit -am "added question.txt file"`  
Tip: `-am ` allows you to specify a commit message. The commit message should be short and descriptive about the purpose of the commit or what you changed.

### Step 2.3 Pushing to remote
Use `git remote -v` to see which remote branches your branch is tracking.  
`git push origin master` will push the committed changes from your local machine to the GitHub repository, where others can see it or clone it.

## Working with branches
### Step 3.0 Creating a new branch
Use `git branch` to check which branch you are on. It should say `master`.  
Then enter `git checkout -b my-new-branch` to create a new branch. This will be an exact copy of the branch you were on when you called the command, which in this case is `master`.

### Step 3.1 Modifying the branch
Using the method from Step 2.0, create a file called `random.txt`, but leave it blank. Then edit `question.txt` to ask an additional question (Ex. "What is your favorite animal and why?").

### Step 3.2 Staging and committing changes in the branch
`git status`  
`git add random.txt`  
`git commit -am "new question, addition of random file"`  
`git status`  

### Step 3.3 Comparison
List the files in your directory while you're on `my-new-branch` with `ls`. What do you see?
To list your branches, use `git branch`.
To switch between branches, use `git checkout <branch>`, ex. `git checkout master`.
List the files in your same directory now while on the `master` branch. What is different?

### Step 3.4 Merging the branch
Use `git branch` to check that you're on the `master` branch.
Then use `git merge my-new-branch` to merge the changes from `my-new-branch` into your current branch (`master`).

### Step 3.5 Push
Push your branches to remote!
