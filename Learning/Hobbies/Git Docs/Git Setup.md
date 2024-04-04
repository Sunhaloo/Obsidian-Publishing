---
Alias: Git Setup Windows | Linux
Tag: Git, GitHub
Author: S.Sunhaloo
Date: 2023-12-09
Status: HOLD
---

>[!info] [Git Setup Website](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

>[!note]
>I might use these shortcuts / acronyms
>- Repository = Repo

## List of Contents

### Chapter 1: Setup

- [[Git Setup#Requirements | Requirements]]
- [[Git Setup#First Time Setup | First Time Setup]]
	- [[Git Setup#View All Settings | View All Settings]]
	- [[Git Setup#Identity | Identity]]
	- [[Git Setup#Editor | Editor]]
		- [[Git Setup#VS Code | VS Code]]
	- [[Git Setup#Default Branch ( `master` $ rightarrow$ `main`) | Default Branch]]
	- [[Git Setup#Checking Settings | Checking Settings]]

---

### Help

- [[Git Setup#Getting Help | Getting Help]]

<h3>Chapter 2: Getting Started ( <span style="color: red">IMPORTANT</span> )</h3>

- [[Git Setup#Git Basics - Getting a Git Repo | Git Basics - Getting a Git Repo]]
	- [[Git Setup#Getting a Git Repo] | Getting a Git Repo]]
		- [[Git Setup#Initialising Repo into Existing Directory / Folder | Initialising Repo into Existing Directory / Folder]]
		- [[Git Setup#Commiting | Commiting]]
	- [[Git Setup#Cloning an Existing Repository | Cloning an Existing Repository]]
		- [[Git Setup#Command to clone any Repo | Command to clone any Repo]]

### Git Basics - Recording Changes to the Repo

- [[Git Setup#Git Basics - Recording Changes to Repository | Git Basics - Recording Changes to Repository]]
- [[Git Setup#Life Cycle of Status of Files | Life Cycle of Status of Files]]
- [[Git Setup#Checking Status of Files | Checking Status of Files]]
- [[Git Setup#Tracking New Files | Tracking New Files]]
- [[Git Setup#Staging Modified Files | Staging Modified Files]]
	- [[Git Setup#Adding the Modified File | Adding the Modified File]]
- [[Git Setup#Ignoring Files | Ignoring Files]]
- [[Git Setup#Rules for `.gitignore` Files | Rules for Git Ignore]]
- [[Git Setup#Viewing Staged and Unstaged Changes | Viewing Staged and Unstaged Changes]]
- [[Git Setup#Committing Your Changes | Committing Your Changes]]
- [[Git Setup#Skipping the Staging Area | Skipping the Staging Area]]
- [[Git Setup#Removing Files | Removing Files]]
- [[Git Setup#Moving Files | Moving Files]]

## Requirements

- [Git](https://git-scm.com/downloads) $\leftarrow$ Click on Link to go Download it!

### Optional

- Terminal
  If you are in Linux / WSL; I don't think you need **Git Bash**

---

### My Links

- [[Git Setup#Socials | Links to Socials]]

---

# First Time Setup

## View All Settings

You can view all the settings and where they are coming from by using the command

```bash

git config --list --show-origin

```
	
## Identity

You will need to add your **email** and your **username**. This is because every Git Commit uses these information $\uparrow$

- Setup Email

```bash

git config --global user.email "username@email.com"

```

- Setup Username

```bash

git config --global user.name "username"

```

>[!note]
>This is only done **once**.
>Because we added the `--global` option / argument; Git will know this and always use the information we gave it.
>- Many GUI tools will help you do this when you first run them.

## Editor

>[!success] Vim is the Greatest Editor!

- Please copy the code where you desired *Editor* is found.

### Vim

```bash

git config --global core.editor "vim"

```

### Emacs

```bash

git config --global core.editor "emacs"

```

### VS Code

```bash

git config --global core.editor "code --wait"

```

- Option / Argument `--wait`: Makes Git wait until you **close** the *file* in VS Code

### Nano

```bash

git config --global core.editor "nano"

```

## Default Branch ( `master` $\rightarrow$ `main`)

To change the default branch to `main`; we need to enter this following command:

```bash

git config --global init.defaultBranch main

```

## Checking Settings

To check the all settings that we have added are configured properly. We can use the command:

```bash

git config --list

```

### Check each settings separately

We can check the settings **separately** by using commands like these:

```bash

# Outputs User's Username
git config user.name

# Outputs User's Email
git config user.email

# Outputs Users's color.ui settings
git config color.ui

```

- You get the idea!

>[!warning]
>Since Git might read the same configuration variable value from more than one file, it’s possible that you have an unexpected value for one of these values and you don’t know why. In cases like that, you can query Git as to the _origin_ for that value, and it will tell you which configuration file had the final say in setting that value:
>```bash
>
>git config --show-origin rerere.autoUpdate
>
>```

---

# Getting Help

These are some commands you can use to get help.

```bash

# General Help
git
# or
git help

# Manual ( man page )
man git

# Config Help
git help config

# More Precise Help usin option / arugment `-h` 
# For Example:
git add -h
git push -h
git status -h

```

>[!note] Now...
>There is always **Google**, **YouTube**, **Discord** and **AI**... *Just Saying!*

---

# Git Basics - Getting a Git Repo

After this part you should be able to:

1. Configure and Initialise a Repository
2. Begin and Stop Tracking Files
3. Stage and Commit Changes
4. Setup Git to Ignore certain Files
5. Undo Mistakes
6. Browse History of Project
7. View Changes Between Commits
8. Push and Pull from Remote Repositories

## Getting a Git Repo

There are 2 way of *getting a Git Repo*:

1. Cloning existing *Remote* Repo
2. Turn **Local Directory** into *Git Repo*

### Initialising Repo into Existing Directory / Folder

>[!note]- Need to use the Terminal!!!
>I like to **live** in the Terminal

You need to go the *directory* or *folder* where you want to initialise the Repo, then type:

```bash

git init

```

- Creates a new *sub-directory* with the name `.git`
	- This is basically a Git Repository Skeleton

Nevertheless, nothing is being **tracked** yet!

- If you want to start version-controlling existing files, you should be *tracking* those files and do an initial commit.

```bash

# Begin Staging
git add *.c
# Or could just do
git add *

```

>[!info] What is the `.c` extension?
>From what I understand; If you have many `.jpg` files. I will only check the files with the extension `.jpg`
>>[!warning] I am not sure about this
>>- Ask for help!


- Next you need to use the command:

```bash

# Adding Single File
git add File_Name

# Adding ALL Files
git add .

```

This will add the specified file to the staging area, which is **crucial** before creating a new commit!

#### Commiting

After doing all of this; we can use the command:

```bash

git commit -m "Description"

```

>[!tip]- Remember
>![[Commit Message]]

### Cloning an Existing Repository

>I think we all know how to do that... Don't kill please!

- You only need to know one thing for now

#### Command to clone any Repo

```bash

git clone <insert_url_here>

```

- Example:

```bash

git clone https://www.github.com/Sunhaloo/nvim

```

This will clone all the files from the my repository called `nvim`.

- Think of cloning as "*downloading*" ( *not sure if it is actually downloading* )

---

# Git Basics - Recording Changes to Repository

>[!tip] Remember
>Each file in your **working** directory can be in 1 of 2 *states*
>- **Tracked**
>	- Files that were in the **last** snapshot, as well as newly *staged* files. These files can be:
>		- Unmodified
>		- Modified
>		- Staged
>	- These are basically files that *Git* knows about
>- **Untracked**
>	- These include everything else that does not falls in the category *Tracked*.

## Life Cycle of Status of Files

![[git status lifecycle.png]]

## Checking Status of Files

The command use to determine the *status* of files is:

```bash

git status

```

If you run this command in your ( *new* ) working directory; you must see something like this:

```console

On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working tree clean

```

>For now, that branch is always `master`

>[!warning]
>GitHub changed the default branch name from `master` to `main` in mid-2020, and other Git hosts followed suit. So you may find that the default branch name in some newly created repositories is `main` and not `master`. In addition, the default branch name can be changed (as you have seen in [Your default branch name](https://git-scm.com/book/en/v2/ch00/_new_default_branch)), so you may see a different name for the default branch.<br><br>However, Git itself still uses `master` as the default, so we will use it throughout the book.

#### What happens if you add a file?

For example: If we add a simple `README.md` file ( *markdown is the greatest language for note taking! my opinion fuck you* ).

Then you would see:

```console

On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    README.md

nothing added to commit but untracked files present (use "git add" to track)

```

## Tracking New Files

To *track* ( *track that thing like you are going to send an 'aim-120' on it xD* ) use the command:

```bash

git add README.md

```

### Checking the *Status* again

So...

```bash

git status

```

We we be able to see that there has been a new file that has been added:

```console

On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)

    new file:   README.md

```

You can now see that the file has been <span style="color: green;">staged</span> because it wrote:

1. "Changes to be committed"
2. "use 'git restore --staged file ...' to unstage" ( *could not write file like above $\uparrow$ because it was converted to HTML -- there are work-arounds but... time* )

## Staging Modified Files

We are now going to change an already **existing** file.

So lets just say that there was a `test.py` file that was empty but we are now going to write some code into it.

```python

for x in range(5):

	print("Hello World")

```

If we save our `test.py` and use the command `git status` again! We are going to see

```console
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   test.py

```

### Adding the Modified File

To add the modified file to begin *tracking* it; we again use the command:

```bash

git add test.py

```

Now if we performed a `git status` and we are now going to see:

```console

On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   README.md
    modified:   test.py
    
```

>[!warning]
>If you go back to the `test.py` file and add something else to it; REMEMBER to **add** the file again as if you *commit* without adding; Git will add the version that was previously added.

#### Short Status

```bash

git status -s

# OR

git status --short

```

I think we all know where this is going; I just give you a simpler version of `git status`.

>I must that I do like the "*un-short*" version more
>I could have just said "*longer version*"... Fuck you!

## Ignoring Files

### Git Ignore

Sometimes you are going to have files that are you do **not** want *Git* to automatically add then for you or even show you as being **untracked**.

These are generally files such as:

- Log Files
- Files produced by build system

In these cases you can create a `.gitignore` file

#### Linux and MacOS

```bash

touch .gitignore

```

#### Windows

```powershell

New-Item .gitignore

```

### Examples of `.gitignore`

#### Example 1

```console

*.[oa]
*~

```

#### Example 2

```bash

# ignore all .a files
*.a

# but do track lib.a, even though you're ignoring .a files above
!lib.a

# only ignore the TODO file in the current directory, not subdir/TODO
/TODO

# ignore all files in any directory named build
build/

# ignore doc/notes.txt, but not doc/server/arch.txt
doc/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
doc/**/*.pdf

```

>[!info] Want A Starting Template
>There are many available for you if you want a good starting point
>Click the link below $\downarrow$ to see them
>Link: https://github.com/github/gitignore

#### Explanation of `.gitignore`'s Contents':

- `*.[oa]`:
	- *Git* will **ignore** all files that **ends** in `.o` or `.a`
		- Object and archive files that may be the product of building your code
- `*.~`:
	- This will tell *Git* to **ignore** all files whose *names* ends with `~`

>[!info] Did Not Know That!
>Text Editors such as [[Git Setup#Emacs | Emacs]] uses the `~` to **mark** *temporary files*


>[!note]
>Setting up a `.gitignore` file for **new** repository is a great way to **not** files accidentally that you did not want to commit.

### Rules for `.gitignore` Files

- Comments: `#`
- Standard *glob* patterns work, and will be applied recursively throughout the entire working tree
- Start Patterns with `/` to avoid recursivity
- End Patterns with `/` to specify directory
- Negate Pattern by starting it with an `!`

>[!note]
>#### Multiple `.gitignore` Files
>If you only have a single `.gitignore` file in the **root** directory
>	It will be applied to the entire repo recursively
>However, there is the possibility of multiple `.gitignore` files.

#### More Help

To get more help as this is a really long thing; use the command

```bash

man gitignore

```

## Viewing Staged and Unstaged Changes

If you want to know exactly what you have changed ( *not just which files were changed* ), use the command:

```bash

git diff

```

The reason you are going to use this $\uparrow$ command is to answer 2 *questions*.

1. "*What have I changed but not yet staged?*"
2. "*What have I staged that I was about to commit?*"

### Lets Go Back to Our `README.md` and `test.py` Files

Now, lets say that we edited the `README.md` and **staged** it while we only edit the `test.py` file and we do **not** *stage* it.

If we run the command <code style="color: grey;">git status</code>; we are going to get

```console

On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   README

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   test.py
	
```

But if we run the command <code style="color: red;">git diff</code>; we are actually going to only see what has **changed** but **not** *staged*

```console

diff --git a/test.py b/test.py
index 8ebb991..643e24f 100644
--- a/test.py
+++ b/test.py
@@ -65,7 +65,8 @@ branch directly, things can get messy.
 Please include a nice description of your changes when you submit your PR;
 if we have to read the whole diff to figure out why you're contributing
 in the first place, you're less likely to get feedback and have your change
-merged in.
+merged in. Also, split your changes into comprehensive chunks if your patch is
+longer than a dozen lines.

 If you are starting to work on a particular area, feel free to submit a PR
 that highlights your work in progress (and note in the PR title that it's
 
```

If you want to see what you have **staged** that will go into your next commit use <code style="color: red;">git diff <span style="color: green">--staged</span></code> *OR* use <code style="color: red;">git diff <span style="color: green">--cached</span></code>

```console

diff --git a/README b/README
new file mode 100644
index 0000000..03902a1
--- /dev/null
+++ b/README
@@ -0,0 +1 @@
+My Project

```

>[!note]
>`git diff` by itself does not show all the changes made since your last commit - **only** the changes that are still *unstaged*
>If you have *staged* all of your changes:
>	You will get **no** output!

#### Staging and Editing Again

If we **stage** the `test.py` and *then* edit it; you can use the command `git diff` to see:

- what has been staged
- what has **not** been staged ( *more like unstage* )

A little example:

- Add ( stage ) `test.py`

```bash

git add test.py

```

- Running `git status`

```console

On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    modified:   CONTRIBUTING.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

    modified:   CONTRIBUTING.md
    
```

- Running `git diff` to see what is **unstage**

```console

diff --git a/CONTRIBUTING.md b/CONTRIBUTING.md
index 643e24f..87f08c8 100644
--- a/CONTRIBUTING.md
+++ b/CONTRIBUTING.md
@@ -119,3 +119,4 @@ at the
 ## Starter Projects

 See our [projects list](https://github.com/libgit2/libgit2/blob/development/PROJECTS.md).
+# test line

```

- Running `git diff --staged` to be what we have staged so far

```console

diff --git a/test.py b/test.py
index 8ebb991..643e24f 100644
--- a/test.py
+++ b/test.py
@@ -65,7 +65,8 @@ branch directly, things can get messy.
 Please include a nice description of your changes when you submit your PR;
 if we have to read the whole diff to figure out why you're contributing
 in the first place, you're less likely to get feedback and have your change
-merged in.
+merged in. Also, split your changes into comprehensive chunks if your patch is
+longer than a dozen lines.

 If you are starting to work on a particular area, feel free to submit a PR
 that highlights your work in progress (and note in the PR title that it's
 
```

>[!info] `git diff` in an External Tool
>If you want a GUI version / External version; you can use the command `git difftool`
>To see what is available on your system run the command:
>```bash
>
>git difftool --tool-help
>
>```

### Committing Your Changes

Now that we have setup our *staging area* and is happy that the required files are staged; we can now move on to **committing**.

1. The simplest way to commit is to run the command:

```bash

git commit

```

- This will bring up your text editor
	- So that you can write good [[Commit Message | commit messages]]

2. The second way ( *i like this one more* ) is to directly write the commit message in the *terminal* itself

```bash

git commit -m "Fixed line 2 on test.py file"

```

### Skipping the Staging Area

Sometimes **staging** can be really annoying and time consuming depending on the work you are doing;

Look at my case; I sometimes, more like *rarely* push my Neovim. Thus I know that I need to add **all** of the files inside my `nvim` folder.

Thus, *Git* have thought of that and we can use the command:

```bash

git commit -a -m "Committing"

```

The argument / options `-a` will tell Git to stage every file that is already tracked before doing the commit

This means that we can all skip the `git add` part! Noice!

### Removing Files

To remove a file use the command:

```bash

git rm File_Name.ext

```

- Will also remove the file from the working directory.

If you simply remove the file from working directory, it show under "*Changes not staged for commit*" i.e **unstage** ( using the command `git status` )

### Moving Files

#### Renaming a File

To rename a file; you can use something like this:

```bash

git mv original_name new_name

```

- The same fucking thing in Linux

Running this command is similar to saying

```bash

git rm orginal_name
git add new_name

```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!