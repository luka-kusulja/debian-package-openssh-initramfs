# Remote unlock LUKS using OpenSSH

Tested only on Ubuntu 24.04

1. `sudo apt install git busybox`
2. Generate host keys `ssh-keygen -t ed25519 -f /etc/openssh-initramfs/ssh_host_ed25519_key -q -N ""`
3. `git clone https://github.com/luka-kusulja/debian-package-openssh-initramfs.git`
4. `cd debian-package-openssh-initramfs`
5. `sudo dpkg-deb --build openssh-initramfs openssh-initramfs.deb`
6. `sudo dpkg -i openssh-initramfs.deb`
7. Edit `/etc/openssh-initramfs/config` and change the port number (Default is 20123)
8. `sudo update-initramfs -u`
9. `sudo reboot`

## More details
See [OLD-README.md](OLD-README.md)