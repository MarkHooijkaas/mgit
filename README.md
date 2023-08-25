# mgit: manage multiple git clones

For my work I often have to maintain 30 or more git repositories and keep them in sync.
For this I developed mgit.
It can be used to check the status, of a list of git clone,
but also to pull, push, commit, add files, etc

# example: getting a short status of all clones
If you do not specify a command, mgit will show the status.
If you do not specify one or more directories, mgit will use all directories (*) in the current directory
```
$ mgit
dirs=*
======= mgit =============
A  README.md
A  mgit
======= my-links =============
======= savv =============
======= savvy-tools =============
======= vissy =============
 M vissy
```
After moving sgit from another project (kloink), and renaming it to mgit, my output looked like this.
It shows that I have not pushed some commits to the origin
```
$ mgit
dirs=*
======= kloink =============
d6b21ef (HEAD -> master) removed sgit, since it now is in mgit repo
======= mgit =============
 M mgit
======= my-links =============
======= savv =============
======= savvy-tools =============
======= vissy =============
 M vissy
```

You can also be more explicit about which command and which directories you want to process:
```
$ mgit --status savv*
dirs=savv savvy-tools
======= savv =============
======= savvy-tools =============
```


# help
There is some basic help info available
```
$ mgit --help
Usage: mgit [options] [dir ...]

The purpose of sgit is git commands in multiple directories
Options can be:
    -h|--help          display this help and exit
    -v|--verbose       verbose mode.
    -q|--quiet         quiet mode.
    -s|--status        show git status (default)
    -m|--commit <msg>  git commit with message
    -a|--add <file>    git add one file or dir (e.g. .)
    -l|--pull          git pull
       --push          git push
    -c|--cmd <cmd>     perform any command
```
