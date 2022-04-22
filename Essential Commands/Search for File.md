# Search for files

```
find [/path/to/directory] [search_parameter]
````


#### name parameter

```
find -name felix
```
#### use -i for case insensitive
```
find -iname felix
```
#### Wildcard expression
```
find -name felix "f*"
```
#### Search Parameter - Modified time
```
find -mmin 5 # modified minute
find -mtime 2 # 24 hour period
```
#### Change time - changed metadata or permissions
#### Search parameter - file Size
```
find -size [size]
find -size 512k
find -size +512k
find -size -512k
```
#### Operator Parameter
```
find -name "f*" -size 512k  # AND operator
find -name "f*" -o -size 512k #OR Operator
find -not -name "f*"  #Not Operator
```
#### Search parameter permission
```
find -perm 664
find -perm -664
```

## Q&A

- What command would find files and directories modified in the last 5 minutes in /dev directory?  
```
find /dev/ -mmin -5
```
- Find our secret file under /home/bob. You can either look for a file that is exactly 213 kilobytes or a file that has permission 402 in octal.
Save the name (including the parent directory path) of this file in /home/bob/secfile.txt file.
You can use the redirection to save your command's output in a file i.e [your-command] > /home/bob/secfile.txt
```
find /home/bob -size 213k > /home/bob/secfile.txt
```
- Find dogs.txt file under /usr/share directory.Save the location of the file in /home/bob/dogs file.  
```
sudo find /usr/share/ -name "dogs.txt" > /home/bob/dogs
```
- Find cats.txt file under bob's home directory and copy it into /opt directory.
```
find /home/bob/ -name "cats.txt"
/home/bob/.etc/h/e/r/cats.txt
sudo cp /home/bob/.etc/h/e/r/cats.txt /opt/
```
- Find all directories named pets in /var/directory and save the output (along with directory path) in /home/bob/pets.txt file.You should be able to save the output in a file using redirection i.e <your-command> > /home/bob/pets.txt
```
sudo find /var/ -type d -name pets > /home/bob/pets.txt
```
- Find all the files which have been modified in the last 2 hours in /usr directory.
```
sudo find /usr -type f -mmin -120
```
- Find all the files with size 20MB in /var directory.
```
sudo find /var/ -type f -size 20M # type f return only file
```
- Find all files between 5mb and 10mb in the /usr directory and save the output (along with parent path) in home/bob/size.txt file.
```
sudo find /usr -type f -size +5M -size -10M > /home/bob/size.txt
```