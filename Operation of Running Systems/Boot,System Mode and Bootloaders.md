# Boot,reboot and shutdown a system safely

- Reboot and Shutdown
```
# systemctl = system control
sudo systemctl reboot
sudo systemctl reboot --force
systemctl poweroff
```
- Reboot at particular time
```
shutdown 02:00
shutdown +15
#Shutdown with wall message
sudo shutdown -r +1 'Scheduled restart tp do an offline-backup of our database'
```
# Boot or change system into different operating modes

- Change default target
```
systemctl get-default
sudo systemctl set-default multi-user.target #remove graphical interface
sudo systemctl isolate graphical.target # Without Reebot
sudo systemctl isolate emergency.target
sudo systemctl isolate rescue.target # Root shell 
```

# Install, configure and troubleshoot bootloaders

- Purpose of bootloader is to start the linux kernel

- GRUB is a complete program for loading and managing the boot process. It is the most common bootloader for Linux distributions. A bootloader is the first software that runs when a computer starts.

```
grub2-mkconfig -o /boot/grub2/grub.cfg
grub2-install /dev/sda/
```

## Q&A

- On a system booting through legacy BIOS mode, what file would you edit before generating a new grub configuration file  
Ans - /etc/default/grub
- After you edited the file mentioned previously, what command would you use to generate the new grub configuration file?  
ANs - sudo grub2-mkconfig -o /boot/grub2/grub.cfg
- Schedule this system to power off two hours later from now.
```
sudo shutdown +120
```
- The system is currently booting to a text-only console.
Change it to boot to a graphical desktop by default.
```
systemctl set-default graphical.target
```
- Change grub's default timeout from 1 seconds to 5 second.
```
Edit /etc/default/grub file:
sudo vi /etc/default/grub
GRUB_TIMEOUT=1
GRUB_TIMEOUT=5
```
- Install grub to /dev/vda.Make sure to save the installation command output to /home/bob/grub.txt file.
```
