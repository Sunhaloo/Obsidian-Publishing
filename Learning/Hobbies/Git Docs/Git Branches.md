---
Alias: Branches in Git
Tag: Git, GitHub
Author: S.Sunhaloo
Date: 2024-04-12
Status: Completed
---

## List of Contents

- [[Git Branches#Create New Branch | Create New Branch]]
- [[Git Branches#Delete a Branch | Delete a Branch]]
- [[Git Branches#Change Branch Name| Change Branch]]

---

### My Links

- [[Git Branches#Socials | Link to Socials]]

---

# Create New Branch

This part of the note will show you how to create a branch locally and then push it to remote / [GitHub](https://www.github.com).

>[!warning]
>Before we do anything; we need to make sure that our Local and Remote repository are *synced*. To be able to do that we need to use the command `git pull`.

>All the things that we will be doing if going to require the use of the Terminal / PowerShell / Bash / *Fuck You*.
>I think you get the point.

### Check all the branches in a Repository

To check all the branches that are found in a repository ( *local* / *remote* ); use the command:

```bash

git branch

```

### Create and Switch to New Branch

```bash

git checkout -b new_branch_name

```

### Push New Branch to GitHub / Remote Repository

```bash

git push -u origin new_branch_name

```

---

# Delete a Branch

Again we start with our little `git pull` command to sync everything up with our remote and local repository.

>[!note]
>Git will **not** let use *delete* a branch that we are currently on!
>Make sure that you are **not** in that branch when deleting it.

## Delete Branch Locally

This one is also simple! To delete a branch **locally**, we use the command:

```bash

git branch -d branch_name

```

## Delete Branch Remotely / GitHub

To remove that *branch* from GitHub / Remote "*thing*". We are going to run the command:

```bash

git push origin --delete branch_name

```

OR similarly, we can use:

```bash

git push origin :branch_name

```

>I prefer the first version of this command!

>[!tip]
>If you encounter an errors like:
>```bash
error: unable to push to unqualified destination: remoteBranchName The destination refspec neither matches an existing ref on the remote nor begins with refs/, and we are unable to guess a prefix based on the source ref. error: failed to push some refs to 'git@repository_name'
>```
>This means that someone has **already** removed / deleted the branch.
>To synchronise your branch using `git fetch -p`

---

# Change Branch Name

Again first thing first, we need to run the command `git pull` to synchronise both the local and remote repository.

### Switch to Branch that Needs to be Renamed

```bash

git checkout old_branch_name

```

### Rename the Branch

```bash

git branch -m new_branch_name

```

### Verify the Branches

We need to check if we have actually changed the branch name.

```bash

git checkout branch -a

```

### Remote Repo: Delete Old Branch Name

```bash

git push origin --delete old_branch_name

```

### Remote Repo: Push New Branch Name to GitHub / Remote Repository

```bash

git push -u origin new_branch_name

```

---
# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!