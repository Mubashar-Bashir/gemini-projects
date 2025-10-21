# Zed.dev, Gemini-CLI, and Git Project Setup Guide

This guide will walk you through setting up your development environment with Zed.dev, Gemini-CLI, and Git, along with a basic project setup.

## 1. Install Zed.dev

1.  **Download Zed.dev:** Visit the official Zed.dev website (https://zed.dev/) and download the installer for your operating system.
2.  **Install Zed.dev:** Follow the on-screen instructions to install the application.
3.  **Launch Zed.dev:** Open Zed.dev to ensure it's installed correctly.

## 2. Install Gemini-CLI

(Note: The installation steps for Gemini-CLI may vary depending on its distribution method. This guide assumes a common installation approach. Please refer to the official Gemini-CLI documentation for the most accurate instructions.)

1.  **Prerequisites:** Ensure you have Node.js and npm (Node Package Manager) installed. You can download them from https://nodejs.org/.
2.  **Install Gemini-CLI:** Open your terminal or command prompt and run the following command:
    ```bash
    npm install -g gemini-cli
    ```
    (If you encounter permission errors, you might need to use `sudo` on macOS/Linux: `sudo npm install -g gemini-cli`)
3.  **Verify Installation:** After installation, check the version to confirm it's working:
    ```bash
    gemini-cli --version
    ```

## 3. Set Up Git

1.  **Install Git:** If you don't have Git installed, download it from https://git-scm.com/downloads and follow the installation instructions.
2.  **Configure Git:** Open your terminal or command prompt and set up your user name and email, which will be used for your commits:
    ```bash
    git config --global user.name "Your Name"
    git config --global user.email "your.email@example.com"
    ```
3.  **Generate SSH Key (Optional but Recommended):** For secure communication with remote repositories (like GitHub, GitLab, Bitbucket), generate an SSH key:
    ```bash
    ssh-keygen -t ed25519 -C "your.email@example.com"
    ```
    Follow the prompts. You can usually accept the default file location and choose a strong passphrase.
4.  **Add SSH Key to SSH Agent:**
    ```bash
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    ```
5.  **Add SSH Key to GitHub/GitLab/Bitbucket:** Copy your public SSH key to your clipboard:
    - **macOS:** `pbcopy < ~/.ssh/id_ed25519.pub`
    - **Windows (Git Bash):** `cat ~/.ssh/id_ed25519.pub | clip`
    - **Linux:** `cat ~/.ssh/id_ed25519.pub` (then manually copy the output)
    Then, go to your Git hosting service's settings (e.g., GitHub -> Settings -> SSH and GPG keys -> New SSH key) and paste your public key.

## 4. Basic Project Setup

This section provides a generic project setup. You'll adapt this based on your specific project type (e.g., web development, Python, Java).

1.  **Create a Project Directory:** Choose a location for your project and create a new folder:
    ```bash
    mkdir my-new-project
    cd my-new-project
    ```
2.  **Initialize Git Repository:** Turn your project directory into a Git repository:
    ```bash
    git init
    ```
3.  **Create a Remote Repository (e.g., on GitHub):** Go to your Git hosting service (e.g., GitHub), create a new empty repository, and copy the remote URL (usually HTTPS or SSH).
4.  **Link Local to Remote Repository:** Add the remote repository to your local Git setup:
    ```bash
    git remote add origin <remote_repository_url>
    ```
    (Replace `<remote_repository_url>` with the URL you copied.)
5.  **dir:** It's good practice to start with a `README.md` file to describe your project.
    ```bash
    echo "# My New Project" > README.md
    ```
6.  **Make Your First Commit:**
    ```bash
    git add .
    git commit -m "Initial project setup"
    ```
7.  **Push to Remote:** Push your local changes to the remote repository:
    ```bash
    git push -u origin main
    ```
    (Note: The default branch name might be `master` instead of `main` in older Git versions. Adjust accordingly.)

## 5. Open Project in Zed.dev

1.  **Open Zed.dev.**
2.  **Go to File > Open Folder...** (or similar menu option).
3.  **Navigate to your `my-new-project` directory** and open it.

You are now ready to start developing with Zed.dev, Gemini-CLI, and Git!