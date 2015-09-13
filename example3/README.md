To ensure we can run, we should take below instructions to prepare the VM:

# Install Guest Extension

- Update sources.list

```
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak 
sudo echo "
deb http://mirrors.aliyun.com/ubuntu/ vivid main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ vivid-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ vivid-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ vivid-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ vivid-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ vivid main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ vivid-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ vivid-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ vivid-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ vivid-backports main restricted universe multiverse
" | sudo tee /etc/apt/sources.list

sudo apt-get update
```

- Start the Ubuntu Server VM and insert the Guest Additions CD image (Devices menu, Install Guest Additions).
- Mount the CD Rom with the shell command:

	sudo mount /dev/cdrom /media/cdrom

- Install necessary build tools and build dependencies:

	sudo apt-get install -y dkms build-essential linux-headers-generic linux-headers-$(uname -r)

- Build and install the Guest Additions:

	sudo /media/cdrom/VBoxLinuxAdditions.run

# Install `puppet`

```
sudo apt-get install puppet
```