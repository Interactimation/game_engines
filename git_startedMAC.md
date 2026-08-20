---
layout: default
---

# Local Git Repository → GitHub → GitHub Pages Static Site (macOS)

## 0 — What This Does

Creates a local Git repository, connects it to GitHub, and publishes it as a static website using GitHub Pages.

---

## 1 — Check That Git Is Installed

Open **Terminal**:

**Applications → Utilities → Terminal**

Enter:

```bash
git --version
```

You should see a Git version number.

If macOS asks to install **Command Line Tools**, click **Install**.

You will also need:

- **Visual Studio Code:** https://code.visualstudio.com
- **GitHub account:** https://github.com

---

## 2 — Configure Your Git Identity

Do this once on each computer.

This information identifies **you as the author of your commits**.

Use your own name:

```bash
git config --global user.name "Your Name"
```

Use the **email address associated with your GitHub account**:

```bash
git config --global user.email "your@email.com"
```

This is your personal information, **not the repository name**.

You normally do not need to do this again on this computer.

---

## 3 — Create the GitHub Repository

1. Log in to GitHub.
2. Click **New repository**.
3. Enter a repository name.
4. Do **not** add:
   - README
   - `.gitignore`
   - License
5. Click **Create repository**.
6. Copy the **HTTPS** repository URL.

It should look like:

```text
https://github.com/USERNAME/REPOSITORY.git
```

Keep this page open.

---

## 4 — Create and Open Your Local Project Folder

1. Create a folder on your Mac for the project.
2. Open **Visual Studio Code**.
3. Choose **File → Open Folder**.
4. Select your project folder.

VS Code should now show the folder in the Explorer.

---

## 5 — Initialize the Local Git Repository

In VS Code:

1. Click the **Source Control** icon in the left sidebar.
2. Click **Initialize Repository**.

A hidden `.git` folder is created inside your project folder.

This turns the folder into a Git repository.

---

## 6 — Connect It to Your GitHub Repository

In VS Code choose:

**Terminal → New Terminal**

Enter:

```bash
git branch -M main
```

Then enter:

```bash
git remote add origin PASTE-YOUR-REPOSITORY-URL-HERE
```

Example:

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
```

That is the last routine Terminal setup required.

### If You Entered the Wrong Repository URL

Enter:

```bash
git remote remove origin
```

Then repeat the `git remote add origin` command with the correct URL.

---

## 7 — Create a Basic Website

In VS Code, create a file named:

```text
index.html
```

Add:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Site</title>
</head>
<body>
    <h1>Hello, world!</h1>
</body>
</html>
```

Save the file.

---

## 8 — Make Your First Commit

1. Click **Source Control**.
2. `index.html` should appear under **Changes**.
3. Click the **+** beside **Changes** to stage everything.
4. Enter a commit message:

```text
Initial site
```

5. Click **Commit**.

If VS Code reports that your name or email has not been configured, return to **Step 2**.

---

## 9 — Push the Site to GitHub

After committing, click:

**Publish Branch**

or, if shown:

**Sync Changes**

If VS Code asks you to sign in to GitHub:

1. Click **Sign In**.
2. Complete authentication in your browser.
3. Return to VS Code.

You normally do **not** need to create a Personal Access Token.

### Check

Open your repository on GitHub.

You should now see:

```text
index.html
```

If you do, your local folder and GitHub repository are successfully connected.

---

## 10 — Enable GitHub Pages

On GitHub:

1. Open the repository.
2. Click **Settings**.
3. Select **Pages**.
4. Under **Build and deployment** choose:
   - **Source:** Deploy from a branch
   - **Branch:** main
   - **Folder:** / (root)
5. Click **Save**.

GitHub will create a site address similar to:

```text
https://USERNAME.github.io/REPOSITORY/
```

It may take several minutes to appear.

Refresh the **Pages** settings page until GitHub displays the site URL.

---

## 11 — Test the Website

Open the GitHub Pages URL.

You should see:

```text
Hello, world!
```

If you do not:

1. Confirm that `index.html` is visible in the GitHub repository.
2. Confirm that GitHub Pages is using:
   - `main`
   - `/ (root)`
3. Wait several minutes.
4. Refresh the browser.
5. If necessary, hard refresh with:

```text
Cmd+Shift+R
```

---

## 12 — Add the Website Link to the Repository

On the main page of the GitHub repository:

1. Find **About**.
2. Click the gear icon.
3. Check **Website**.
4. Paste your GitHub Pages URL.
5. Save.

The live website link should now appear on the repository page.

---

## 13 — Normal Workflow From Now On

You should not normally need Terminal again for this project.

After changing your files:

1. Save your work.
2. Open **Source Control**.
3. Click the **+** beside **Changes** to stage the changes.
4. Enter a short commit message.
5. Click **Commit**.
6. Click **Sync Changes**.

Your changes are now pushed to GitHub.

GitHub Pages will update shortly afterward.

---

## 14 — Test the Workflow

Change:

```html
<h1>Hello, world!</h1>
```

to:

```html
<h1>Hello, world!!</h1>
```

Save the file.

The **Source Control** icon should show that one file has changed.

Then:

1. Open **Source Control**.
2. Stage the change with **+**.
3. Enter:

```text
Update heading
```

4. Click **Commit**.
5. Click **Sync Changes**.

Check the repository on GitHub.

The changed `index.html` should appear there.

After a short delay, the GitHub Pages website should update as well.

---

## 15 — Working on More Than One Computer

If you work on the same repository from multiple computers, **Sync before you begin editing**.

In VS Code:

1. Open the project.
2. Open **Source Control**.
3. Click **Sync Changes** if available.
4. Then begin working.

When finished:

1. Stage.
2. Commit.
3. Sync Changes.

This reduces the chance of conflicting versions of the same files.

---

## 16 — If Something Goes Wrong

Do not delete your project folder.

Open:

**Terminal → New Terminal**

and enter:

```bash
git status
```

`git status` is safe: it does not change your files.

It can tell you:

- which branch you are on
- which files have changed
- which files are staged
- whether you have uncommitted work
- whether your local repository differs from GitHub

If you do not understand the result, copy the complete `git status` output before trying to fix anything.

