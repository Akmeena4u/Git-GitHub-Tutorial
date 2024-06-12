### Git Behind the Scenes

#### Introduction
Git is a version control system that helps you track changes to your files and folders. Understanding how Git works internally can help you manage your code more effectively.

### Git Snapshots
- A **snapshot** in Git is a record of the state of your code at a specific point in time.
- Each snapshot is identified by a unique **hash code**, a string of characters that uniquely represents the contents of the snapshot.
- Git stores snapshots in a locally stored key-value based database, where each piece of data is an object identified by a unique hash.

### The 3 Musketeers of Git
Git uses three main types of objects to manage your code:

1. **Commit Object**
2. **Tree Object**
3. **Blob Object**

#### Commit Object
- Represents a specific version of your code.
- Contains the following information:
  - **Tree Object**: Points to the tree object representing the state of the directory.
  - **Parent Commit Object**: Points to the previous commit.
  - **Author**: The person who originally wrote the code.
  - **Committer**: The person who last applied the commit.
  - **Commit Message**: A message describing the changes.

#### Tree Object
- Represents the directory structure of your project at a specific point in time.
- Contains the following information:
  - **File Mode**: The permissions for the file.
  - **File Name**: The name of the file.
  - **File Hash**: A unique identifier for the file.
  - **Parent Tree Object**: Points to the parent directory tree object.

#### Blob Object
- Represents the actual content of a file.
- Stored within the tree object and contains the file data.

  ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/cedba054-7c6f-4cfa-a190-1b45fb3d06bc)


### Helpful Commands to Explore Git Internals

#### View Commit Object
- Use the following command to display detailed information about a commit:
  ```sh
  git show -s --pretty=raw <commit-hash>
  ```

#### View Tree Object
- Get the tree object ID from the commit object and use this command to display the tree object:
  ```sh
  git ls-tree <tree-id>
  ```

#### View Blob Object
- Get the blob object ID from the tree object and use this command to display the file content:
  ```sh
  git show <blob-id>
  ```

#### View Commit Details
- Use this command to display the full commit object:
  ```sh
  git cat-file -p <commit-id>
  ```

### Summary
- Git uses snapshots to track changes, with each snapshot identified by a unique hash.
- The key objects in Git are the commit object, tree object, and blob object.
- The commit object contains metadata and links to the tree object.
- The tree object represents the directory structure and links to blob objects.
- Blob objects store the actual file content.
- Useful commands help you explore the internal structure and content of Git objects.
