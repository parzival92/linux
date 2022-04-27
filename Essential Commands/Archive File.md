# Archiving Files

tar = **t**ape **ar**chive

- Packing Files and Directories with tar
```
tar --list --file archive.tar
tar tf archive.tar
```
- Create tar file
```
tar --create --file archive.tar file1
tar cf archive.tar file1
```
- Add a file to existing tar file
```
tar --append --file archive.tar file2
tar rf archive.tar file2
```
- Add directory and its content to tar file

```
tar cf archive.tar Picture/
```
- Extracting file from Archive
```
tar --extract --file archive.tar
tar xf archive.tar
```
- Extract tar to another directory
```
tar xf arhive.tar -C /tmp/
tar --extract --file archive.tar
```
## Q&A


- Create a tar archive logs.tar (under bob's home) of /var/log/ directory.
```
sudo tar --create --file logs.tar /var/log/
```
- List the content of /home/bob/logs.tar archive and save the output in /home/bob/tar_data.txt file.
```
tar tfP /home/bob/logs.tar > /home/bob/tar_data.txt
```