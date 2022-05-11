# What is a version control system
Version control, also known as source control, is the practice of tracking and managing changes to software code. 
Version control systems are software tools that help software teams manage changes to source code over time.

# Advantages of version control system
- Changes can be tracked easily
- Provides backup
# Types of Version control systems
1. Central Version Control System, Ex: svn
2. Distributed/Decentralized Version Control System, Ex: Git, Bitbucket

# What is a Distributed version control system
...

# What is Git ?
Git is a source code management (SCM) tool which handles small as well as large projects with efficiency. It is basically used to store our repositories in remote server such as GitHub.

Git is a distributed version control system. 

## Git vs SVN
GIT | SVN
:-- | :--
Git is a Decentralized Version Control Tool | SVN is a Centralized Version Control Tool 
Git contains the local repo as well as the full history of the whole project on all the developers machines, so if there is a server outage , you can easily do recovery from your team mates local git | SVN relies only on the central server to store
Commits can be done offline too | Commits can be done only online

# What language is used in Git
Git is written in C language, and since its written in C language its very fast and reduces the overhead of runtimes.

# What is subGit ?
SubGit is a tool for migrating SVN to Git. It creates a writable Git mirror of a local or remote Subversion repository and uses both Subversion and Git if you like.

# Explain the difference between git pull and git fetch?
Git pull merges your local repository with remote repository.
Git fetch lists the differences between your local repo and remote repo.

Git pull = git fetch + git merge

# How do we know in Git if a branch has already been merged into master? 
`git branch –merged` 
The above command lists the branches that have been merged into the current branch. 
`git branch –no-merged` 
this command lists the branches that have not been merged.

# What is ‘Staging Area’ or ‘Index’ in GIT? 
Before committing a file, it must be formatted and reviewed in an intermediate area known as ‘Staging Area’ or ‘Indexing Area’. 
`git add <file_name>`

# What is Git Stash? 
Let’s say you’ve been working on part of your project, things are in a messy state and you want to switch branches for some time to work on something else. The problem is, you don’t want to do a commit of your half-done work just, so you can get back to this point later. The answer to this issue is Git stash. Git Stashing takes your working directory that is, your modified tracked files and staged changes and saves it on a stack of unfinished changes that you can reapply at any time.

# What is Git stash drop? 
Git `stash drop` command is basically used to remove the stashed item. It will basically remove the last added stash item by default, and it can also remove a specific item if you include it as an argument.
**example**:  
If you want to remove any particular stash item from the list of stashed items you can use the below commands: git stash list: It will display the list of stashed items as follows: stash@{0}: WIP on master: 049d080 added the index file stash@{1}: WIP on master: c265351 Revert “added files” stash@{2}: WIP on master: 13d80a5 added number to log.

# What is the function of ‘git config’? 
Git uses our username to associate commits with an identity. 
The git config command can be used to change our Git configuration, including your username. Suppose you want to give a username and email id to associate commit with an identity so that you can know who has made a commit. 
use: `git config –global user.name “Your Name”`  - This command will add your username. 
`git config –global user.email “Your E-mail Address”`  This command will add your email id.

# How can you create a repository in Git? 
To create a repository, you must create a directory for the project if it does not exist, then run command “git init”. By running this command .git directory will be created inside the project directory.

# Describe the branching strategies you have used?
**Feature branching**
This model keeps all the changes for a feature inside of a branch. When the feature branch is fully tested and validated by automated tests, the branch is then merged into master. 
**Task branching**
In this task branching model each task is implemented on its own branch with the task key included in the branch name. It is quite easy to see which code implements which task, just look for the task key in the branch name. 
**Release branching**
Once the develop branch has acquired enough features for a release, then we can clone that branch to form a Release branch. Creating this release branch starts the next release cycle, so no new features can be added after this point, only bug fixes, documentation generation, and other release-oriented tasks should go in this branch. Once it’s ready to ship, the release gets merged into master and then tagged with a version number. In addition, it should be merged back into develop branch, which may have progressed since the release was initiated earlier.

# How you will do the releases? 
There are some steps to follow. 
• Create a check list 
• Create a release branch 
• Bump the version 
• Merge release branch to master & tag it. 
• Use a Pull request to merge the release merge 
• Deploy master to Prod Environment 
• Merge back into develop & delete release branch 
• Change log generation 
• Communicating with stake holders 
• Grooming the issue tracker

# How can I modify the commit message in git? 
I have to use following command and enter the required message.  
`Git commit –amend`

# How you handle the merge conflicts in git?
Follow the steps 
1. Create Pull request 
2.Modify according to the requirement by sitting with developers
3. Commit the correct file to the branch 
4. Merge the current branch with master branch.

# How you will do tagging in git? 
We have following command to create tags in git Git tag v0.1

# What is git checkout
Switch branch or restore working files

# What is git push
Sends the changes to the remote repository

# Commit
## What is git commit
Commits the changes to the HEAD (staging area)
**commit message:** is the description of the changes performed in the code.

## How do you fix a broken commit
`git commit --amend`

# what is git add
adds the file changes to the staging area
# what is git branch
Creates a branch
# what is git fetch
Fetch the latest history from the remote server and updates the local repo
# what is git merge
Joins two or more branches together
# what is git pull
Fetch from and integrate with another repository or a local branch (git fetch + git merge)
# What is git rebase? 
Process of moving or combining a sequence of commits to a new base commit
# What is git revert? 
To revert a commit that has already been published and made public
# What is git clone? 
clones the git repository and creates a working copy in the local machine
# What is the command in git to modify the commit message? 
Use the command “amend” to modify the commit message.

# How to get specific version or previous version of a file ?
# Git init vs clone vs fork
`git init` : Initializes a new empty local repository
`git clone` : Creates a copy of the original repository from Github on local machine.
`git fork` : Creates a copy of the original repository on your github account.