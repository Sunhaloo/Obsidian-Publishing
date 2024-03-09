---
Alias: The Odin Project-HTML-Commit-Message
Tag: HTML, TheOdinProject, basics
Author: S.Sunhaloo
Type: HTML - Commit Message
Date: 2023-11-12
Status: Completed
---

>Messages need to be:
>- Clear, Concise and To The Point!

# What is a Commit Message?

- It is a *message* that explains the **change** *you* made to your project.

It is really important to be able to communicate well with other people so that they can help you if need be.

## Why the Importance?

- When applying for jobs, employers will look at your commit message and if you know what you are talking about; you will be able to stand out from the rest of the candidates
- Allows you and / or other developers to see what changes were made and why!
- For Yourself; if you have been away for some time on a project, you will be able to get right back on track in no time as you *documented* yourself with the commit messages

## BAD v/s GOOD Commits

### BAD Commits

```git

fix a bug

```

- The message is too **vague**
- Has no **significant** meaning behind it
- Might lead to more confusion

### GOOD Commits

```git

This is the change I made to the codebase; Explain change...

```

```git

Title

Decription

```

```git

Add missing link and alt text to the company's logo

Screen readers won't read the images to users with disabilities without this information

```

Good Commits Messages does the following things:

- Provides a subject that specifies your code’s action (e.g., “Add missing link and alt text to the company’s logo”)
- Contains a body that provides a concise yet clear description of why the commit needed to be made (e.g., “Screen readers won’t read the images to users with disabilities without this information”)
- Separates the subject from the body with a new/blank line. This is a best practice we highly recommend following. It makes commit messages easier for other developers to read.