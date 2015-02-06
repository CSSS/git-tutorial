CSSS Git Tutorial
=================

Welcome! In this tutorial you're going to learn:

- Basic command-line use
- How to install/configure git
- How to edit files in emacs/vim
- Simple git usage (diffs, commits, etc.)
- How to navigate and use Github

Let's get started.

## What is Git?

## Git Setup
### Installion

Programs in Linux are never downloaded and installed from websites like
they are with Windows or Mac. Every Linux distribution has a
*package manager*, which when asked for a program, downloads it and
its dependencies from the central servers of your distro and installs them
exactly where your system expects them to be in order to be used.

#### Manjaro (Arch Linux)
Manjaro is a child of Arch, meaning they share a lot, including a package
manager. Do the following in a terminal to get git:

    pacman -S git

`-S` means *sync* and will download any package you ask it for.

#### Mint / Ubuntu / ElementaryOS (Debian)
All these three are actually children of the very first Linux distribution,
Debian. Hence they all use the same packaging software. Do the
following in a terminal to get git:

    apt-get install git

These distros also have graphical packaging software, but for now
let's get used to using the command line.

### Configuration
Git needs to know who you are. Enter the following two commands
into your terminal:

```
git config --global user.name  "Your Name"
git config --global user.email "you@whatever.com"
```

Every time you make a commit with git, your information will be
associated with that commit. This makes it very clear who
changed what and when in a project.

## Github

Make a [Github](https://github.com) account if you haven't already.
What Github *is* is a site to host your code (your repos). What it *allows*
is a collaborative coding environment. Users can comment on code, create
issues (for bugs), copy repos, and merge their changes together.

The CSSS uses Github to store our documents, and you can use it
to keep all your future coding projects backed up, including
code you write for your classes.

Q: *But shadowy CSSS git tutorial narrator, why would I want to put
all my code up on the internet? Won't people find my stuff and
copy it?*

A: Github actually has a
[student pack](https://education.github.com/pack) which gives
you loads of free access to various web services. Notably:

* Free Github Micro Account (5 Private Repos. No one else can see your code.)
* $100 credit for DigitalOcean (web hosting. Their cheapest server is $5/month, meaning you get 20 months to do whatever you want with a server.)
* Free `.me` domain name for a year with Namecheap.

## Getting to Work
### Forking this Repo
In the top-right corner of this Github page you should see a button
labeled `Fork`. Click it.

You now have a perfect copy of this repo that exists on your Github
account. You can do whatever you want to it.

*Forking* generally means one of two things:

1. Taking a project, copying it, and taking it in a new
direction for philisophical/political reasons, or;
2. Making a copy of it on Github.

### Cloning your Fork
Move back to your terminal. We're now going to clone to the repo
you just forked.

*Cloning* is the process of copying a remote repo (like on Github)
to your own machine to work on.

Using `cd` (change directory), move to a directory using you'd like
your clone to be in, and enter the following:

    git clone https://github.com/your-github-account/csss-git.git

Use `ls` and you should see the `csss-git` folder. It contains the
contents of the repo. You can make whatever changes you want to it;
nothing on Github will be affected until you make a `git push`.

### Making a change

Thsi si a teriblee speld sentins.

Fix the sentence above in an editor of your choice. We
recommend `emacs`, `vim`, or Sublime Text. In particular,
`emacs` and `vim` run in the terminal. Since you're going to
be spending a lot of time there, you might as well get used to
them.

#### Emacs
`C` refers to your `control/ctrl` button.

* Save a change: `C-x C-s`
* Leave emacs: `C-x C-c`

#### Vim
In vim you have to type `i` to enter *Insert Mode* before you
can type. `Esc` puts you back into *Normal Mode*. You need to
be in *Normal Mode* to run the commands below:

* Save a change: `:w`
* Leave vim: `:q`

### Checking your Changes
Use `git diff` to see what changes you've made since your last commit.

### Commiting
When you want to track a new file you've added to your project,
use `git add thefilenamehere`. Since `README.md` is already tracked
by the project, we can just use `git commit -a`, which prepares
all files you've changed this time around to be commited.

`git commit` will open up an editor for you to write a commit
message in. One you do so, and then save and leave, the commit
will be made.

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
Now that you've made a commit, let's check confirm it with
`git log`. You should see a list of all the recent commits,
with the one you just made at the top.

### Editing/Deleting Commits
If you screwed up your latest commit message, you can change it
with `git commit --amend`.

However we're going to completely delete the commit you just
made. Remember `HEAD` from *Learn Git Branching*? Here are
two handy commands:

* `git reset --hard HEAD`: Deletes all your *current* uncommited changes.
* `git reset --hard HEAD^`: Deletes your latest commit.

Do the second one to kill your commit.

### Add your Name
That's pretty much all we have to teach you right now. There's more of
course, but this was a good start. See the file `COMPLETED.md`? Add your
name and the date to it, and commit the change.

### Push to your Fork
The commit you made is local to your machine. By *Pushing*, we can sync your
Clone and your Fork, and your new commit will then be on Github too.

    git push origin master

### Make a Pull Request
Okay, the commit is now in your Fork too. But its still not in the
original repo you copied in the first place. By making a *Pull Request*
from your Fork you can ask the maintainers of the original repo
to merge your changes into the master project.

On your Fork's page on Github, there should be a Green button near
the upper-left. Click that, then hit *Create Pull Request* on the
next page. This will create a new *Issue* in the main repo,
where everyone can discuss your commits. The maintainers
may ask you to make further changes before they merge.

### You're Done!
Pretty soon the `csss-git` repo maintainers should merge your commit
in, and you'll be forever remembered for having completed this tutorial.

The above process is how modern collaborative software development
is done. By getting a handle on it now, you'll have a head-start
in your co-op placements and other real job placements. Good luck!
