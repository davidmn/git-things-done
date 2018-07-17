# Branches

So you want to do things with branches?

## Rename a branch (even one you've already pushed)

```
git branch -m feature/some-stupid-name feature/jira-001 
git push origin :feature/some-stupid-name
git push --set-upstream origin feature/jira-001 
```

This will take your branch that had some foolish name that violated the coding standards and renames it to a nice standards conforming name.
