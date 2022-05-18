# Kernel Runtime Parameters

- sysctl is used to modify kernel parameters at runtime. The parameters available are those listed under /proc/sys/. Procfs is required for sysctl(8) support in Linux. You can use sysctl(8) to both read and write sysctl data.

```
sudo sysctl -a
sudo sysctl -w net.ipv6.conf.default.disable_ipv6=1
man sysctl.d
sysctl -a | grep vm
```
# SELinux

- SELinux Contexts
```
ls -l
ls -Z #SELinux Context
user,role,type,level
ps axZ
id -Z
sudo semanage login -l
```

| SELinux User   | Roles       |
| ---------------| ----------- |
| developer_u  | developer_r,docker_r | 
| guest_u      | guest_r          | 
| root         | staff_r,sysadm_r,unconfied_r          | 

- Only Certain user can enter certain roles and certain types
- It lets authorized users and processes do their job, by granting the permission they need
- Authorized users and processes are allowed to take only a limited set of action
- Everything else is denied

## SELinux Modes
```
getenforce
```
# Q&A

- Find the SELinux labels of sshd process running on this system, save its value in /home/bob/sshd file.
```
ps auxZ | grep sshd
```
- Turn on kernel.modules_disabled kernel runtime parameter, so that loading new kernel modules will be disabled.

```
sudo sysctl -w kernel.modules_disabled=1
```
- Check out the SELinux label for the file stored at /bin/sudo. Ignore the SELinux user and role here.
```
ls -Z /bin/sudo
```
- Use the sysctl command to make sure this kernel runtime parameter is actively enabling its settings:
```
sudo sysctl -w net.ipv6.conf.lo.seg6_enabled=1
```
-Adjust the value of this kernel runtime parameter, vm.swappiness, to 10.After you set this to 10, also make the change persistent so that it will be auto-set to this value on the next reboot.
```
sudo vi /etc/sysctl.conf
vm.swappiness=10
sudo sysctl -p
```
- Change the SELinux context of /var/index.html file to httpd_sys_content_t
```
sudo chcon -t httpd_sys_content_t /var/index.html
```
- Temporarily change the SELinux status to Permissive on this system.
```
sudo getenforce
sudo setenforce 0
```
- Identify the SELinux Roles for xguest_u SELinux user and save the value(s) in /home/bob/serole file.
```
sudo semanage user -l
```