# Search File using Grep

```
grep 'CentOS' /etc/os-release'
grep -i 'CentOS' /etc/os-release'
grep -r 'CentOS /dir
```

- Filter out the lines that contain any word that starts with a capital letter and are then followed by exactly two lowercase letters in /etc/nsswitch.conf file and save the output in /home/bob/filtered1 file.

```
egrep -w '[A-Z][a-z]{2}' /etc/nsswitch.conf > /home/bob/filtered1
```
- How many numbers in /home/bob/textfile begin with a number 2, save the count in /home/bob/count file.
You can use the redirection to save your command's output in a file i.e [your-command] > /home/bob/count
```
grep -c '^2' textfile > /home/bob/count
```
- How many lines in /home/bob/testfile file begin with string Section, regardless of case.
Save the count in /home/bob/count_lines file.

```
grep -ic '^SECTION' testfile > /home/bob/count_lines
```
- Find all lines in /home/bob/testfile file that contain string man, it must be an exact match.
For example the line like # before /usr/man. or NOCACHE keeps man should match but # given manpath. or For a manpath must not match.
```
grep -w man testfile > /home/bob/man_filtered
```