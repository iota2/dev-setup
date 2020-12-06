# iota2

> Making Imaginations, Real

<i2.iotasquare@gmail.com>

```
 ██╗ ██████╗ ████████╗ █████╗ ██████╗
 ██║██╔═══██╗╚══██╔══╝██╔══██╗╚════██╗
 ██║██║   ██║   ██║   ███████║ █████╔╝
 ██║██║   ██║   ██║   ██╔══██║██╔═══╝
 ██║╚██████╔╝   ██║   ██║  ██║███████╗
 ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝
```

[![BSD licensed](https://img.shields.io/badge/license-GPL3-blue.svg)](https://raw.githubusercontent.com/iota2/dev-setup/master/LICENSE)


# Git Workflow : Fork-and-Branch
Basics of the "fork and branch" workflow:
- [x] Fork a GitHub repository.
- [x] Clone the forked repository to local system.
- [x] Add a Git remote for the original repository.
- [x] Create a feature branch to make the changes.
- [x] Make the changes to the new branch.
- [x] Commit the changes to the branch.
- [x] Push the branch to GitHub.
- [x] Open a pull request from the new branch to the original repository.
- [x] Clean up after pull request is merged.


## Forking a GitHub Repository
First we need to fork the repository that we want to update.
Forking a repository is really straightforward:
1. Login to GitHub account.
2. Find the GitHub repository with which you want to work on.
3. Click the `Fork` button on the upper right-hand corner of the repository's
   page.
> Forking it is basically making a copy of the repository,
> but with a link back to the original.


## Making a Local Clone
Even though using fork we have a copy of the original repository in our GitHub
account, we don't yet have a way to make changes to our copy of the repository.
As we have no way of making changes to the forked repository directly from the
GitHub account. We need to make a local clone of the repo into our machine.
We can get the HTTPS link of our repository `<link to forked repository>` from
GitHub and use that on our machine to create the clone.
```
git clone <link to forked repository>
````
> When cloned a repository, Git will copy down the repository,
> including both contents and commit history, to the system.
> Git will also add a Git remote called `origin` that points back to the forked
> repository in the GitHub.


## Adding a Remote
In order to use the "fork and branch" workflow,
we need to add a Git remote pointing back to the original repository (the one
we forked on GitHub). We can name  this Git remote anything we want; here we'll
call it using the term `upstream`.
```
git remote add upstream <link to original repository>
```
> After cloning Git automatically adds a Git remote named origin of the Git
repository on the system, > and this will allow us to push changes back up to
the forked repository in our GitHub account using `git commit` and `git push`


## Working in a Branch
So far, we forked a project repository, cloned it down to our local system,
and added a Git remote to our clone that points to the original project repo on
GitHub. Now we're ready to start making changes to our local Git repository.
In order to make changes, we need to start with creating a new branch.

The basic steps include:
* Create and checkout a feature branch.
```
git checkout -b <feature branch>
```
* Make changes to the files.
* Commit your changes to the branch.
```
git add <files to add>
git commit -m "commit message"
```
> Because of the way in which Git works,
> it's incredibly fast and easy for developers to create multiple branches.


## Pushing Changes to GitHub
Till now we made desired changes and committed them to our local repository.
The next step is to push those changes back up to GitHub:
```
git push origin <feature branch>
```
> The generic form of this command is `git push <remote> <branch>`.
> Here, we're pushing changes in the feature branch to the origin remote.


## Opening a Pull Request
GitHub makes this part incredibly easy. Once we push a new branch up to our
repository, GitHub will prompt us to create a pull request. The maintainers of
the original project can use this pull request to pull our changes across to
their repository and, if they approve of the changes, those changes cna be
merged them into the main repository.


## Cleaning up After a Merged Pull Request
If the maintainers accept the changes and merge them into the main repository,
then there is a little bit of clean-up for us to do. First, we should update
our local clone by using:
```
git pull upstream master
```
This pulls the changes from the original repository's (indicated by `upstream`)
master branch (indicated by `master` in that command) to our local cloned repo.
One of the commits in the commit history will be the commit that merged our
feature branch, so after we do `git pull` our local repository's `master`
branch will have our feature branch's changes committed.
This means we can delete the feature branch (because the changes are already
in the `master branch`):
```
git branch -d <feature branch>
```
Then we can update the `master` branch in our forked repository:
```
git push origin master
```
And push the deletion of the feature branch to your GitHub repository:
```
git push --delete origin <feature branch>
```


## Keeping Your Fork in Sync
The forked repository can't automatically stay in sync with the original repo;
we need to take care of this ourself. To keep our fork in sync with original
repository, use these commands:
```
git pull upstream master
git push origin master
```
This pulls the changes from the original repository (the one pointed to by the
`upstream` Git remote) and pushes them to our forked repository (the one
pointed to by the `origin remote`).



# License
> `GNU GPU v3` <br>
> This program is free software; you can redistribute it and/or
> modify it under the terms of the GNU General Public License
> as published by the Free Software Foundation; either version 3
> of the License, or (at your option) any later version.
> This program is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.

**Free Software, Hell Yeah!**

