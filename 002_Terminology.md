### Terminology and Basics of Git and GitHub

#### Git and GitHub
- **Git**: A version control system to track changes in your files. Installed on your computer.
- **GitHub**: An online platform to store and share Git repositories. Allows collaboration on projects. GitHub is the largest host of source code in the world, and has been owned by Microsoft 
    since 2018.

#### Key Terms
- **Repository**: A collection of files and directories managed by Git. Think of it as a folder with extra tracking features.
- **Branch**: An alternative timeline of your code. Allows you to work on different features or fixes separately.

### Checking Your Git Version
- To check the installed version of Git, run:
  ```sh
  git --version
  ```
  This will display the Git version on your system.

### Repository
- A repository (or "repo") is like a folder that holds your project files, including code, documents, and other resources.
- To check the current state of your repository, use:
  ```sh
  git status
  ```

### Configuring Git Settings
- Git uses your username and email for each commit.
- Set your global username and email:
  ```sh
  git config --global user.email "your-email@example.com"
  git config --global user.name "Your Name"
  ```
- To view all your settings:
  ```sh
  git config --list
  ```

### Creating a Repository
1. **Create a new folder** and navigate into it.
2. **Initialize it as a Git repository**:
   ```sh
   git init
   ```

### Making a Commit
1. **Stage your files**:
   ```sh
   git add <file> <file2>
   ```
2. **Commit your changes**:
   ```sh
   git commit -m "commit message"
   ```

    ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/5a584558-42b0-4885-837b-f9d9cd91b4a2)

   Use a descriptive message to remember what changes were made.
3. **Complete git flow**
     A complete git flow, along with pushing the code to github looks like this:

    ![image](https://github.com/Akmeena4u/Git-GitHub-Tutorial/assets/93425334/8e111d7d-2533-4c63-a9eb-5f5ad57d8c72)


### Viewing Commit History
- To see the history of your repository:
  ```sh
  git log
  ```
- For a simplified view:
  ```sh
  git log --oneline
  ```

### Changing the Default Editor
- To set Visual Studio Code as your default Git editor:
  ```sh
  git config --global core.editor "code --wait"
  ```

### Ignoring Files
- Create a `.gitignore` file to tell Git which files or directories to ignore.
  Example:
  ```sh
  node_modules
  .env
  .vscode
  ```
- This will prevent Git from tracking the specified files or folders.

### Conclusion
- We've covered the basics of Git, including checking your version, configuring settings, creating a repository, making commits, viewing history, and ignoring files.
- With these fundamentals, you can start managing your code effectively with Git and GitHub.
