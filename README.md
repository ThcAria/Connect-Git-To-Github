# 🔐 How to Connect Git to GitHub Using SSH — (Step by Step Guide)
This guide will help you securely connect your local Git to GitHub using SSH authentication.

## ✅ Step 1 — Generate Your SSH Keys in Git

Open your terminal (Git Bash on Windows) and run:

```bash 
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Press Enter to save the key in the default location.

After the process finishes, you will have:

Private key → stays on your computer (never share it)

Public key → this is what you add to GitHub

Now copy your public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

## ✅ Step 2 — Add the SSH Key to Your GitHub Account
Go to GitHub

Click your profile picture → Settings

Navigate to SSH and GPG keys

Click New SSH Key

Paste your public key

Click Add SSH key

Your GitHub account can now recognize your computer.

## ✅ Step 3 — Use SSH in Your Repository
After creating a repository on GitHub:

Open your repository page

Click the Code button

Select SSH

Copy the SSH URL

It should look like:

```bash
git@github.com:username/repository.git
```

Now clone the repository:

```bash
git clone git@github.com:username/repository
```

Or if your repo already exists locally, connect it:

```bash
git remote set-url origin git@github.com:username/repository.git
```

## ✅ Step 4 — Test Your Connection (Recommended)
Run:

```bash
ssh -T git@github.com
```

If successful, you’ll see:

`Hi username! You've successfully authenticated.`

🎉 Done! Your Git is now connected to GitHub using SSH.
