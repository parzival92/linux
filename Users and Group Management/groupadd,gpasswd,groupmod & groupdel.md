# Create, delete, and modify local groups and group memberships

- Local Groups and Group Memeberships
    - Admin Group is primary group/login group
    - Create group
    ```
    sudo groupadd developers
    ```
    - Add user to group
    ```
    sudo gpasswd -a john developers
    ```
    - List group for user
    ```
    groups john
    ```
    - Delete user from group
    ```
    sudo gpasswd -d john developers
    ```
    - Modify group
    ```
    sudo usermod -gid developers john
    ```
    - Rename group
    ```
    sudo groupmod -n programmers developers
    ```
    - Delete group
    ```
    sudo groupdel programmers
    ```

# Q&A

- Add the user jane to the group called developers.
```
sudo gpasswd -a jane developers
```
- Create a group named cricket and set its GID to 9875
```
sudo groupadd -g 9875 cricket
```
- You already created group cricket in the previous question, now rename this group to soccer while preserving the same GID.
```
sudo groupmod -n soccer cricket
```
- Create a user sam with UID 5322, also make it a member of soccer group.
```
sudo useradd -u 5322 sam
sudo gpasswd -a sam soccer
```
- Update primary group of user sam and set it to rugby
```
sudo usermod -g rugby sam
```
- Delete the group called appdevs.
```
sudo groupdel appdevs
```