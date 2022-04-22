# List, set, and change standard file permissions

- chgrp group_name file/directory (**ch**ange **gr**ou**p**)

- sudo chown username:group file (**ch**ange **own**er)


## File and Directory Permission(-rwxrwxrwx)
     

| File Type     | Identifier |  
| ------------- | ---------- |
| Directory     | d          | 
| Regular file  | -          |
| Charcter Device  | c          |
| link          | l         |
| socket file   | s          | 
| Pipe          | s          | 
| Block Device  | b          | 

- rwx(user) rwx(group) rwx(other)

| Bit| Purpose |  
| ---| ---------- |
| r  | **R**ead File         | 
| w  | **W**rite File        |
| x  | E**x**ecute File      |
| -  | No Permission         |

## Evaluating Permission

- Suppose example permission -r--rw---- breaking into user ,group and other user>r-->Read only group>rw->Read and write other(---) no permissions  
- Permission are evaluated from left to right which mean if user is part of group and it has read only permission where as group has read write the user will not be able to write file as permission are evaluated left to right.  

## Add Permissions

- chmod permission file/directory

|       | Option                | Example           |  
| ------| ----------------------|-------------------|   
| user  | u+                    | u+w / u+rw / u+rwx|
| group | g+                    | g+w / g+rw / g+rwx|
| other | o+                    | o+w / o+rw / o+rwx|

```
chmod u+w family_dog.jpg

```
## Remove Permission

|       | Option                | Example           |  
| ------| ----------------------|-------------------|   
| user  | u-                    | u-w / u-rw / u-rwx|
| group | g-                    | g-w / g-rw / g-rwx|
| other | o-                    | o-w / o-rw / o-rwx|

```
# Remove Read Permissions from other
chmod o-r family_dog.jpg
```

## Setting Exact Permission

|       | Option                | Example           |  
| ------| ----------------------|-------------------|   
| user  | u=                    | u=w / u=rw / u=rwx|
| group | g=                    | g=w / g=rw / g=rwx|
| other | o=                    | o=w / o=rw / o=rwx|

- u=[list of permissions]
```
# If you want exact read permission
chmod g=r family_dog.jpg
# if you want to remove all permission
chmod g= family_dog.jpg
chmod g-rwx family_dog.jpg
```
## Octal Permissions

| Binary        | Decimal |  
| ------------- | ---------- |
| 000     | 0          | 
| 001     | 1          |
| 010     | 2          |
| 011     | 3          |
| 100     | 4          | 
| 101     | 5          | 
| 110     | 6          |
| 111     | 7          |

| Permission    | Value      |  
| ------------- | ---------- |
| r     | 4          | 
| w     | 2          |
| x     | 1          |

- Permission - rw-|r--|--- > 110|100|000 > 640 > **chmod 640 file_name**

| rw-    | r--        | ---    |
| -------| ---------- | ------ |
| 4+2+0  | 4+0+0      | 0+0+0  |
| 6      | 4          | 0      |

| rwx    | r-x        | r-x    |
| -------| ---------- | ------ |
| 4+2+1  | 4+0+1      | 4+0+1  |
| 7      | 5          | 5      |

## Q&A

- What command removes the write permission for the group from a file?
```
chmod g-w some_file
```
- Create a directory named LFCS under bob's home directory and update its user owner permissions to only x (execute), and group and others should not have any permissions.
It should give us a permission denied error while listing the contents of the directory.
```
sudo mkdir /home/bob/LFCS
sudo chmod 0100 /home/bob/LFCS
```
- Update the permissions for some_directory to rwxr-xr-x
```
chmod 755 some_directory/
```
