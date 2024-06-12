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

![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/9a777b58-2770-4775-a8a8-b3239f9d7ce2)

You need to decide which changes to keep, remove the annotations, and continue with the merge.

### Types of Merge Conflicts
1. **Content Merge Conflict**: Occurs when changes made to the same line in a file conflict.
2. **Structural Merge Conflict**: Occurs when changes affect the structure or organization of a file, such as renaming a variable or function.

### Resolving Merge Conflicts

#### Using GitHub 
   In this case, immediately you click on “Compare and Pull”, you will see that there can’t be an automatic merging because there’s a conflict:
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/5308a479-b46c-4ee3-a354-6ebdcf7745c2)

1. **Create a Pull Request (PR)**: Push your branch to GitHub and create a PR to merge it into the `main` branch.
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/c4eef437-dd3a-41c2-884f-2650c01daf1f)

2. **Resolve Conflicts**: If there are conflicts, GitHub will notify you and provide a "Resolve conflicts" button.
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/6e6bca97-1dbc-4b9d-87dd-6ae6efdad232)

3. **Edit Conflicting Files**: In the editor, you'll see the conflicting lines. Choose which changes to keep, remove the conflict markers, and mark the conflict as resolved.
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/fe518f99-6dd9-4b4e-8dda-a65ae158c2bc)
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/2d44cbe3-3e89-43aa-bcc3-4d069fdd0fa9)


4. **Commit Merge**: After resolving all conflicts, click "Commit merge" to complete the merge.
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/6904664b-7369-4970-9fa0-4f53d4bf1c17)


#### Using VS Code
1. **Initiate Merge**: In your terminal, switch to the branch you want to merge into and run `git merge branch-to-merge`.
2. **VS Code Merge Editor**: If conflicts arise, VS Code will prompt you to resolve them. You can choose to accept the incoming changes, current changes, or both.
   
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/7df94a60-9144-46d0-9c20-15745d952667)

4. **Resolve Conflicts**: Use the options provided by VS Code to resolve each conflict. After resolving, add the files and commit them:
   ```sh
   git add .
   git commit -m "Resolved merge conflicts"
   ```

#### Using VS Code 3-Way Merge Editor
1. **Open Merge Editor**: After running `git merge branch-to-merge`, click "Resolve in Merge Editor" in VS Code.
   ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/bee9c2aa-a709-4355-9546-b500e9eb6ec6)

2. **Three Views**: The editor shows three views – the incoming branch, the current branch, and a preview.
3. **Resolve Conflicts**: Choose from options like "Accept Incoming", "Accept Current", or "Accept Combination". After resolving, click "Complete Merge".
4. **Commit Changes**: Add and commit the resolved files:
   ```sh
   git add .
   git commit -m "Resolved merge conflicts with 3-way merge editor"
   ```

### Wrapping Up
Merge conflicts are a common part of working with Git and can be resolved using tools like GitHub and VS Code. By understanding how to handle these conflicts, you can ensure a smoother workflow and collaboration with your team.
