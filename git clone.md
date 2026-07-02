# Git Clone
------------------------------------------------------------------------------------
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/a09864be-e2ad-4cf9-a401-bf1ff0f1dbd9" />


## Imagine this real-world scenario

You're hired as a Java Full Stack Developer.

It's your first day.

Your Team Lead says

> "Sai, clone the project and run it locally."

He doesn't say

> "Create a repository."

He doesn't say

> "Write Git commands."

He simply says

> **Clone the repository.**

Why?

Because the project already exists.

Someone has already spent months or years building it.

Your job is to download the entire project.

That is exactly what **git clone** does.

------------------------------------------------------------------------

# What is git clone?

**Definition**

`git clone` creates an exact copy of a remote Git repository on your
local computer.

It downloads

-   Source code
-   Git history
-   Branches
-   Commit history
-   Tags
-   Remote configuration

Everything.

Think of it as

> "Download the entire software project."

------------------------------------------------------------------------

# Before clone

Remote Repository

    GitHub

    Inventory Management System

    ├── src
    ├── pom.xml
    ├── README.md
    ├── .git
    ├── commits
    ├── branches
    └── history

Nothing exists on your laptop.

------------------------------------------------------------------------

# After clone

    Your Laptop

    Inventory Management System

    ├── src
    ├── pom.xml
    ├── README.md
    ├── .git
    ├── commits
    ├── branches
    └── history

Now your laptop has everything.

------------------------------------------------------------------------

# Command

``` bash
git clone https://github.com/company/project.git
```

or

``` bash
git clone git@github.com:company/project.git
```

------------------------------------------------------------------------

# What happens internally?

When you type

``` bash
git clone
```

Git performs several operations automatically.

### Step 1

Connects to GitHub.

    Laptop
         |
         |
         v
    GitHub

------------------------------------------------------------------------

### Step 2

Downloads every commit.

Suppose there are

    Commit 1

    Commit 2

    Commit 3

    Commit 4

    Commit 5

Git downloads all five.

Not just the latest files.

It downloads history.

------------------------------------------------------------------------

### Step 3

Downloads every branch.

Suppose repository contains

    main

    development

    feature/login

    feature/payment

    release

    hotfix

Git downloads references to all branches.

------------------------------------------------------------------------

### Step 4

Creates hidden

    .git

folder.

This is the brain of Git.

Inside it stores

-   commit history
-   branch info
-   objects
-   logs
-   references
-   configuration

------------------------------------------------------------------------

### Step 5

Checks out the default branch.

Usually

    main

or

    master

Your working directory becomes

    project/

    src/

    pom.xml

    README.md

Ready to work.

------------------------------------------------------------------------

# How many times do we clone?

This is one of the biggest misconceptions.

Many beginners think

    git clone
    git clone
    git clone
    git clone

No.

In real companies,

## Usually only ONCE.

Example

Day 1

    git clone

Done.

After that,

Never again.

------------------------------------------------------------------------

# Why only once?

Because the project already exists on your laptop.

You don't need to download it again.

Instead,

You simply update it.

We'll learn that using `git pull` later.

------------------------------------------------------------------------

# Real-world timeline

## Monday

    git clone

------------------------------------------------------------------------

Tuesday

Open project.

    Code
    Commit
    Push

------------------------------------------------------------------------

Wednesday

    Code
    Commit
    Push

------------------------------------------------------------------------

Thursday

    Code
    Commit
    Push

------------------------------------------------------------------------

Friday

    Code
    Commit
    Push

Notice?

Only one clone.

------------------------------------------------------------------------

# When do we clone again?

There are only a few situations.

------------------------------------------------------------------------

## Scenario 1

New laptop.

Old laptop broke.

Buy new laptop.

Clone again.

    git clone

------------------------------------------------------------------------

## Scenario 2

Deleted the project accidentally.

    rm -rf project

Clone again.

------------------------------------------------------------------------

## Scenario 3

Working on another computer.

Office PC

↓

Home PC

↓

Personal Laptop

Need clone on each computer.

------------------------------------------------------------------------

## Scenario 4

Joining another project.

Project A

    git clone

Project B

    git clone

Project C

    git clone

Each repository is cloned once per machine.

------------------------------------------------------------------------

# Real company example

Suppose your company has

    Banking App

    Employee Portal

    HR Portal

    Admin Dashboard

    Notification Service

    Payment Service

You'll clone each project once.

Example

    git clone banking-app

    git clone hr-portal

    git clone employee-service

    git clone payment-service

Each one only once.

------------------------------------------------------------------------

# Common beginner mistake

They think

    Morning

    git clone

    Evening

    git clone

    Tomorrow

    git clone

Wrong.

Once the project exists,

Don't clone again.

------------------------------------------------------------------------

# What if new code is added by teammates?

Imagine

Monday

You cloned.

Tuesday

Your teammate added

    10 new files

How do you get them?

Do you clone again?

No.

You use

    git pull

That is why `git pull` exists.

------------------------------------------------------------------------

# Simple analogy

Think of GitHub like Google Drive.

The repository is a folder stored online.

`git clone`

means:

> Download the folder for the first time.

After downloading,

When someone updates the online folder,

you don't download the entire folder again.

You **sync** the changes.

That synchronization is `git pull`.

------------------------------------------------------------------------

# A senior developer's advice

During my career, I've seen many new developers accidentally clone the
same repository multiple times into different folders because they
didn't realize the existing local copy could simply be updated. This
leads to confusion about which copy contains their latest work.

A good habit is:

-   Clone each repository **once per machine**.
-   Keep that local copy organized in a dedicated workspace (for
    example, `~/workspace` or `D:\Projects`).
-   Use that same copy every day.
-   Update it with `git pull` (or another team-approved workflow)
    instead of cloning again.

------------------------------------------------------------------------

## What you've learned

-   `git clone` downloads a complete repository for the first time.
-   It includes the project files, commit history, branches, tags, and
    Git metadata.
-   You normally run `git clone` **only once per repository on each
    computer**.
-   You clone again only when using a new machine, after deleting the
    local copy, or when working with a different repository.
-   After the initial clone, you keep the local copy updated rather than
    downloading it again.

------------------------------------------------------------------------

In the next lesson, we'll cover **`git pull`** in depth: what it
actually does, how often it's used in real companies, when to run it
during the day, what happens if you don't pull, merge conflicts, and the
workflows followed by experienced development teams.
