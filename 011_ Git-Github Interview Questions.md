
### Basic Git Interview Questions and Answers

1. **What is Git?**
   Git is a distributed version control system that enables developers to track changes in their code, collaborate with others, and manage project versions efficiently.

2. **What is a repository in Git?**
   A Git repository is a storage location that holds all the files, directories, and version history of a project. It allows developers to track changes, collaborate, and manage different project versions.

3. **What is the difference between Git and GitHub?**
   Git is a version control system, while GitHub is a web-based platform that provides hosting services for Git repositories. GitHub adds collaboration features like issue tracking, pull requests, and project management tools.

4. **How does Git work?**
   Git works by creating snapshots of a project's files and storing them in a repository. It tracks changes made to files, allows branching for parallel development, and facilitates merging changes back into the main branch.

5. **What is a commit in Git?**
   A commit in Git is a snapshot of the project at a specific point in time. It records changes made to files, includes a commit message, author information, and a unique identifier (SHA-1 hash).

6. **What is branching in Git?**
   Branching in Git allows developers to create separate lines of development. It enables parallel work on features, bug fixes, or experiments without affecting the main codebase until changes are ready to be merged.

7. **What is a merge in Git?**
   Merging in Git combines changes from different branches into a single branch. It integrates divergent histories, resolves conflicts, and creates a new commit to reflect the merged changes.

8. **What is a conflict in Git?**
   A conflict in Git occurs when changes made in different branches conflict with each other. Git cannot automatically resolve these conflicts, requiring manual intervention from developers to resolve them.

9. **What is a pull request?**
   A pull request is a method used to propose changes to a repository hosted on platforms like GitHub. It allows developers to review, discuss, and merge code changes from one branch to another.

10. **What is `git fetch` vs. `git pull`?**
    - `git fetch` downloads changes from a remote repository to the local repository but does not merge them.
    - `git pull` downloads changes from a remote repository and merges them into the current branch automatically.

11. **How do you revert a commit that has already been pushed?**
    To undo changes from a previous commit without losing history, use `git revert <commit_hash>`. To remove a commit entirely, use `git reset --hard HEAD^` (with caution).

12. **What is a `.gitignore` file?**
    A `.gitignore` file specifies files or directories to exclude from version control. It helps prevent unnecessary files (like build artifacts or configuration files) from being tracked by Git.

13. **How do you clone a repository?**
    Use `git clone <repository_url>` to create a local copy of a repository on your machine. This command copies the entire repository, including its history and branches.

14. **What is `git stash`?**
    `git stash` temporarily shelves changes in the working directory, allowing you to switch branches or apply changes later without committing them.

15. **How do you view the commit history?**
    Use `git log` to view the commit history of a repository. You can customize the output with options like `--oneline` for a condensed view or `--graph` for a visual representation.

16. **What is a remote in Git?**
    A Git remote is a shared repository hosted on a server or a platform like GitHub. It allows multiple developers to collaborate on a project by sharing changes and updates.

17. **How do you create a new branch?**
    - Use `git branch <branch_name>` to create a new branch based on the current branch.
    - Use `git checkout -b <branch_name>` to create a new branch and switch to it in one step.

18. **What is `git merge --squash`?**
    `git merge --squash` merges changes from a feature branch into another branch while squashing all commits into a single commit, creating a cleaner commit history.

19. **How do you resolve a merge conflict?**
    To resolve a merge conflict, edit the conflicting files, mark the conflicts as resolved with `git add`, and commit the changes using `git commit`.

20. **What is `git rebase`?**
    `git rebase` reorganizes the commit history by applying commits from one branch onto another. It helps maintain a linear history and integrates changes more seamlessly.

21. **What is the difference between `git merge` and `git rebase`?**
    - `git merge` integrates changes from one branch into another with a merge commit, preserving the branch history.
    - `git rebase` applies changes from one branch onto another by re-writing commit history, creating a linear history without merge commits.

22. **How do you change the last commit?**
    Use `git commit --amend` to modify the last commit's message, add new changes, or combine it with the previous commit.

23. **What is `git push`?**
    `git push` uploads local repository changes to a remote repository, making them available for collaboration and sharing with others.

24. **How do you delete a branch?**
    - Use `git branch -d <branch_name>` to delete a local branch after merging.
    - Use `git branch -D <branch_name>` to force delete a branch that has not been merged.

25. **What is `git checkout`?**
    `git checkout` switches between branches, restores files to a previous state, or creates new branches depending on the command used.

26. **How do you list all remote repositories?**
    Use `git remote -v` to list all remote repositories configured for your local repository, showing their URLs and fetch/push configurations.

27. **How do you add a file to the staging area?**
    Use `git add <file_name>` to add a file or changes to the staging area, preparing them for the next commit.

28. **How do you remove a file from Git without deleting it?**
    Use `git rm --cached <file_name>` to remove a file from Git's index without deleting it from the filesystem, making Git ignore future changes to that file.

29. **What is `git diff`?**
    `git diff` shows the difference between changes in the working directory and the index (staging area) or between commits, helping track modifications.

30. **How do you rename a Git branch?**
    Use `git branch -m <new_name>` to rename the current branch or `git branch -m <old_name> <new_name>` to rename a different branch.

---

Sure, here are the intermediate Git interview questions and detailed answers in Markdown format:

---

---

### Intermediate Git Interview Questions and Answers

1. **Explain the Git branching strategy you use.**

   A common strategy is the Git Flow, which involves having a master branch, develop branch, feature branches, release branches, and hotfix branches, each serving a different purpose in the development cycle.

2. **What is the significance of `git merge --no-ff`?**

   `git merge --no-ff` creates a merge commit even if the merge could be resolved as a fast-forward, preserving the history of a feature branch.

3. **How do you revert a Git repository to a previous commit?**

   Use `git reset --hard <commit-hash>` to revert to a specific commit, discarding all changes since that commit.

4. **What is a detached HEAD in Git?**

   A detached HEAD occurs when you check out a commit, branch, or tag that is not the latest commit of a branch.

5. **How do you fix a detached HEAD?**

   Create a new branch from the detached HEAD state with `git branch <new-branch>` and check it out with `git checkout <new-branch>` to move back to a non-detached state.

6. **Explain the difference between `git pull` and `git fetch` followed by `git merge`.**

   `git pull` does a `git fetch` followed by a `git merge` automatically. Using `git fetch` followed by `git merge` allows you to review changes before merging.

7. **What is `git rebase --interactive`?**

   `git rebase --interactive` allows you to modify commits in many ways, such as rewriting, combining, and removing commits in a more controlled manner.

8. **How do you squash the last N commits into a single commit?**

   Use `git rebase --interactive HEAD~N` and choose `squash` for the commits you want to combine.

9. **What are submodules in Git?**

   Submodules enable the inclusion of one Git repository within another as a subdirectory. This feature is beneficial for integrating external projects or libraries into your main project.

10. **How do you update a submodule?**

    Use `git submodule update --remote` to fetch and update your submodules.

11. **What is `git bisect`? How do you use it?**

    `git bisect` assists in identifying the commit responsible for introducing a bug through the application of a binary search algorithm.

12. **How do you change the URL of a remote repository?**

    Use `git remote set-url <remote-name> <new-url>` to change the URL.

13. **What is the significance of `git push --force`?**

    `git push --force` is used to overwrite the remote history with your local history. It should be used with caution as it can overwrite changes in the remote repository.

14. **How do you clean untracked files from your working directory?**

    Use `git clean` to remove untracked files from your working directory.

15. **What is `git reflog`?**

    `git reflog` shows a log of where the HEAD and branch references have been, allowing you to navigate back to previous states.

16. **How do you resolve a rebase conflict?**

    Resolve the conflict manually in the affected files, then use `git add` to stage the resolved files, and continue the rebase with `git rebase --continue`.

17. **What is a bare repository in Git?**

    A bare repository is a Git repository that does not have a working directory, making it suitable for sharing code as it contains only the version history.

18. **How do you rename a remote branch?**

    Rename the local branch, push it to the remote, and then delete the old remote branch.

19. **What is the purpose of `git tag -a`?**

    `git tag -a` creates an annotated tag, which includes metadata such as the tagger name, email, and date, useful for marking releases.

20. **How do you find a list of files that have changed in a specific commit?**

    Use `git show --name-only <commit-hash>` to list the files that changed in a commit.

21. **What is `git blame` and how do you use it?**

    `git blame` shows what revision and author last modified each line of a file. It's useful for tracking changes and identifying who made them.

22. **How do you configure Git to ignore changes in file permissions?**

    Use `git config core.fileMode false` to ignore file permission changes.

23. **What is the difference between `HEAD`, `working tree` and `index` in Git?**

    `HEAD` refers to the last commit on the current branch, `working tree` is the set of files in your directory, and `index` (or staging area) is a staging area for commits.

24. **How do you make an existing Git branch track a remote branch?**

    Use `git branch --set-upstream-to=<remote>/<branch> <local-branch>` to set a local branch to track a remote branch.

25. **What does `git fetch --prune` do?**

    `git fetch --prune` removes remote-tracking branches that no longer exist on the remote.

26. **How do you combine multiple commits into one without merging?**

    Use `git rebase --interactive` to squash commits into a single commit without creating a merge commit.

27. **What is `git stash drop`?**

    `git stash drop` removes a single stashed state from the stash list.

28. **How do you list all the remote branches?**

    Use `git branch -r` to list all remote branches.

29. **What is the purpose of `git gc` (garbage collection)?**

    `git gc` cleans up unnecessary files and optimizes the local repository.

30. **How do you find who introduced a line of code using Git?**

    Use `git blame <file-name>` to see who last modified each line of a file.

31. **What does `git commit --dry-run` do?**

    It simulates a commit, showing what would be committed without actually committing the changes.

32. **How do you revert changes made to the working directory?**

    Use `git checkout -- <file-name>` to discard changes in the working directory.

33. **What is the purpose of `git log --graph`?**

    `git log --graph` displays the commit history in a graphical representation.

34. **How do you list all tags in Git?**

    Use `git tag` to list all tags in the current repository.

35. **What is `git show` and how do you use it?**

    `git show <commit-hash>` displays the information about a git object like a commit.

36. **How do you copy a commit from one branch to another?**

    Use `git cherry-pick <commit-hash>` to apply the changes from a commit on another branch to the current branch.

37. **What is `git archive`?**

    `git archive` is used to create an archive (zip or tar) of files from a named tree.

