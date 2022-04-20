## Remote text-mode login

ssh - Secure SHell

Server (ssh daemon) --------> ssh client
Windows - putty

```
ssh username@ipaddress
```
Note: linux also supports rdp

## Read and Use System Documentation

- Use '--help' flag to get help on command
```
ls --help
man man
```
- apropos command will help you search in man pages
```
apropos director
```
- Use tab to get suggestions

## Lab Question

- The ssh command has an option to display its version number. Use man to find out what is the correct command line option. 
```
man ssh
ssh -V
```
- Find out using which command you can change the static hostname of your Linux system.

```
apropos hostname
hostnamectl --help
```
- You are trying to use ssh alex@localhost to log in through SSH. Your connection is refused. ssh has a command line option to show you the verbose output. That will show a lot more status messages and help you debug why this connection is failing. What is the correct option for that? (you need not to make ssh connection work at this point)

```
man ssh
ssh -v alex@localhost
```
- How many hidden files are there in /home/bob/data/ directory?
```
ls -la /home/bob/data/
```
- We are trying to run apropos ssh command to get some details about the commands related to ssh but we are getting this error:ssh: nothing appropriate.
```
sudo mandb
```