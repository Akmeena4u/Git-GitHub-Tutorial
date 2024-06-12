## Git Diff, Stash, and Tags

### Git Diff

The `git diff` command shows the differences between two commits or versions of files. It's useful for seeing what changes have been made. It is used to compare the changes made in one commit with the changes made in another commit. Git consider the changed versions of same file as two different files. Then it gives names to these two files and shows the differences between them.

#### How to Read a Diff

- **a** -> file A (original version)
- **b** -> file B (new version)
- `----` indicates the old file (A)
- `+++` indicates the new file (B)
- `@@` shows the line number where the change occurred

Git will highlight the changes between file A and file B and show the line numbers and previews of the changes.

#### Comparing Working Directory and Staging Area

- **Command**: `git diff`
  - Shows unstaged changes in your working directory compared to the staging area.

#### Comparing Staging Area with Repository

- **Command**: `git diff --staged`
  - Shows changes between your last commit and the staging area (staged changes ready to be committed).

#### Comparing Between Branches

- **Command**: `git diff <branch-name-one> <branch-name-two>`
  - Compares differences between two branches.
  
- **Alternative Command**: `git diff branch-name-one..branch-name-two`
  - Another way to compare differences between two branches.

#### Comparing Specific Commits

- **Command**: `git diff <commit-hash-one> <commit-hash-two>`
  - Compares differences between two specific commits.
---
### Git Stash

Stash allows you to save changes in a temporary location without committing them, useful when you need to switch branches or need a clean working directory.You can then come back to the file later and apply the changes.
Conflicting changes will not allow you to switch branches without committing the changes. Another alternative is to use the git stash command to save your changes in a temporary location.

#### Stashing Changes

- **Command**: `git stash`
  - Saves your changes in a temporary location.

#### Naming the Stash

- **Command**: `git stash save "work in progress on X feature"`
  - Saves your changes with a descriptive name.

#### Viewing the Stash List

- **Command**: `git stash list`
  - Lists all stashes.

#### Applying the Stash

- **Command**: `git stash apply`
  - Applies the most recent stash.

#### Applying a Specific Stash

- **Command**: `git stash apply stash@{0}`
  - Applies a specific stash. Use `git stash list` to find the stash name.

#### Applying and Dropping the Stash

- **Command**: `git stash pop`
  - Applies the most recent stash and removes it from the stash list.

#### Dropping the Stash

- **Command**: `git stash drop`
  - Removes the most recent stash without applying it.

#### Applying Stash to a Specific Branch

- **Command**: `git stash apply stash@{0} <branch-name>`
  - Applies a specific stash to a specific branch.

#### Clearing the Stash

- **Command**: `git stash clear`
  - Clears all stashes.
----
### Git Tags

Tags mark specific points in your repository, useful for versioning or remembering specific commits. Tags are like sticky notes that you can attach to your commits.

#### Creating a Tag

- **Command**: `git tag <tag-name>`
  - Creates a new tag with the specified name, attached to the current commit.

#### Creating an Annotated Tag

- **Command**: `git tag -a <tag-name> -m "Release 1.0"`
  - Creates an annotated tag with a message, attached to the current commit.

#### Listing All Tags

- **Command**: `git tag`
  - Lists all tags in the repository.

#### Tagging a Specific Commit

- **Command**: `git tag <tag-name> <commit-hash>`
  - Tags a specific commit.

#### Pushing Tags to Remote Repository

- **Command**: `git push origin <tag-name>`
  - Pushes a tag to the remote repository.

#### Deleting a Tag

- **Command**: `git tag -d <tag-name>`
  - Deletes a tag locally.

#### Deleting a Tag on Remote Repository

- **Command**: `git push origin :<tag-name>`
  - Deletes a tag on the remote repository.

### Conclusion

These git commands—`diff`, `stash`, and `tag`—are not everyday commands but are very useful in specific situations. By understanding how to use them, you can manage your git workflow more effectively.
