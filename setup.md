## Windows
*Remember to upgrade your WSL to Version 2 and install Ubuntu or similar*
`usbipd list` -> Remember the BUSID of the appropriate COM port
`usbipd bind -b <BUSID>` -> Share the BUSID with the WSL Subsystem
`usbipd attach --auto-attach --busid <BUSID> --wsl` -> permanently attach the BUSID to the WSL Subsystem

## WSL2
- Copy the Iceman Firmware Repo `git clone https://github.com/RfidResearchGroup/proxmark3.git`
- Path to the fw `cd ~/proxmark3`
- Install necessary prereqs for compiling the fw 
```
- sudo apt-get install --no-install-recommends \
  git ca-certificates build-essential pkg-config \
  libreadline-dev gcc-arm-none-eabi libnewlib-dev \
  libbz2-dev liblz4-dev libpython3-dev qtbase5-dev \
  libssl-dev libgd-dev
```
- Setup your makefile.platform `sudo nano Makefile.platform`
- I know that my proxmark has external flash so i specified, if youre not sure just remove the line.
```
PLATFORM=PM3GENERIC
PLATFORM_EXTRAS=FLASH
# always ensure final line ends in line feed, or comment line
```
- Next compile the fw with
```
- make clean
make -j
```
- Make sure `ls -lFA /dev/ttyACM*` returns something like *crw-rw---- 1 root dialout 166, 0 Feb  1 17:06 /dev/ttyACM0*
- Next set all perms
```
sudo make accessrights
sudo make udev
```
- And restart everything because WSL 2 is a weird one sometimes
```
sudo service udev restart
sudo udevadm trigger --action=change
```
- Check if a symbolic link has been made with `ls -lFA /dev/ttyACM* /dev/pm3*` it should output something like *lrwxrwxrwx 1 root root         7 Feb  1 17:06 /dev/pm3-0 -> ttyACM0
crw-rw---- 1 root dialout 166, 0 Feb  1 17:22 /dev/ttyACM0*

- Now only thing left is to flash your pm3 with
```
./pm3-flash-all
```

- run `./pm3` and youre done.