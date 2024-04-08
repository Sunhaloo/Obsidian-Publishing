---
Alias: Change Branch Name from CLI
Tag: Git, GitHub
Author: S.Sunhaloo
Date: 2024-02-28
Status: Completed
---

# Medium Article

I found this Medium article when search on this topic. Click [here](https://medium.com/geekculture/how-to-change-the-name-of-the-principal-git-branch-4dd39a620ad8) to visit the website.

# Steps

Again, I will polish / learn this later, but for now, I will only be writing this quickly, so that I can finally do my work.

## See Current Branch Name

```bash

git status

```

After running this command; you will see something like

```console

On Branch master

```

>Basically something "*master*" or nowadays "*main*".

## Checking other Branches of the Repository

To check all the other branches found in the repository. We can use the command:

```bash

git branch

```

>Simple Enough!

## "*Moving*" / Renaming the Branch

>[!note]
>The guy who wrote this "*blog*", does not write well; like I do not really understand what he is writing. Like some commands are bold and some are not. <span style="color: orange">Hence, the content below might contain some errors.</span>

```bash

git branch --move old_branch_name new_branch_name

```

>[!warning]
>This will only change a **local** change. Follow the next step to actually change the branch name on the *remote repository*.


## Push "*renamed branch*" to Remote Repository

```bash

git push --set-upstream origin main

```

### Finally

We can check it with the command ( *again* ):

```bash

git status

```

>[!note]
>This *note* is not completed.
>1. Because I do not really know what I am doing
>2. I copied some random guy on the Internet
>	- Like I did not even look at the **[GitHub](https://docs.github.com/en)** Documentation

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!