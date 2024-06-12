### Getting Started with GitHub: A Step-by-Step Guide

#### What is GitHub?
- GitHub is a web-based Git repository hosting service used by developers to collaborate on projects and share code.
- Alternatives to GitHub include GitLab, Bitbucket, Azure Repos, and Gitea, but GitHub is the most popular platform.

#### Creating a GitHub Account
1. Visit the GitHub website and click "Sign up."
2. Enter your email and password to create an account.

#### Configuring Git
This will set your email and name as your global settings. You can change these settings later by running the following command:
1. Open a terminal window.
2. Set your email and name globally using:
   ```
   git config --global user.email "your-email@example.com"
   git config --global user.name "Your Name"
   ```
3. Verify your settings with `git config --list`.


---

### Setting Up SSH Key and Adding to GitHub

If you haven’t done it already, you need to set up an SSH key and add it to your GitHub account. Below are the steps to do this:
[Github website](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

#### Step 1: Generate a new SSH key

Open the terminal and run the following command:

```bash
ssh-keygen -t ed25519 -C "your-email@chaicode.com"
```

Replace `"your-email@chaicode.com"` with your actual email address. This command generates a new SSH key using the Ed25519 algorithm.

#### Save the key

After generating the key, save it to your computer by pressing enter when prompted to choose a file location:

```
Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]
```

You can choose to set a passphrase for the key or leave it blank. Press enter to save the key without a passphrase.

#### Add the key to your SSH agent

Add the key to your SSH agent by running the following command:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

This command starts the SSH agent and adds your SSH key to it.

#### Add the key to GitHub

Use the GitHub website to add the SSH key to your account:
[Github website](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account?tool=webui)

1. Navigate to your GitHub account settings.
2. Go to "SSH and GPG keys" in the left menu.
3. Click on "New SSH key" or "Add SSH key."
4. Paste your SSH key into the provided field.
5. Give your key a title (e.g., "My SSH Key") and click "Add SSH key."

That's it! Your SSH key is now set up and added to your GitHub account, allowing you to securely authenticate and interact with GitHub repositories using SSH.

---

#### Adding Code to a Remote Repository
1. Initialize a new repository on your system:
   ```
   git init
   ```
2. Add files and commit changes:
   ```
   git add <files>
   git commit -m "Commit message"
   ```
3. Check the remote URL:
   ```
   git remote -v
   ```

#### Pushing Code to Remote Repository
1. Add a remote repository:
   ```
   git remote add origin <remote-url>
   ```
2. Push code to the remote repository:
   ```
   git push origin main
   ```

#### Setting Up an Upstream Remote
1. Add an upstream remote:
   ```
   git remote add upstream <remote-url>
   ```
   or shorthand:
   ```
   git remote add -u <remote-url>
   ```
2. Push code with upstream:
   ```
   git push -u origin main
   ```

#### Fetching and Pulling Code from Remote Repository
- Fetch code:
  ```
  git fetch <remote-name>
  ```
- Pull code:
  ```
  git pull origin main
  ```

#### Conclusion
- GitHub is a powerful platform for collaboration and code sharing.
- Key steps include creating an account, configuring Git, setting up SSH keys, adding code to repositories, pushing and pulling code, and managing upstream remotes.
