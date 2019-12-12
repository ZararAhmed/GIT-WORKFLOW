# Git Workflow

## 1. To start a project
1. Clone the repository
    ```zsh
    $ git clone <remote-url>
    ```

## 2. To do new feature/modify/hotfix
1. Checkout into `dev` branch
    ```zsh
    $ git checkout dev
    ```
1. Pull the latest changes
    ```zsh
    $ git pull origin dev
    ```
1. Create a `<branch-name>` branch from `dev` branch
    ```zsh
    $ git checkout -b <branch-name> dev
    # branch-name must contain add/, modify/ or hotfix/ 
    # e.g. add/feature-name for new feature or hotfix/bug-name for hotfix

    # push new-branch to remote repository
    $ git push -u origin <branch-name>
    ```
1. Make changes and commit each logical change with descriptive message
## 3. To commit the changes
1. Inside your working branch
    ```zsh
    # check the changed files
    $ git status
    # make sure only files are modified which you intend to

    # stage the changes
    $ git add file1 file2 file3 ...

    # to stage all changes at once 
    $ git add .
    # make sure any file you didn't change shouldn't be appeared in red in git status

    # commit the changes
    $ git commit -m "[Add/Modify/Hotfix] <MESSAGE>"
    # Message must be descriptive and relevent to the changes in the code
    ```
## 4. To submit merge request
1. Checkout into `dev` branch and pull any new changes
    ```zsh
    $ git checkout dev
    $ git pull origin dev
    ```
1. Checkout into your working branch and merge with dev
    ```zsh
    $ git checkout <branch-name>
    $ git merge dev
    ```
1. Resolve the conflict if any and commit the changes [as discussed above](#3-to-commit-the-changes)
1. Push the branch and create the merge request
    ```zsh
    $ git push -u origin <branch-name>
    ```
## 5. To delete a block of code (Dead Code Removal)
1. Comment the block of code and make your required changes
1. Commit the changes describing the changes you made [as discussed above](#3-to-commit-the-changes)
1. Delete the commented code with this message format 
    ```zsh
    $ git commit -m "[DCR] <Describe the code block functionality>"
    ```
