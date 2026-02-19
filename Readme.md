learn from Git & GitHub Setup Guide (Step-by-Step)
1️⃣ Install Git

Sabse pehle system me Git install karo:

Check karne ke liye:

git --version


Agar version show ho raha hai → Git properly installed hai.

2️⃣ Configure Git (First Time Setup)

Git ko batana padta hai tum kaun ho:

git config --global user.name "Your Name"
git config --global user.email "your@email.com"


Ye information commits ke sath attach hoti hai.

3️⃣ Initialize Repository

Project folder ke andar:

git init


Ye command ek hidden .git folder banata hai.

⚙️ Background me kya hota hai?

Git ek local version control system create karta hai.

Ab har file change track ho sakta hai.

4️⃣ Add Files to Staging Area
git add .


Ya specific file:

git add filename.js


🔎 Background:
Git directly commit nahi karta. Pehle files staging area me jati hain.

5️⃣ Commit Changes
git commit -m "Initial commit"


Ye ek snapshot create karta hai.

🔐 SSH Key Setup (Secure Connection with GitHub)

HTTPS se push karoge to bar-bar password maangega.
SSH secure aur permanent solution hai.

1️⃣ Check Existing SSH Key
ls -al ~/.ssh


Agar id_rsa.pub ya id_ed25519.pub file nahi hai → new key banao.

2️⃣ Generate SSH Key
ssh-keygen -t ed25519 -C "your@email.com"


Enter press karte jao.

Ye 2 files banayega:

Private key (secret)

Public key (.pub)

3️⃣ Copy Public Key
cat ~/.ssh/id_ed25519.pub


Is output ko copy karo.

4️⃣ Add SSH Key to GitHub

GitHub → Settings

SSH and GPG Keys

New SSH Key

Paste key → Save

5️⃣ Test SSH Connection
ssh -T git@github.com


Agar message aaye:

Hi username! You've successfully authenticated


Toh setup successful 🎉

🌍 Connect Local Repo to GitHub
1️⃣ GitHub par New Repository banao

Repository create karo (without README if already local project hai).

2️⃣ Add Remote Origin
git remote add origin git@github.com:username/repository-name.git


⚙️ Background:

origin remote server ka naam hota hai.

Ye GitHub repository ka address hai.

🚀 git push -u origin main Explained

Command:

git push -u origin main


Ab isko breakdown karte hain 👇

🔹 git push

Local commits ko remote repository par bhejta hai.

🔹 origin

Remote repository ka naam (jo humne add kiya).

🔹 main

Branch ka naam.

🔹 -u (Important)

-u ka matlab hai upstream set karna.

Iska kaam:

Local branch ko remote branch se link kar deta hai.

Future me sirf git push likhne se kaam ho jayega.

Har baar origin main likhne ki zarurat nahi padegi.

👉 Ye command normally first push me use hoti hai.

Example:

First time:

git push -u origin main


Next time:

git push

🔄 Future Workflow

After changes:

git add .
git commit -m "Updated feature"
git push

🧠 Internally Kya Hota Hai?

Jab tum push karte ho:

Git commits ko compress karta hai.

SSH ke through secure channel banata hai.

Remote repo me objects store karta hai.

Branch pointer update karta hai.

Git actually files store nahi karta —
wo snapshots aur object hashes store karta hai.