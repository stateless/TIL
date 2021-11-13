# [How to Keep the Default Audio Devices from Changing on Ubuntu](https://wolfgang-ziegler.com/blog/prevent-changing-of-default-ubuntu-sound-device)

"using the set-default-sink and set-default-source options of the pactl command, we can set the default input and output devices".

"Note that these settings are volatile and won't survive a reboot of your PC. To make those settings persistent (well, kind of), I simply added those pactl set-default... instructions to my ~/.bashrcfile - problem solved."

# [Ubuntu changes sound device after suspend, how to fix?](https://askubuntu.com/questions/762816/ubuntu-changes-sound-device-after-suspend-how-to-fix)

"Basically, Pulseaudio reroutes the sound when it loses contact with HDMI and doesn't return it after HDMI is reconnected. It is fixed in version 9."

"edit /etc/pulse/default.pa to comment out (add # to the start of) the line:"
```
    #load-module module-switch-on-port-available
```
