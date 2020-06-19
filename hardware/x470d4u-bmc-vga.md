Installing a GPU into a x470d4u motherboard will disable the Onboard VGA.  This means the BMC KVM will stop working. Enable the Onboard VGA in BIOS to fix this issue.

```
BIOS -> Advanced -> Chipset and change the Onboard VGA setting from Auto to Enabled
```

[src](http://forum.asrock.com/forum_posts.asp?TID=12812&title=x470d4u-with-pcie-gpu)
