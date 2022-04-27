# Use Input Output redirection

- Redirecting Output(use greather than >)
```
sort file.txt > sortedfile.txt
```
Note: When the same redirection is done multiple time only the last one will stay  
Use Double greater tha sign to to append in multiple statement
```
date >> file.txt
date >> file.txt
date >> file.txt
date >> file.txt
date >> file.txt
```
- stdin,stdout and stderr

    - less than < for stdin
    - greater than 1> for stdoutput
    - 2> for stderr

- Redirecting Error
```
grep -r '^The' /etc/ 2>/dev/null
# /dev/null - Black hole of linux / used for discard
```
- Redirecting Input
```
sendemail someone@example.com < email.txt
```
- Heredoc and Here String
```
#Here string
bc <<<1+2+3+4 = 10
```
- Piping
```
grep -v '^#' /etc/login.defs | sort | column -t
```