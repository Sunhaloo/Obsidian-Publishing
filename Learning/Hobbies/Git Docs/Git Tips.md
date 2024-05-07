---
Alias: Random Git / GitHub Notes
Tag: Git, GitHub
Author: S.Sunhaloo
Date: 2024-04-04
Status: HOLD
---

## List of Contents

- [[Git Tips#What is `git pull`? | What is `git pull`?]]
- [[Git Tips#How to switch Branches | How to switch Branches]]

### My Links

- [[Git Tips#Socials | Link to Socials]]

---

# What is `git pull`?

The command `git pull` it used to fetch and download contents from a **remote** repository and immediately *update* the **local** repository.

Think of it like we are **syncing** some files.

>[!tip]- Usage
>To use this function; simply type:
>```console
>
>git pull
>
>```

# How to switch Branches

To be able to switch branches. We need to find out if / whether the repository has other branches except from `main` / `master`.

We are going to run the command below $\downarrow$ to check if the repo has any other branches.

```bash

git branch -a

```

Switching to another branch

```bash

git checkout branch_name

```

# What does `git fetch` do?

The command `git fetch` will **download** commits, files and refs from a remote repository onto your local repository.

```mermaid
graph LR;
	Remote-Repository --->|git fetch| Local-Repository
```

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!