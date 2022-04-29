# Use scripting to automate system maintenance tasks

- All the command we type in linux are interpreted by bash(Bourne shell).It is command line interpreter

- Scripts are instructions which are kept in file.

- Script file end with .sh
```
touch script.sh
vim script.sh
#!/bin/bash -> Shebang
```
- How to run scripts
```
/home/user.script.sh or ./script.sh
cat /tmp/script.log
```
- Use if in scripts
```
#!/bin/bash

if test -f /tmp/archive.tar.gz; then
    mv /tmp/archive.tar.gz /tmp/archive.tar.gz.OLD
    tar acf /tmp/archive.tar.gz /etc/dnf
else
    tar acf /tmp/archive.tar.gz /etc/dnf
fi

chmod +x script.sh
```
- If the command return is sucessfull it return 0 else it return non zero value

