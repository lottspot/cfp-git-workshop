# Building useful history

## It's all about commits

The closer you adhere to these guidelines, the more useful your history will be:

- All commits should be **atomic**
- Smaller commits are almost always better commits
- A useful message *must* describe **why** the change was made
- A useful commit message *may* also summarize the change itself

## When your changes are neither small or atomic, but you still want your commits to be

### Useful commands

- `git add -p`

### Configure the lab branch

```
git checkout git-add-p
git apply changes.patch
```

## When you forgot to add a file to your last commit

Also when:

- You didn't make an atomic commit and you'd like to fix that

### Useful commands

- `git commit --amend` **!!!!!**

### Configure the lab branch

```
git checkout git-commit-amend
git apply changes.patch
```

## When your changes aren't ready to commit, but someone else's need to be merged in

Also when:

- You want to checkout another branch, but you aren't ready to commit your changes (and don't want to lose them!)

### Useful commands

- `git stash`
- `git stash pop`

### Configure the lab branch

```
git checkout git-stash
git apply changes.patch
```

## Merge conflicts: Facing the inevitable

Also when:
- Conflicts can happen using `git rebase`
- Conflicts can happen using `git stash pop`

### Configure the lab branch

```
git checkout -b git-conflicts conflict-path-a
git merge conflict-path-b
```

### Reset the lab branch for a clean go

```
git stash
git stash drop
git checkout master
git branch -D git-conflicts
```

# Making use of history

## When you want to inspect all changes ever

### Useful commands

- `git log`
- `git log --pretty=oneline`
- `git log -p`
- `git show`
- `git grep`
- `git blame`

### Open the lab branch

```
git checkout git-history
```

## When you accidentally deleted a file, or you want an older copy of a file

### Useful commands

- `git checkout`

## When something changed, everything exploded, and you need to go back to happier times

### Useful commands

- `git revert`

## When you're feeling particularly courageous (see synonym: foolish) and you want to do things that can never be undone

### Useful commands

- `git reset --hard` **!!!!!**

# Making real life use of history

## Solo work

When working solo projects, git history is mostly useful for the purpose of protecting
yourself from yourself. Common mishaps, such as:

- Oops, I didn't mean to delete that file
- Ok so I changed this file to do this thing differently, but turns out I liked the first way more
- That changed seemd ok when I tested it, but everyting just exploded when I deployed it

are easily addressed by maintaining a good commit history, and knowing how to navigate it. Less common,
but equally practical benefits of maintaining quality git history for your solo projects include:

- **Introducing collaborators**: If someone later joins you in contributing to the project, you are
  immediately reaping the benefits of using git history on collaborative projects (for spoilers, see ensuing section)
- **Handing off your project**: If someone else has to pick up the baton from you, their life will be about a billion
  times easier with quality change history to refer to

## Collaboration

When collaborating with others, the most valuable benefit provided by building quality git
history derives from the fact that every change will have 3 crucial pieces of information
attached to it:

1. What changed
2. Who changed it
3. Why was it changed

For anyone with experience collaborating with others, the pragmatic value of having this
information available for every single change ever made to a project is self-evident.
