CSSS Git Tutorial
=================

Welcome! In this tutorial you're going to learn:

- Basic command-line use
- How to install/configure git
- How to edit files in emacs/vim
- Simple git usage (diffs, commits, merges, etc.)
- How to navigate and use Github

Let's get started.

## What is Git?

## Git Setup
### Installion

### Configuration

## Github

Make a [Github](https://github.com) account if you haven't already.
What Github *is* is a site to host your code (your repos). What it *allows*
is a collaborative coding environment. Users can comment on code, create
issues (for bugs), copy repos, and merge their changes together.

The CSSS uses Github to store our documents, and you can use it
to keep all your future coding projects backed up.

## Getting to Work

### Forking this Repo

### Cloning your Fork

### Making a change

Thsi si a teriblee speld sentins.

### Commiting

#### Writing Good Commit Messages
**Advice:** Writing good commit messages is important. Future you (or a
coworker) will love you for it, trust me. Here's a terrible commit:

```
commit 2e4c6df191cdb6597464122d05adae61c314e91f
Author: Colin Woodbury <colingw@gmail.com>
Date:   Tue Sep 11 18:59:22 2012 +0900

    Fixed a bug
```

What was the problem? Where was it? How did you fix it?

Here's a good commit:

```
commit 71c26a15c9f2f763028e34c6ddde83b1763d93d0
Author: Colin Woodbury <colingw@gmail.com>
Date:   Sat Jan 3 09:19:48 2015 -0800

(Aura1): Success code given when `--needed` finds nothing to do - fixes #299

- This is what pacman does, and is helpful for scripts.
- In fixing this I found more weird behaviour:
    `pacman -S` gives 1 (bad) saying there's nothing to do.
    `aura -A` gives 0 (good) saying nothing.
```

Here we see:
- The title describes new behaviour.
- A github issue is referenced (and actually closed) by this commit.
- Some reasoning was given for the change.
- Further problems can be addressed.

### Checking the Git Log

NOTES
-----
- Forking a repo
- Cloning their fork
- Editing in emacs/vim/sublime
- Simple diffs/commits/logs
- Writing good commit messages
- Simple branch/checkout
- Adding/removing files (.gitignore)
- Amending commits

Advice
------
- COMMIT OFTEN!
- git commit -p
- Always merge while *in* master.
- Stay way from Windows.

Ideas
-----
- Make them do bad things, then show them how to fix it.
