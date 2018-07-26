# Aliases

## aliases
```
git config --global alias.aliases "config --get-regexp alias"
```

Lists all your aliases like this:

```
$ git aliases
alias.lg log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
alias.conflicts diff --name-only --diff-filter=U
alias.aliases config --get-regexp alias
```

## lg

```
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --oneline -10"
```

Gives a pretty summary of the git history a bit like this:

```
$ git lg
*   64125fb (HEAD -> feature/JIRA-000, origin/feature/JIRA-000) Merge develop
|\
| *   7aaa902 (origin/develop, origin/HEAD, develop) Merged in feature/JIRA-000 (pull request #3319)
| |\
| | * 314zf51 JIRA-000: Do the thing!
...
```

## conflicts
```
 git config --global alias.conflicts "diff --name-only --diff-filter=U"
```

Useful when you're mid rebase and want a nice list of merge conflicts that'll look a bit like this:

```
$ git conflicts
Views/Common/Implementation/CustomerDetailsView.xaml
Views/Common/Implementation/HomeView.xaml
```
