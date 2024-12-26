# Remote unlock LUKS using OpenSSH

Tested only on Ubuntu 24.04

1. `sudo apt install git busybox`
1. Create directory `sudo mkdir /etc/openssh-initramfs`
1. Generate host keys `sudo ssh-keygen -t ed25519 -f /etc/openssh-initramfs/ssh_host_ed25519_key -q -N ""`
1. `git clone https://github.com/luka-kusulja/debian-package-openssh-initramfs.git`
1. `cd debian-package-openssh-initramfs`
1. `sudo cp ./openssh-initramfs/etc/openssh-initramfs/* /etc/openssh-initramfs`
1. `sudo dpkg-deb --build openssh-initramfs openssh-initramfs.deb`
1. `sudo dpkg -i openssh-initramfs.deb`
1. Edit `sudo nano /etc/openssh-initramfs/config` and change the port number (Default is 20123)
1. `sudo update-initramfs -u`
1. `sudo reboot`

## More details
See [OLD-README.md](OLD-README.md)