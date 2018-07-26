# General

## Push to current branch

You I've made your feature branch `feature/JIRA-001` and you want to push it as backup or to raise a pull request.

You type `git push` but OH NO! git is unhappy!

```
$ git push
fatal: The current branch feature/JIRA-001 has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin feature/JIRA-001
```

Easy solution. Set this in the config:

```
git config --global push.default current
```

Push again and all should be well.
