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
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

Gives a pretty summary of the git history a bit like this:

```
$ git lg
*   e52311c - (HEAD, origin/develop, origin/HEAD, develop) Merged in feature/jira-001 (pull request #123) (11 hours ago) <Alice>
|\
| * 313ade1 - (origin/feature/jira-001) jira-001: Add customer view (21 hours ago) <Alice>

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
