## Create, Delete, Copy, and Move Files and Directories

- ls - **l**i**s**t
- ls -a  --> List all
- ls -l /var/log --> List file and folder into list format
- ls -al --> combining flag all and list flag
- ls -alh --> a(all) l(list format) h(human readable format- shows size)

```
cd / 
cd 
touch reciept.pdf 
touch ../jane/reciept.pdf
mkdir
cp [source] [destination] 
cp -r [source] [destination] - recursive
mv [source] [destination] - move
rm filename - Delete file
rm -r invoices/ - Delete Directory

```

## Create and Manage Hard Links

An inode is a data structure that stores various information about a file in Linux, such as the access mode (read, write, execute permissions), ownership, file type, file size, group, number of links, etc. Each inode is identified by an integer number. An inode is assigned to a file when it is created.

Q -Why we need more than one hard link for data?
- Ans: Instead of copying file where it is required in other location we can hard link that will memory.

```
ln path_target_file path_to_link_file
```
- Limitation
    - Hardlinks are only applicable to file not folders
    - Only hardlink to file on same filesytem

## Create and Manage Soft Links

- Hard link point to the inode where as **soft link points to the path instead**
- Soft links are allowed for directories and other file system
```
ln -s path_target_file path_to_link_file
ln -s /home/aaron/pictures/family_dog.jpg family_dog_shortcut.jpg
readlink family_dog_shortcut.jpg
```
## Q&A

- In what form does Linux organise files and directories?  
    Ans: Filesytem Tree
- Create a soft link to /tmp directory. Create this link in /home/bob directory and call it link_to_tmp.  
    Ans: ln -s /tmp link_to_tmp
- Create a hard link to /tmp/hlink file. Create this link in /home/bob/ directory and call it hlink.  
    Ans: ln /tmp/hlink hlink / stat hlink
- There is a file called /home/bob/new_file, rename this to /home/bob/old_file  
    Ans: mv /home/bob/new_file /home/bob/old_file(Use move for rename)
- Create a directory named 9 under /tmp/1/2/3/4/5/6/7/8 directory. Please note that the structure of             sub-directories, from 1 to 8 does not exist. However, mkdir has a command line option to automatically create all of these sub-directories automatically in one shot, instead of 9 consecutive commands. This option is described in the help output or manual pages as make parent directories as needed. Find out what the correct option is and use it to create the directory in one shot.  
    Ans: mkdir -p /tmp/1/2/3/4/5/6/7/8/9
- ls -l shows you the time when a file has been last modified, but it only shows you the hour and the minute, usually in a form like 17:53. Find another way to make ls display the full/exact last modified time for the files in /home/bob directory.
At what exact time was important_file created/modified?  
    Ans: ls --full-time





