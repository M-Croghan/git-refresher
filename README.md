# <img src="content/git.png" width=5%> Git / Version Control Refresher <img src="content/github.png" width=5%>

## Links
- [Git Documentation & Reference Guide](https://git-scm.com/docs)

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
<<<<<<< HEAD

It is important to be mindful that initializing a repository only need occur once in the main / root directory of a project. Things can get messy if sub-directories are also initlized.
## <span style="color: yellow;">Branching & Merging</span>

## <span style="color: yellow;">Updating & Sharing</span>

=======
## <span style="color: yellow;">Branching & Merging</span>

## <span style="color: yellow;">Updating & Sharing</span>

>>>>>>> a00911bf6c2e48fa81ec0b9bb1397ed92a043ce7
## <span style="color: yellow;">Comparing & Inspecting Changes</span>