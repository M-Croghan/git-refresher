# <img src="content/git.png" width=5%> Git / Version Control Refresher <img src="content/github.png" width=5%>

## Links
- [Git Documentation & Reference Guide](https://git-scm.com/docs)
- [Learn Git Branching](https://learngitbranching.js.org/)

## <span style="color: yellow;">Configuration</span>
While using a GUI like [GitKraken](https://gitkraken.com) can make things easier and help in visualizing workflows, comfort on the command line is extremely important.

```$ git config``` : allows one to configure options for a local repository or the global functionality of git itself.
* <span style="color: red;">.git/config</span> : specific to each local repository maintains specific configurations to that specific repo.
* <span style="color: red;">~/.gitconfig</span> : is the file containing the configuration of git _globally_.
* <span style="color: orange;">Aliases</span> can be set-up within these files as well:

    <img src="content/alias.png">

    * This command would be invoke using  ```$ git hist```.
    * Arguements can be passed to aliases, they are appended to the end of the command.

* <span style="color: red;">.gitignore</span> files set up within a repository allow for information / files to be hidden or untracked by git.
    * Ignoring files / folders:
        * Using the filename itself: <span style="color: red;">_myfile.txt_</span>
        * Using a wildcard / pattern: <span style="color: red;">_*.log_</span> 
        * The contents of a folder: <span style="color: red;">_my-directory/_</span>

## <span style="color: yellow;">Creating & Accessing Projects</span>
Repositories can be set-up in a few ways:
1. On the creation of a new directory
    * ```$ git init <directory_name>```
2. Initializing a repository while in an existing directory
    * ```$ git init```
3. Cloning an existing repository
    * ```$ git clone <github.com/link>```

It is important to be mindful that initializing a repository only need occur once in the main / root directory of a project. Things can get messy if sub-directories are also initlized.

## <span style="color: yellow;">Comparing & Inspecting Changes</span>
* ```$ git status```
* ```$ git diff```
* ```$ git log```


## <span style="color: yellow;">Adding & Commiting</span>
Git as a version control environment can be thought of as 4 distinct areas:

<img src="content/repo.png" width=60%>

The ```working directory``` can be thought of as the region where change takes place. Any work performed here must deliberately added / tracked in order to save its state. The ``` staging area``` are where these changes are prepared to be saved. The staging area can be viewed as a holding location for where the changes we have made are acknowledged as what we would like to commit. Upon making this commit, these changes are recorded as a snapshot in the project's timeline of the ```local repository```. These changes are represented by a commit hash and a message we provide to illustrate what we accomplished.

* ```$ git add <filename>``` - adds file(s) to the staging area.
* ```$ git add .``` - adds all changes to the staging area.
* ```$ git commit -m "message"``` - commits staged changes to the local repository.
    * Commiting without the use of the ```-m``` flag and a message will open the text editor (if configured) to allow for a more detailed / longer commit message.
* ```$ git commit -am "message"``` - adds & commits inline.

The fourth area of the version control environment is the ```remote repository``` (i.e. GitHub). This external repository allows for us to back-up our projects, share our work, and collaborate with others.

## <span style="color: yellow;">Stashing</span>
Sometimes it may be necessary to switch branches BEFORE the current work in the working directory is ready to be staged and committed. In some cases, changing a branch won't cause any significant issue and the changes will simply follow you. Other times a conflict will prevent you from changing branch and require you to either commit or ***stash*** your work.

```Stashing``` is a way to save your work on a branch without committing. The stash operates similar to a stack data structure where what is saved is pushed onto and can be poped off of the stack.

* ```$ git stash``` or ```$ git stash save``` - saves all changes (both staged & unstaged).
* ```$ git stash pop``` - reapplies the changes wherever you are AND remove those changes from the stash.
* ```$ git stash apply``` - applies the changes wherever you are WITHOUT removing those changes from the stash.
* ```$ git stash list``` - lists the changes in the stack, labeled to differentiate between changes: ***Stash@{1}, Stash@{2}***
    * Pop & Apply can be appended with the stash ID to apply the specific item in the stash
* ```$ git stash drop``` - removes the top most item in the stash.
    * Can also drop by using the Stash@{id}.
* ```$ git stash clear``` -  remove all items from the stash.

## <span style="color: yellow;">Branching & Merging</span>
It may be appropriate to work directly on the main / master branch of a project if you are the only one contributing to it. However, as the scale of a project and the number of contributors working on it grows, it becomes increasingly important to pay attention to branching and the overall workflow.

***Branching*** allows for isolating segments of work while preserving the codebase. This allows for the freedom to experiment and try new things without the fear of destroying the time and effort already put into a project.

* Creating branches:
    * ```$ git branch <branch_name>``` - only creates the branch, doesn't switch to it.
    * ```$ git checkout -b <branch_name>``` - creates branch and switches to it.
    * ```$ git switch -c <branch_name>``` - newer way to create branch and switch to it.
        * Came about as _checkout_ is seen as being overloaded considering its other functionality.
* Viewing existing branchs in a repository:
    * ```$ git branch``` - shows local branches.
        * Using the ```-a``` flag will show remote branches as well.
* Changing branches:
    * ```$ git switch <branch_name>```
    * ```$ git checkout <branch_name>```

***Merging*** allows for work from one branch to be incorperated (_merged_) into another branch. To do so, one must navigate to the branch in which they wish to add changes to and then call for the merge of the other branch. For example, navigating to the _main_ branch which contains our functioning application and then merging a feature branch which contains the code of some addition we wish to include. ```$ git merge <branch_name>```

Merges can confound the commit history and the approach to merging can vary (i.e. Fast-forward merges, merge commits, etc.).

## <span style="color: yellow;">Checkout & HEAD</span>
An important concept within git is that of the ***HEAD***. The HEAD can be thought of a bit like a bookmark which denotes on which branch or commit the repo is currently open to.

```Checkout``` allows one the ability to travel through the commit history to a specific point in time. Doing so results in a ***DETACHED HEAD*** and can provide for the inspection of a given commit and allow to branch off from it.

* ```$ git checkout <commit hash>``` - points to the specified commit, resulting in a Detached HEAD
* ```$ git checkout HEAD~#``` - The # represents a number of commits PRIOR to the HEAD location (i.e. HEAD~2 will go back 2 commits).
* ```$ git checkout HEAD <filename>``` or ```$ git checkout -- <filename>``` - can be used to clear changes since the most current commit

## <span style="color: yellow;">Restore, Revert, & Reset</span>

* ```$ git restore <filename>``` - restores the file to the state of the last commit BEFORE any changes were made.
* ```$ git restore --staged <filename>``` - unstages any work waiting in staging area waiting to be commited.

* ```$ git reset <commit hash>``` - clears the commits up to the specified commit but keeps the changes.
* ```$ git reset --hard <commit hash>``` - clears the commits AND the working directory.



## <span style="color: yellow;">Remote Tracking & GitHub</span>
* ```$ git fetch```: Retrieves remote changes & brings them down to the local repository.
    * Gets the information WITHOUT merging changes to current existing work.
* ```$ git pull```: Grab the changes from the remote and pull them into the local repository.
    * Merges with the existing work locally.
* ```$ git push```: Pushes the work local to remote.

The remote tracking branch has a direct relationship to a remote branch whereby ```git push``` / ```git pull``` work without additional arguements.

Merge conflicts are always a possibility when attempting to retrieve or incorperate changes. A good rule of thumb is to pull down any changes that may have occured before pushing to the remote. An example of this would be in the case of contributing to an open source project, where the existing project is _forked_ to your own GitHub account, cloning that existing project to your local machine, and pushing any changes to that forked repository and making pull requests from there. One can set the upstream to the actual live project to retrieve changes.

## <span style="color: yellow;">Rebasing</span>
* An alternative to _merge_ & clean up tool.
    * Helps combine changes from 2 branches.
    * Rewrite history (essentially clears the merge commits)
* Appends the commits / changes to the end of a specified branch

<img src="content/rb.png">

## <span style="color: yellow;">Tags</span>
Tags act as a pointer to a specific commit. they are commonly used to mark a release version and exist in two distinct forms:
* ***Lightweight:*** Consisting of just a name / title.
* ***Annotated:*** Contains additional metadata.

Tags & semantic versioning often go hand and hand:

<img src="content/semver.png">

* ```$ git tag```: List all tags in the current repository.
* ```$ git checkout <tag>```: Result in detached HEAD just like using a commit hash.
* ```$ git diff <tag1> <tag2>```: Check changes between 2 tags.
* ```$ git tag <tag name>```: Creates a lightweight tag on whatever HEAD is referencing.
* ```$ git tag -a <tag name>```: Creates an annotated tag on whatever HEAD is referencing.
    * ```$ git show <tag name>```: Show metadata on a tag.
* ```$ git tag <tag name> <commit>```: Tag a specific commit.
* ```$ git tag -f <tag name> <hash>```: Moves a tag (Note! - tags must be unique!).
* ```$ git tag -d <tag name>```: Delete specified tag.