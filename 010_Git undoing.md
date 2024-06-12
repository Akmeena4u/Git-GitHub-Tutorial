
### Git Revert:

#### Purpose:
Git revert is used to undo specific commits by creating new commits that undo the changes introduced by the targeted commits. This approach keeps the commit history intact and is safer for shared repositories.

#### Step-by-Step Guide:

1. **Find the Commit to Revert:**
   You first need to identify the commit you want to revert. This can be done using `git log` to see the commit history.

   ```bash
   git log --oneline
   ```

   Look for the commit hash or the commit message that corresponds to the change you want to revert.

2. **Revert the Commit:**
   Once you have the commit hash or message, use the `git revert` command followed by the commit ID to create a new commit that undoes the changes.

   ```bash
   git revert <commit-hash>
   ```

   For example, if the commit hash is `abcd123`, the command would be:

   ```bash
   git revert abcd123
   ```

   Git will open an editor for you to write a revert message. If you want to skip this and use the default message, add the `--no-edit` option:

   ```bash
   git revert <commit-hash> --no-edit
   ```

   This will directly create the revert commit without opening the editor.

#### Example:
Let's say you have the following commit history:

```
abcdef1 (HEAD -> main) Fix bug in login feature
1234567 Add new feature
```

You want to revert the commit that added the new feature (`1234567`). You would use:

```bash
git revert 1234567
```

Git will create a new commit that undoes the changes introduced by the commit `1234567`.

### Git Reset:

#### Purpose:
Git reset is used to move the HEAD pointer and the current branch pointer to a specific commit, effectively resetting the project to that state. This command can be used to undo changes, but it should be used with caution, especially in shared repositories.

#### Step-by-Step Guide:

1. **Find the Commit to Reset To:**
   Similar to git revert, you need to find the commit you want to reset to using `git log`.

   ```bash
   git log --oneline
   ```

2. **Perform the Reset:**
   Use the `git reset` command followed by the commit ID to reset the project to that commit.

   ```bash
   git reset <commit-hash>
   ```

   For example, if you want to reset to commit `abcdef1`, the command would be:

   ```bash
   git reset abcdef1
   ```

   By default, `git reset` moves the HEAD pointer to the specified commit but does not modify the working directory or staging area. If you want to also reset the staging area and working directory to match the specified commit, you can use the `--hard` option:

   ```bash
   git reset --hard abcdef1
   ```

#### Example:
Using the same commit history as before:

```
abcdef1 (HEAD -> main) Fix bug in login feature
1234567 Add new feature
```

If you want to reset back to commit `abcdef1` and discard the changes from commit `1234567`, you would use:

```bash
git reset --hard abcdef1
```

This will move the HEAD pointer and the current branch pointer back to `abcdef1`, effectively undoing the changes from `1234567`.

### Git Amend:

#### Purpose:
Git amend is used to modify the most recent commit. It allows you to make changes to the commit message or add more changes to the commit.

#### Step-by-Step Guide:

1. **Make Changes:**
   First, make the changes you want to include in the commit. This could be editing files or fixing typos in the commit message.

2. **Stage Changes:**
   Stage the changes using `git add` as you would for a regular commit.

   ```bash
   git add <file1> <file2> ...
   ```

3. **Amend the Commit:**
   Once the changes are staged, use the `git commit --amend` command to modify the most recent commit.

   ```bash
   git commit --amend
   ```

   This will open an editor where you can modify the commit message. Make your changes, save, and close the editor.

#### Example:
Suppose you made a commit with the message "Fixed typo" but later realized there was more to add to that commit. You make the additional changes to your files and stage them:

```bash
git add <file1> <file2> ...
```

Then, you use `git commit --amend` to modify the existing commit:

```bash
git commit --amend
```

This will open the editor with the previous commit message. You can edit the message to include the additional changes or fix any typos, save, and close the editor. Git will then create a new commit that includes both the original changes and the additional changes or modifications to the commit message.

These commands are fundamental in Git for managing your project's history, undoing changes, and making adjustments to commits. However, they can have significant effects on your repository's history, so it's crucial to use them with care, especially in collaborative environments.
