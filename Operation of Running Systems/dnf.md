# Upgrading with package manager

- Dandified yum, better known as DNF, is a software package manager for RPM-based Linux distributions that installs, updates, and removes packages

```
dnf check-upgrade
sudo dnf upgrade
```

# Manage Software with dnf

```
sudo dnf repolist
sudo dnf repolist --all # Enable repository status
sudo dnf config-mananger --enable powertools
sudo dnf config-mananger --add-repo url
sudo rm file_name
sudo dnf search 'web server'
sudo dnf info nginx
```

- Install Package and Reinstall Package

```
sudo dnf install nginx
sudo dnf reinstalll nginx
```

- Unistall and Remove Package

```
sudo dnf remove nginx
```

- Group Install via dnf

```
sudo dnf group list
sudo dnf group list --hidden
sudo dnf group install 'Server with GUI'
sudo dnf group remove 'Server with GUI'
```
- dnf install via rpm

```
wget url
sudo dnf install ./path_to_file
```

- Use dnf to identify file origins

```
dnf provides /etc/anacrontab
dnf provides docker
dnf repoquery --list nginx
```

# Q&A

- How do we enable the PowerTools repository on CentOS?
```
sudo dnf repolist --all
sudo dnf config-manager --enable powertools
``` 
- Install the software package called nginx.

```
sudo dnf install nginx -y
```
- Install the group that brings in software related to Container Management.
```
sudo dnf group install 'Container Management'
```
- Remove the Nginx software package.
```
sudo dnf remove nginx
```
- List what old packages can be upgraded and store the list in /home/bob/upgrade.txt file.
```
sudo dnf check-upgrade > /home/bob/upgrade.txt
```
- Check the repositories in verbose mode, which are enabled by default and copy the output in /home/bob/verbose.txt file.
```
sudo dnf repolist -v > /home/bob/verbose.txt
```
- In some cases, we might not be sure about the package name for a particular software. Search the package related to Apache HTTP Server and store the output in /home/bob/webservers.txt file.
```
sudo dnf search "Apache HTTP Server" > webservers.txt
```
- List all files contained by the curl package and save the output in /home/bob/curl.txt file
```
sudo dnf repoquery --list curl > curl.txt
```