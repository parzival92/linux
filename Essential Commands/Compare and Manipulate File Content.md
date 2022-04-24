# Compare and Manipulate File Content

- View File
```
cat /home/user.txt
```
- View file in reverse order
```
tac /home/users.txt
```
- View last 5,20 line from a file
```
tail -n 20 /var/log/dng.log # Last 20
head -n 20 /var/log/dng.log # Top 20 from start
```
- Transforming Text:Sed(Search and replace text)
```
sed 's/canda/canda/g' userinfo.txt 
# Only preview not change actual file
# Decoding above text - s- subsitute g- global search and replace
sed 's/canda/canda/' userinfo.txt # Only replace first occurence
sed -i 's/canda/canda/g' userinfo.txt 
#Above command will change actual file
sed -i 's/disabled/enabled/gi' /home/bob/values.conf
# Ignore case
```
- cut command
```
cut -d ',' -f 3 userinfo.txt >countries.txt
```
- uniq and sort
```
sort countries.txt
uniq countries.txt
```
- Comparing File :diff
```
diff file1 file2
sdiff file1 file2
```

#### Q&A

- Change all values enabled to disabled in /home/bob/values.conf config file from line number 500 to 2000.
```
sed -i '500,2000s/enabled/disabled/g' values.conf
```
- Replace all occurrence of string #%$2jh//238720//31223 with $2//23872031223 in /home/bob/data.txt file

```
sed -i 's~#%$2jh//238720//31223~$2//23872031223~g' /home/bob/data.txt
```
- Save last 500 lines of /home/bob/textfile file in /home/bob/last file.
```
tail -500  /home/bob/textfile > /home/bob/last
```