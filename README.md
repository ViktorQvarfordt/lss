# lss

*Like `ls` but lists actual size for both files and directories.*

**l**i**s**t **s**ize


## Install

```
$ curl https://raw.githubusercontent.com/ViktorQvarfordt/lss/master/lss -o /usr/local/bin/lss
$ chmod +x /usr/local/bin/lss
```

(Or change `/usr/local/bin` to any folder that is in your `$PATH`.)


## Example

```
$ lss
 1.07 KB  LICENSE
 1.72 KB  README.md
 3.98 KB  lss
41.63 KB  .git/      48  39
48.60 KB  .          51  40

$ lss .git
   31  B  .git/COMMIT_EDITMSG
   41  B  .git/ORIG_HEAD
   41  B  .git/HEAD
   73  B  .git/description
  246  B  .git/config
  281  B  .git/index
  336  B  .git/info/           1   0
  521  B  .git/refs/           1   4
 5.04 KB  .git/logs/           2   4
15.34 KB  .git/objects/        27  26
19.26 KB  .git/hooks/          11  0
41.63 KB  .git/                48  39
```

The third and fourth columns are the number of files and subfolders inside a folder, respectively.

If you pass more than one argument, then `lss` will not list children, to support the use case `lss *jpg`.

## FAQ

**Q:** Why?<br />
**A:** Because all standard tools are terrible at this. Good luck trying to show human readable sizes that are sorted using `du`. You get stuck with `awk` and get really sad.

**Q:** How is it implemented?<br />
**A:** Python 3. No dependencies. Cross platform compatible.

**Q:** How is `lss` different from `du`?<br />
**A:** `lss` just does what you want, no flags or options. `lss` shows precise and actual file size in human readable format. It orders files and folders by size. It also lists number of files and subfolders inside folders. Furthermore `du` has annoying inconsistencies across platforms, such as `du -sb .` not working on macOS.
