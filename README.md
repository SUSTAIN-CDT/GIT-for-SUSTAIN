# GIT-for-SUSTAIN
A guide for getting to grips with GitHub

![Git Workflow Diagram](./diagram.svg)


# Step-by-Step Process to Create and Connect to a New Repository

## Step 0: Set Up Authentication
[TO ADD]

## Step 1: Create a Repository on GitHub (or similar platform)
1. Log in to your GitHub account
2. Click the "+" icon in the top-right corner, then select "New repository"
3. Enter a repository name
4. Optionally add a description
5. Choose public or private
6. **Important:** Do NOT initialize with a README, .gitignore, or license if you already have a local project
7. Click "Create repository"

## Step 2: Initialize Your Local Project (if not already done)
```bash
# Navigate to your project directory
cd /path/to/your/project

# Initialize a Git repository
git init
```

## Step 3: Add Your Files to Git
```bash
# Add all files to staging
git add .

# Commit the files
git commit -m "Initial commit"
```

## Step 4: Connect to the Remote Repository
```bash
# Add the remote repository URL (GitHub will show you this URL after creating the repo)
# For HTTPS connection:
git remote add origin https://github.com/yourusername/your-repository-name.git

# OR for SSH connection (if you set up SSH keys):
git remote add origin git@github.com:yourusername/your-repository-name.git

# Verify the remote was added correctly (optional)
git remote -v
```

## Step 5: Push Your Code to GitHub
```bash
# Push your committed code to the remote repository
git push -u origin main    # Use 'master' instead of 'main' for older Git versions

# The -u flag sets the upstream, so next time you can just use 'git push'
```

### Authentication During Push
- **If using HTTPS**: You'll be prompted for your username and personal access token (not your regular password)
- **If using SSH**: Your SSH key will be used automatically if you've set it up correctly
- **Credential Helper**: Git may store your credentials after the first successful authentication:
  ```bash
  # Set Git to cache credentials for 15 minutes
  git config --global credential.helper cache
  
  # Or store credentials permanently (less secure)
  git config --global credential.helper store
  ```

## Step 6: Verify Your Code is on GitHub
Visit your repository URL (https://github.com/yourusername/your-repository-name) to make sure your code was pushed successfully.

## If You're Starting from Scratch (No Local Project)
If you don't have existing code and want to start a new project:

1. Create the repository with a README on GitHub
2. Clone it to your local machine:
   ```bash
   # Using HTTPS
   git clone https://github.com/yourusername/your-repository-name.git
   
   # OR using SSH (if you set up SSH keys)
   git clone git@github.com:yourusername/your-repository-name.git
   ```
3. You'll be prompted for authentication if using HTTPS
4. Start adding your files and follow the normal Git workflow
