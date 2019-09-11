# utcp
Tool to quickly copy files to remote machines

I've used this to work on projects so that I can edit on my IDE on my own computer and copy my changes to the remote, where the program can be run.

To configure the tool, edit the utcp python file
The project directory structure must be the same between both machines, and the root directory must be written as a string in place of `<root of directory>`.
The remote host name (e.g. "bob@cs.utexas.edu") must be written in place of `<remote host>`.
The base directory where the project directory resides on the remote must be written in place of `<base directory of host>`.

Example directory structure:
```
/path/to/dir
├── dirroot
│   ├── a.out
│   └── b.py
└── others
```

To copy a file or directory from dirroot to the remote, run `utcp <filename>` on the local machine.
For exmaple, if the base directory of host is `/host/base`, `utcp a.out` will copy `a.out` into `/host/base/dirroot/a.out` on the remote.

Running utcp without arguments runs `utcp .` by default.

Git files (.git/, .gitignore) are ignored so it works with git directories.
It also does not copy itself.
