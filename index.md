# Advanced Git and Github Documentation
*****

## Git Basics
### What is Git?
Git is an open source Version Control System (VCS), often used fir tracking changes in code allowing mutliple developers to work together on a project.
### Why use Git? What problem does it solve?
Like mentioned, using Git allows you to work collaboratively and track changes made by multiple people with the reasoning of why. Using the branching options also allows you to test code in a safe environement, and once ready to implement, is as easy as a button click to put into production. This saves the hassle of possible losing your entire app due to a mess up in the code. 
### What is the difference between Git and Github?
Git is on your local system rather than in the cloud like GitHub. On top of this, GitHub serves mostly as a hosting service for your Git Repositories and allows you to share and save them on another spot rather than your machine. You are not required to use one with the other, however their integration with eachother makes it an easy choice to host projects and repositories. 

## Git rebase
### What is Git rebase?
A git rebase is when you move the base of your branch to a new set of commits. For example, you branched on commit B and started working on a feature. Time has moved on and you are now on commit D. Rather than merging all of your commits of the feature to the master, a rebase takes your feature branch and resets it to the master commit, after all of the commits are reapplied on top of the feature branch, still ahead of the master but on a linear line. 
### What are some advantages and disadvantages of Git rebase? (At least 2 of each)
Some advantages of Git rebase are:</br>
- Keeping a clean history of your project rather than having a million branches on each commit to test features. </br>
- Rather than merging with the main branch and getting a commit message to see every thing that has changed, doing a rebase tells git to add your changes on top of everyone elses so you do not have to go through the notifications each time. 

Some disadvantages Git rebase are:</br>
- Git rebase rewrites the history of the project, so if you are working with multiple people or need to track all commits merged you might run into issues if not everyone is on the same page.</br>
- You can run into a chain of broken commits if you were to rebase back to the master with a removed dependancy.
### When shouldn't you use Git rebase? Why?
You should never rebase commits that have been pushed or shared with others on your team. Doing this could completely break your code as you are saying you want to use a new base for your code. That may be good but if you change the base of a commit that is now pushed to others and they are working on it there will be discrepancies and break the code.


#### Create a new repo and demonstrate your knowledge of the following items with screenshots:
#### A rebase merge
#### An interactive rebase merge
#### When you shouldn't rebase with a remote repo.


## Git reset, checkout, and revert
### What is Git reset?
Git reset allows you to undo or reset changes made in Git. Basically resets the tip of the current branch to a prior commit.
### What is the difference between hard, mixed and soft?
- `git reset --mixed` - This is the default if you don't specify. This updates the branch to the commit you want to backtrack to and unstages any changes made.</br>
- `git reset --soft` - This will do the update but makes no other changes.</br>
- `git reset --hard` - This will do the update as well as unstage any changes made, however this also deletes any changes that were made in the working directory that hadn't yet been staged and committed.</br>
### What is Git checkout?
Git checkout allows you to switch between branches in a repo and update the files in your current directory to match the version in the branch. 
### What is Git revert?
Revert is similar to reset in that you can make changes on a project, however rather than resetting back to the specified commit and deleting the progress, a `git revert` will create a new commit with the specified changes. 
### In what ways are these commands the same and what ways are they different?
As an example, you have Commits A,B,C,D. `git reset` would leave your tree looking like: A,B if you reset to B. `git revert` would look like A,B,C,D,E where E looks like B but is a new commit.</br>
They are the same as it gives you options to more or less undo what you have done so far or go back to a previous commit version. They are different however as reverting saves all of the previous commits up to that point whereas reset will reset to a specified commit.
### When would you use reset, checkout, or revert? Why?
All of these have their own use case scenarios in which it would be best to use them:</br>
- `git reset` - This wouild most beneficial on a private repo where you are in control of what is happening and are not worried about the commit history as it overrides what is currently there. </br>
- `git checkout` - This would be used when you are checking out old commits as a way to update to a specific point in the projects history. You can even go back to specific commits and look at older versions of your project without reference to the current `HEAD`. Heckout can also be used similarly to reset as you can discard unstaged changes.</br>
- `git revert` - Revert should be used when making or reverting changes on a public branch as it is a safe way to make changes without overwriting or losing any commits. This is a good way to undo committed changes as they have been staged already and there is no fear of totally breaking a project.


#### Create a new repo and demonstrate your knowledge of the following items with screenshots:
#### a Git reset
#### a Git checkout
#### a commit
#### a Git revert


## Submodules
### What are Git submodules?
Git submodules are like repositories inside another repository. A main repository can point to a specific commit in a submodule and access what is there.
### When would you use a submodule?
If you are building a full scale app and have some components that you want to integrate, such as a billing system, you could put that seperate system into a submodule to keep the main history of the app looking cleaner.
### What are the advantages and disadvantages of Git submodules?
- Some advantages are that you can point multiple repositories to a submodule and use them across many projects. </br>
- One of the biggest disadvantages is that they are static, meaning any changes to the submodule will require you to repoint to the commit that you want to use. On top of this, there is no real easy way to merge the submodule into the main repo that you are using.
