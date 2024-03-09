---
Alias: HTML Basics
Tag: HTML, TheOdinProject, basics
Author: S.Sunhaloo
Type: Basics
Date: 2023-11-06
Status: Completed
---

## List of Contents

- [[The Odin Project Foundations#Introduction to Web Development | Introduction to Web Development]]
- [[The Odin Project Foundations#How Does the Web Works? | How Does the Web Works?]]
- [[The Odin Project Foundations#Setting Up Environment | Setting Up Environment]]
	- [[The Odin Project Foundations#Setting up Git | Setting up Git]]

# Introduction to Web Development

>[!tip]- What do Web Developers do?
>They **build** and **maintain** *websites*

>[!tip]- Types of Web Developers
>- Front-End
>	- The beautification of Websites
>	- HTML, CSS
>- Back-End
>	- Server Sided
>	- Serves the *Front-End*
>	- Java, Python, JavaScript
>- Full-Stack
>	- Can **comfortably** work in both *Front* and *Back* End

>[!tip]- Some Tools we are going to be Using?
>1. Text Editors ( *VS Code*, *Neovim* )
>2. Command Line Interface ( *Linux Based* )
>3. Git
>4. GitHub

>[!tip]- Understand $\rightarrow$ Practice $\rightarrow$ Teach
>Even if you are forgetting something, keep pushing ( *that's what she said* ); just trust the process;
>- Build Things
>- Watch YouTube Videos!
>- Google It!
>- Take Breaks; even if you have to take 1 days off
>This will help you to motivate yourself and have a **Growth Mindset**
>- This to this song if you need some motivation: [Click Here](https://www.youtube.com/watch?v=n1oUspMuUgk)
>
>>[!info] Brain Modes
>>### Focus Mode
>>- Occurs when you are **actively** learning, reading, watching videos, working on projects and more
>>### Diffuse Mode
>>- Occurs when you are away from the Computer
>>	- Bathing
>>	- Shitting
>>	- Doing Chores
>>	- Cooking
>
>>[!note]
>>Use the **Pomodoro Technique**
>>### What to Do during Beaks?
>>- Drink Water
>>- Listen to Music
>>- Journal
>>- Close your eyes and Meditate
>>- Go for a walk
>>- Eat Something

# Web Basics

I have moved very quickly on these; because it talks on simple models such as:

- Routers
- Network Topologies
- Client and Server

# Setting Up Environment

## OS

It **highly** recommends to use **Linux** ( "*The GOAT*" )  / **MacOS**.

>I am using WSL on Windows

## Code Editor

Simple; just use **VS Code** ( "*It is the standard for modern developers*" )

Make sure that you have the **Extension**

- Live Server by *Ritwick Dey*

OR

- Just open the *HTML* file in your browser

>I am using a combination of VS Code and Neovim

## Browser

It also recommends to use **Google Chrome**

>I am using a fork of Google Chrome $\Rightarrow$ Thorium $\rightarrow$ The World's Fastest Browser

## CLI

Here is a good explanation on the **UNIX** Shell ( "*Remember this is not PowerShell $\rightarrow$ we are using Linux here!*" )

Website: Click [here](https://swcarpentry.github.io/shell-novice/index.html) to go to tutorials

## Setting up Git

>[!Warning] Windows
>You need **GIT Bash**

### Private Email

Step 1: Create User Name and Email

- I used my GitHub username which is "*Sunhaloo*"
- I used the private email
	- Go to this [link](https://github.com/settings/emails)
		- Just under "*Primary email address*"

```bash

git config --global user.name "Your Name"
git config --global user.email "123456789+odin@users.noreply.github.com" # Remember to use your own private GitHub email here.

```

Step 2: Change the default branch on new "*repos*" from `master` to `main`

```bash

git config --global init.defaultBranch main

```

Step 3: Adding colourful output with `git`

```bash

git config --global color.ui auto

```

Step 4: Making default branch to be compatible ( "*reconciliation*" ) to *merging*

```bash

git config --global pull.rebase false

```

Step 5: Check if everything is working correctly

```bash

git config --global --list

```

>[!note]
>All of the above $\uparrow$ is done in **GIT Bash**

---

### Generating New SSH Key

Step 1: Create SSH Key with *regular* email

```shell

# NOTE: use your regular email
ssh-keygen -t ed25519 -C "example_email@email.com"

```

>[!note]
>Some prompts will appear in the **GIT Bash**
>- I just pressed **ENTER** on everything
>	- I did not want to change the name of the file
>	- I did not want to add a passphrase
>		- Thus pressed **ENTER** on everything

>[!info]
>For this part use **PowerShell** with *admin* privileges

Step 2: Run "*ssh-agent*"

- I have put `-StartupType Manual` $\rightarrow$ Hate things when they run in background

```powershell

Get-Service -Name ssh-agent | Set-Service -StartupType Manual

```

```powershell

Start-Service ssh-agent

```

Step 3: Go to `C:\Users\user_name\.ssh\`

- If you did not change the name; just "*cat*" the file

```powershell

cat id_ed25519.pub

```

- else; "*cat*" the file with the appropriate name that you added in the **GIT Bash** prompt

```powershell

cat file_name.pub

```

>[!info]
>It should **start** with *ssh-ed25519* and **end** with your *email*

---

### Go back to **GIT Bash**

Step 1: SSH to GitHub

```bash

ssh -T git@github.com

```

You will see a warning after this command

Step 2: We are near the finishing line

- If you see `SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU`
	- Type "*yes*"
- You should see something like this

```bash

Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access.
 
```

# Git and GitHub

### Difference Click [[Media Swipe File#Git v/s GitHub | here]]

## Cloning a Repository

```bash

git clone https://www.github.com/Sunhaloo/Projects

```

## Creating and "*Pushing*" a file

### Create a file named "hello_world.txt"

```bash

touch test.txt

```

### Check **Git Status**

```bash

git status

```

- You will see something like this:

![[GitStatus1.PNG]]

### Staging the file

```bash

git add hello_world.txt

```

### Check **Git Status** *again*

- You should see a green text now!

![[GitStatus2.PNG]]

### Check the output

```bash

git log

```

- You should see your entry for "*Add hello_world.txt*"

>[!note] Got Stuck?
>If you got stuck at **END** in the terminal
>- Press "*q*"

### Staging All files ( *Adding all file* )

```bash

git add .

```

## Actually "*Pushing*" all files

### Committing all files

```bash

git commit -m "Edit README.md and hello_world.txt"

```

### Pushing the files into the Repository

>[!note]
>This is done so that we can see the files in the repository
>- This is also found on GitHub when creating a new "*repo*"

```git

git remote add origin https://github.com/Sunhaloo/odin-recipes.git

git branch -M main

git push -u origin main

```

### Check **Git Status** again

- It should say: "*nothing to commit, working ree clean*"

```bash

git status

```

- The output:

![[GitStatus3.PNG]]

### **Git Log** again

```bash

git log

```

- The output:

![[GitLog1.PNG]]

### Push it in

>That's what she said

- Push to main branch

>In this case, I used my own personal repo; where there is not main branch; thus I will be using "*Python*"

```bash

git push origin Python

```

- It will ask you to *authenticate* by opening a *GitHub* page on your browser
	- "*It is not a GitHub page*" $\rightarrow$ more like port / IP page

>[!tip] Don't Stress Too Much
>Its the **first** time you are learning this; thus, it is very normal to forget it immediately!
>But we will be using them later. Hence, keep this file / note handy