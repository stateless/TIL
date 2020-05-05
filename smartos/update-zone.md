# Examples
```
echo '{"ram": 4096}' | vmadm update $ZONEID
```

# Add a disk
```
[root@headnode (bh1-kvm1:0) ~]# cat add_disk.json
{
  "add_disks": [
    {
      "boot": false,
      "model": "virtio",
      "block_size": 8192,
      "size": 40960
   }
 ]
}
[root@headnode (bh1-kvm1:0) ~]# vmadm update $ZONEID -f add_disk.json
Successfully updated ZONEID
```

# Notes
[Source](https://wiki.smartos.org/managing-instances-with-vmamd/)
