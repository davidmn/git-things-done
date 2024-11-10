# General

## Show git branch in terminal

Wouldn't it be nice to always see what branch you're current directory is in bash?

Add the following to your `~/.bashrc` file

```
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
```

## Push to current branch

You made your feature branch `feature/JIRA-001` and you want to push it as backup or to raise a pull request.

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

## Set your git editor to something sensible

You want a GUI for your git associated editor.

For VSCode run:

```
git config --global core.editor "code --wait"
```

For Sublime run:

```
git config --global core.editor "subl -n -w"
```

## Set a merge tool

To use VSCode as your merge/diff tool run the following:

```
git config --global merge.tool vscode
git config --global mergetool.vscode.cmd "code --wait $MERGED"
git config --global diff.tool vscode
git config --global difftool.vscode.cmd "code --wait --diff $LOCAL $REMOTE"
```

## Multiple remotes

A very specific scenario I found:

1) I have a single git repo that creates a static site (davidmn.org) with Hugo and pushes it to GitHub Pages
2) I want a second domain (megaslippers.net) that has the same content
3) I copied the repo (can't fork your own things in github?) and set-up github pages again
4) I want to push to both repos at the same time

It's easy:

```
git remote remove origin
git remote add origin git@github.com:davidmn/davidmn.org.git  
git remote set-url --add --push origin git@github.com:davidmn/megaslippers.net.git
git remote set-url --add --push origin git@github.com:davidmn/davidmn.org.git 
git push --set-upstream origin main   
```
