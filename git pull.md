# Git Pull
-------------------------------------------------------------------------
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/8c4760b6-f6d9-405b-a570-6f6a7b313158" />

--------------------------------------------------------------------------

# What is git pull?

**Definition** 

`git pull` downloads the latest changes from the remote repository and
updates your local repository.

Think of it as

> "Bring my project up to date with what my teammates have pushed."

------------------------------------------------------------------------

# Why do we need git pull?

Imagine you're working in a team of five developers.

    Rahul
    Priya
    John
    Sai (You)
    Ankit

Everyone is working on the same project.

You cloned the repository on Monday.

    GitHub
           ↓
    git clone
           ↓
    Your Laptop

Everything is fine.

------------------------------------------------------------------------

# Tuesday Morning

While you were sleeping,

Rahul pushed

    Login Bug Fix

Priya pushed

    Dashboard UI

John pushed

    Payment Feature

Now GitHub has changed.

But...

Your laptop still has yesterday's version.

    GitHub

    Version 25

    ↓

    Your Laptop

    Version 22

You're behind.

------------------------------------------------------------------------

# What should you do?

You don't clone again.

You simply run

``` bash
git pull
```

That's it.

Git downloads only the missing changes.

------------------------------------------------------------------------

# What actually happens internally?

When you type

``` bash
git pull
```

Git performs two operations automatically.

    git fetch

    +

    git merge

So,

    git pull

    =

    git fetch

    +

    git merge

Later we'll study `fetch` and `merge` separately.

For now,

Remember this.

------------------------------------------------------------------------

# Step 1 --- Fetch

Git contacts GitHub.

    Laptop

    ↓

    GitHub

It checks

"Has anything changed?"

If yes,

It downloads the latest commits.

It does **not** immediately change your working files.

------------------------------------------------------------------------

# Step 2 --- Merge

Now Git merges those downloaded changes into your current branch.

After merging,

Your project becomes updated.

------------------------------------------------------------------------

# Example

Yesterday

    Project

    Login

    Dashboard

    Profile

Today your teammate adds

    Payment Module

You run

``` bash
git pull
```

Now your project becomes

    Project

    Login

    Dashboard

    Profile

    Payment Module

No need to download the whole repository again.

Only the new changes.

------------------------------------------------------------------------

# Real-world company workflow

Imagine it's 9:30 AM.

You enter the office.

What's the first Git command many developers run?

``` bash
git pull
```

Why?

Because many teammates may have pushed code after you left yesterday.

You always want to start with the latest code.

------------------------------------------------------------------------

# Typical developer routine

### 9:30 AM

Open laptop.

    git pull

Latest code downloaded.

### 10:00 AM

Start coding.

### 12:30 PM

Commit changes.

### 1:00 PM

Push your work.

### 4:00 PM

Need another feature from your teammate?

Run

    git pull

Again.

### 6:00 PM

Push today's work.

Notice something?

`git clone`

    Once

`git pull`

    Many times

------------------------------------------------------------------------

# How many times do developers use git pull?

There is no fixed number.

It depends on the project.

Sometimes

    1 time

Sometimes

    3 times

Sometimes

    10 times

per day.

------------------------------------------------------------------------

# Large companies

Imagine you're working at a company with

100 developers.

Every few minutes,

someone pushes code.

Example

    Developer A

    ↓

    Push

5 minutes later

    Developer B

    ↓

    Push

10 minutes later

    Developer C

    ↓

    Push

If you're working on related code,

you may pull several times during the day to stay up to date.

------------------------------------------------------------------------

# Small startup

Suppose only two developers work on the project.

    You

    Friend

Maybe your friend pushes only once today.

Then

    git pull

once is enough.

------------------------------------------------------------------------

# Real-world scenarios

## Scenario 1 --- Morning

You come to work.

Run

``` bash
git pull
```

Always.

## Scenario 2 --- Before starting a new task

Your Team Lead says

> "Rahul completed the authentication module."

Before using it,

Run

    git pull

Now you have Rahul's latest code.

## Scenario 3 --- Before pushing your changes

Suppose

You worked for five hours.

Meanwhile,

three teammates pushed new commits.

If you push immediately,

Git may reject your push because the remote repository has newer
commits.

So first,

``` bash
git pull
```

Resolve any merge conflicts if needed.

Then

``` bash
git push
```

## Scenario 4 --- After lunch

Your teammates merged several pull requests.

You need their latest changes.

Run

    git pull

## Scenario 5 --- Before testing

You want to make sure you're testing the latest version.

Run

    git pull

------------------------------------------------------------------------

# What happens if you don't pull?

Suppose

GitHub

    Version 50

Your Laptop

    Version 45

You continue coding.

Now you try

``` bash
git push
```

Git replies

    Rejected

    Remote contains work that you do not have locally.

Git is protecting the project.

It doesn't want to overwrite your teammates' work.

------------------------------------------------------------------------

# Can git pull cause conflicts?

Yes.

Imagine

Rahul changes

    User.java

    Line 25

At the same time,

you also change

    User.java

    Line 25

When you run

``` bash
git pull
```

Git doesn't know which version to keep.

This is called a

    Merge Conflict

We'll learn how to resolve merge conflicts in a dedicated lesson.

------------------------------------------------------------------------

# Common beginner mistake

Many beginners think

    I cloned yesterday.

    That's enough.

No.

The repository changes every day.

Your local copy becomes outdated unless you update it.

------------------------------------------------------------------------

# Clone vs Pull

  -----------------------------------------------------------------------
  Git Clone                             Git Pull
  ------------------------------------- ---------------------------------
  First download                        Update existing project

  Used once per machine                 Used regularly

  Creates a local repository            Updates the existing repository

  Downloads the full repository         Downloads only new changes

  Used when the project doesn't exist   Used when the project already
  locally                               exists locally
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# Simple analogy

Imagine your phone.

When you buy a new phone,

you download an app for the first time.

That is like

    git clone

Later,

the app receives updates.

You don't uninstall and download it again.

You simply update it.

That update is

    git pull

------------------------------------------------------------------------

# A senior developer's advice

One of the best habits you can develop is to start your workday by
updating your local repository. Working on outdated code increases the
chances of merge conflicts and integration issues.

Also, avoid running `git pull` blindly if you have uncommitted changes.
Either commit your work or temporarily save it (using techniques we'll
learn later, such as `git stash`) before pulling. This keeps your local
work safe and makes the update process smoother.

------------------------------------------------------------------------

## What you've learned

-   `git pull` updates your local repository with the latest changes
    from the remote repository.
-   Internally, `git pull` performs a `git fetch` followed by a
    `git merge`.
-   Unlike `git clone`, `git pull` is used repeatedly throughout the
    life of a project.
-   Developers commonly run `git pull` at the start of the day, before
    beginning new work, before pushing, or whenever they need teammates'
    latest changes.
-   If your local copy is outdated, Git may reject your push until you
    first pull and integrate the latest remote changes.
-   Pulling can sometimes produce merge conflicts if the same code was
    modified in both your local branch and the remote branch.

------------------------------------------------------------------------

### Next Lesson

We'll cover **`git fetch`** in depth.

This is where many beginners get confused: - What is `git fetch`? - Why
does it download changes but not update your files? - What is the
difference between `git fetch` and `git pull`? - Why do many senior
developers prefer `git fetch` first instead of `git pull`?

This is one of the most important Git concepts for working confidently
on real software projects.
