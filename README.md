# <img src="content/git.png" width=5%> Git / Version Control Refresher <img src="content/github.png" width=5%>

## Links
- [Git Documentation & Reference Guide](https://git-scm.com/docs)

## Configuration
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

## Creating & Accessing Projects

## Branching & Merging

## Updating & Sharing

## Comparing & Inspecting Changes