Git & GitHub Setup Guide (Step-by-Step)
1️⃣ Install Git

First, install Git on your system.

To verify the installation, run:

git --version


If a version number appears, Git is installed correctly.

2️⃣ Configure Git (First-Time Setup)

You need to tell Git who you are:

git config --global user.name "Your Name"
git config --global user.email "your@email.com"


This information is attached to every commit you make.

3️⃣ Initialize a Repository

Inside your project folder, run:

git init


This command creates a hidden .git folder.

⚙️ What happens in the background?

Git creates a local version control system.

It starts tracking changes in your project.

All commits and history will now be stored inside the .git directory.

4️⃣ Add Files to the Staging Area

To add all files:

git add .


To add a specific file:

git add filename.js

🔎 Background:

Git does not commit changes directly.
Files must first be placed into the staging area, which prepares them for the next commit.

5️⃣ Commit Changes
git commit -m "Initial commit"


This creates a snapshot of your staged files at that moment.

🔐 SSH Key Setup (Secure Connection with GitHub)

If you use HTTPS, GitHub may ask for authentication repeatedly.
SSH provides a secure and permanent authentication method.

1️⃣ Check for an Existing SSH Key
ls -al ~/.ssh


If you do not see id_rsa.pub or id_ed25519.pub, generate a new key.

2️⃣ Generate a New SSH Key
ssh-keygen -t ed25519 -C "your@email.com"


Press Enter through the prompts.

This creates two files:

Private key (keep this secret)

Public key (ends with .pub)

3️⃣ Copy the Public Key
cat ~/.ssh/id_ed25519.pub


Copy the entire output.

4️⃣ Add the SSH Key to GitHub

Go to GitHub → Settings

Click SSH and GPG Keys

Click New SSH Key

Paste your key

Save

5️⃣ Test SSH Connection
ssh -T git@github.com


If you see:

Hi username! You've successfully authenticated


Your SSH setup is successful 🎉

🌍 Connect Local Repository to GitHub
1️⃣ Create a New Repository on GitHub

Create a repository without initializing it with a README if you already have a local project.

2️⃣ Add Remote Origin
git remote add origin git@github.com:username/repository-name.git

⚙️ Background:

origin is simply the default name for the remote repository.

It points to your GitHub repository URL.

🚀 git push -u origin main Explained

Command:

git push -u origin main


Let’s break it down:

🔹 git push

Uploads local commits to the remote repository.

🔹 origin

The name of the remote repository.

🔹 main

The branch name.

🔹 -u (Important)

-u sets the upstream branch.

What this means:

It links your local branch to the remote branch.

After this, you can simply use git push.

You do not need to type origin main every time.

👉 This command is usually used the first time you push a branch.

Example:

First time:

git push -u origin main


After that:

git push

🔄 Future Workflow

After making changes:

git add .
git commit -m "Updated feature"
git push

🧠 What Happens Internally When You Push?

When you run git push:

Git compresses commit objects.

It establishes a secure SSH connection.

It transfers objects to the remote repository.

It updates the branch pointer on the remote side.

Git does not store files directly.
It stores snapshots and object hashes, which makes it fast and efficient.