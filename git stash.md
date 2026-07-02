# Git Stash
----
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0042668e-4eb9-4403-aae6-b77400591d45" />

---

## What is Git Stash?

**Definition**

`git stash` temporarily saves your uncommitted changes and restores your working directory to a clean state.

Think of it as:

> "Pause my current work safely so I can work on something else."

---

## Why do we need Git Stash?

Imagine you're working on a new feature.

```text
UserService.java

✓ Added new methods
✓ Modified existing code
✓ Haven't committed yet
```

Suddenly your Team Lead says:

> "Sai, production has a critical bug. Fix it immediately."

Your work is incomplete. You don't want to commit half-finished code or lose it.

This is where `git stash` helps.

---

## Basic Command

```bash
git stash
```

Temporarily saves your uncommitted changes and makes your working directory clean.

---

## Real-World Workflow

1. Start working on a feature.
2. An urgent production bug arrives.
3. Run:

```bash
git stash
git checkout main
```

4. Fix the bug.
5. Commit and push.
6. Return to your feature branch:

```bash
git checkout feature/payment
git stash pop
```

Continue exactly where you left off.

---

## Useful Commands

### Save changes

```bash
git stash
```

### List stashes

```bash
git stash list
```

### Restore without deleting

```bash
git stash apply
```

### Restore and remove

```bash
git stash pop
```

### Delete one stash

```bash
git stash drop stash@{0}
```

### Delete all stashes

```bash
git stash clear
```

### Create a named stash

```bash
git stash push -m "Payment Feature Work"
```

---

## Git Stash vs Git Commit

| Git Stash | Git Commit |
|------------|------------|
| Temporary storage | Permanent history |
| No project history | Creates project history |
| Unfinished work | Finished work |
| Local only | Can be shared after push |

---

## Best Practices

- Use Git Stash for temporary interruptions.
- Don't use it as long-term storage.
- Commit completed work instead of stashing it.
- Name important stashes for easier identification.

---

## What You've Learned

- `git stash` temporarily saves uncommitted changes.
- `git stash list` shows saved stashes.
- `git stash apply` restores without deleting.
- `git stash pop` restores and removes the stash.
- `git stash clear` removes every stash.
- Git Stash is meant for temporary work, while commits are permanent.
