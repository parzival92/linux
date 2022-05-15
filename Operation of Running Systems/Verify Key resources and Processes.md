# Verify Key Resources and Processes

## Q&A

- Identify what % space of / partition is in use on our system. Save the value in /home/bob/used file.For example if used space is 10% then the file content should be 10%
```
df /
```
- Figure out how much storage space the /bin/ directory is using and save the value in /home/bob/bin file.
```
du -sh /bin/
```
- Use the correct command to check out the memory on this system (in megabytes). In /home/bob/memory file, save the total amount of RAM that this system has.
For example, if you see 512 in the command's output, the file contents should be 512
```
free --mega
```
- Use the correct command to check out from how long this system is up. In /home/bob/up file, save the time value in hours, minutes or days (whichever is applicable).
For example, if you see 1:07 in the command's output, the file content should be 1.
Similarly, if you see something like 51 min in the command's output, the file content should be 51min (without any space).
```
uptime -p
```
- Use the correct command to identify the CPU core(s) per socket on this system. Save its value in /home/bob/cpu file.
```
lscpu
```
- On /dev/vdb we have an XFS filesystem. Use the correct command to check this filesystem for errors and save the output in /home/bob/fscheck file.
```
sudo xfs_repair -v /dev/vdb
```
