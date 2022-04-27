# Compression And Decompression Utilities

- Compression using gzip,bzip2,xz(deletes original file)
```
gzip file1
bzip2 file2
xz file3
```
- Decompression using gzip,bzip2,xz
```
gzip --decompress file1.gz
bzip2 --decompress file2.bz2
xz --decompress file3.xz
```
- Use -k or --keep option to dont delete input file
```
gzip --keep file1
```
- Compress using zip
```
zip archive file1
zip -r archive Pictures/
unzip archive.zip
```
- Create tar and compression at the same time
```
tar czf archive.tar.gz file1
tar --create --gzip --file archive.tar.gz file1
```

## Q&A

- Create a compressed tar archive logs.tar.gz (under bob's home) of /var/log/ directory.
```
sudo tar --create --gzip --file logs.tar.gz /var/log/
```
- Extract the contents of /home/bob/archive.tar.gz to the /tmp directory.
```
tar --extract --file /home/bob/archive.tar.gz --directory /tmp/
```


