# ZFS Encryption

```
sudo zfs create -o encryption=on -o compression=on -o keylocation=prompt -o keyformat=passphrase test-pool/encrypted
```

Remember to use the -l flag when mounting the encrypted dataset. You will be prompted for the passphrase, supply the passphrase you have used to encrypt the pool, and continue:
```
zfs mount -l pool/encrypted
zfs umount -u pool/encrypted
```

See also:
```
zfs load-key pool/dataset # asks for passphrase
zfs mount pool/dataset # now you can see your data
```
## External HDD mount
```
zpool import thunder
zpool status thunder
zfs mount -a -l
```


## Unlock at boot time: /etc/systemd/system/zfs-load-key@.service

[Unit]
Description=Load %I encryption keys
Before=systemd-user-sessions.service
After=zfs-import.target

[Service]
Type=oneshot
RemainAfterExit=yes
ExecStart=/usr/bin/bash -c 'until (systemd-ask-password "Encrypted ZFS password for %I" --no-tty | zfs load-key %I); do echo "Try again!"; done'

[Install]
WantedBy=zfs-mount.servicesystemd
```
[src](https://wiki.archlinux.org/title/ZFS#Native_encryption)

```

# ZFS other

Check ashift
```
zpool get all | grep ashift # if specified at creation
zdb -U /data/zfs/zpool.cache | grep ashift 
```
