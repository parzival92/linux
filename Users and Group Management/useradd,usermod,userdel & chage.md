# Manage Local User Accounts

- Local User Accounts
    - To add new user
    ```
    sudo useradd john
    cat /etc/login.defs
    useradd --defaults
    ```
    - Set password for useraccount
    ```
    sudo passwd john
    cat /etc/passwd
    ```
    - Delete user
    ```
    sudo userdel --remove john
    ```
    - Assign userid
    ```
    sudo useradd --uid 1100 smith
    ```
    - List ids
    ```
    id
    ```
    - Get username
    ```
    whoami
    ```
    - Modify user home directory
    ```
    sudo usermod --home /home/otherdir --move-home john
    ```
    - Lock/Unlock Account
    ```
    sudo usermod --lock jane
    sudo usermod --unlock jane
    ```
    - Account Expiration
    ```
    sudo usermod -e 2030-03-01 jane
    ```
    - Password expiration(change age)
    ```
    sudo chage --lastday 0 jane
    sudo chage --maxday 30 jane
    ```

- Manage System Accounts
    - Create system user(No home directory)
    ```
    sudo useradd --system sysacc
    ```

# Q&A
- Set the jane user account to expire on March 1, 2030.
```
sudo usermod -e 2030-03-01 jane
```
- Create a system account called apachedev
```
sudo useradd --system apachedev
```
- Jane's account i.e jane is expired.Unexpire the same and make sure it never expires again.
```
sudo usermod -e "" jane
```
- Create a user account called jack and set its default login shell to be /bin/csh.
```
sudo useradd jack -s /bin/csh
```
- Delete the user account called jack and ensure his home directory is removed.
```
sudo userdel --remove jack
```
- Mark the password for jane as expired to force her to immediately change it the next time she logs in.
```
sudo chage -d 0 jane
```
- Lock the user account called sam
```
sudo usermod -L sam
```
- Make sure the user jane gets a warning at least 2 days before the password expires.
```
sudo chage -W 2 jane
```

