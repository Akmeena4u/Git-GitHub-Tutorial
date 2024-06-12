## How to Fix Merge Conflicts in Git

### Introduction
If you work on a team with a large codebase or even by yourself on multiple branches, you've likely encountered merge conflicts. This guide will help you understand what merge conflicts are, the types of merge conflicts, and how to resolve them using GitHub and VS Code.

### What is a Merge Conflict in Git?
A merge conflict happens when changes made to the same part of a file from different branches cannot be automatically merged by Git. 

Example:
- You change line 1 of `file.txt` to "Hi world" in the `main` branch.
- You change line 1 of `file.txt` to "Hello earth" in the `new-feature` branch.

When you attempt to merge `new-feature` into `main`, Git won't know which change to keep and will raise a merge conflict error.

### What to Do When Merge Conflicts Occur
When a merge conflict occurs, Git annotates the conflicting lines like this:

```plaintext
<<<<<<< 
Conflicting change in the current branch
=======
Conflicting change in the incoming branch
>>>>>>> 
```

You need to decide which changes to keep, remove the annotations, and continue with the merge.

### Types of Merge Conflicts
1. **Content Merge Conflict**: Occurs when changes made to the same line in a file conflict.
2. **Structural Merge Conflict**: Occurs when changes affect the structure or organization of a file, such as renaming a variable or function.

### Resolving Merge Conflicts

#### Using GitHub
1. **Create a Pull Request (PR)**: Push your branch to GitHub and create a PR to merge it into the `main` branch.
   ![Create PR](https://github.com/your-repo/pull-request)
2. **Resolve Conflicts**: If there are conflicts, GitHub will notify you and provide a "Resolve conflicts" button.
   ![Resolve Conflicts](https://github.com/your-repo/resolve-conflicts)
3. **Edit Conflicting Files**: In the editor, you'll see the conflicting lines. Choose which changes to keep, remove the conflict markers, and mark the conflict as resolved.
   ![Edit Conflicts](https://github.com/your-repo/edit-conflicts)
4. **Commit Merge**: After resolving all conflicts, click "Commit merge" to complete the merge.
   ![Commit Merge](https://github.com/your-repo/commit-merge)

#### Using VS Code
1. **Initiate Merge**: In your terminal, switch to the branch you want to merge into and run `git merge branch-to-merge`.
2. **VS Code Merge Editor**: If conflicts arise, VS Code will prompt you to resolve them. You can choose to accept the incoming changes, current changes, or both.
   ![VS Code Merge Editor](https://code.visualstudio.com/merge-editor)
3. **Resolve Conflicts**: Use the options provided by VS Code to resolve each conflict. After resolving, add the files and commit them:
   ```sh
   git add .
   git commit -m "Resolved merge conflicts"
   ```

#### Using VS Code 3-Way Merge Editor
1. **Open Merge Editor**: After running `git merge branch-to-merge`, click "Resolve in Merge Editor" in VS Code.
   ![VS Code 3-Way Merge Editor](https://code.visualstudio.com/merge-3way-editor)
2. **Three Views**: The editor shows three views – the incoming branch, the current branch, and a preview.
3. **Resolve Conflicts**: Choose from options like "Accept Incoming", "Accept Current", or "Accept Combination". After resolving, click "Complete Merge".
4. **Commit Changes**: Add and commit the resolved files:
   ```sh
   git add .
   git commit -m "Resolved merge conflicts with 3-way merge editor"
   ```

### Wrapping Up
Merge conflicts are a common part of working with Git and can be resolved using tools like GitHub and VS Code. By understanding how to handle these conflicts, you can ensure a smoother workflow and collaboration with your team.
