For svn+ssh, if you are running ssh on a different port. 

Then, add the followng to ~/.ssh/config. Then svn co svn+ssh://mysvn/home/svn/proj1.
 
```
Host mysvn
HostName server.com
Port 20000
User stateless
```

# See https://unix.stackexchange.com/questions/27143/how-to-configure-svn-ssh-with-ssh-on-non-standard-port
