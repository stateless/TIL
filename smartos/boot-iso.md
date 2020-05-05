1. Create the empty virtual machine
2. Copy iso into zone root
```
cd /zones/$ZONEID/root/
wget $ISOURL
```
3. Boot zone with ISO as cdrom
```
vmadm boot $ZONEID order=cd,once=d cdrom=/$ISOFILE,ide
```
4. Connect via VNC
```
vmadm info $ZONEID vnc
```

# Notes
[Source](https://wiki.smartos.org/how-to-create-a-virtual-machine-from-scratch/)
