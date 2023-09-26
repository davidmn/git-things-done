# WSL

If you're running WSL but your code lives in `/mnt/c` you can add this to `/usr/local/bin/git` to speed up git operations by switching between Linux and Windows gits based on the path:

```bash
#!/bin/sh

if pwd | grep /mnt/c > /dev/null; then
    exec git.exe "$@"
else
    exec /usr/bin/git "$@"
fi
```
