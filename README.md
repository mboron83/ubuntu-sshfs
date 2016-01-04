1. sudo apt-get install sshfs
2. check permissions of ~/ssh/id_rsa. Be sure that they are set to 600 !!!!!!!
3. sudo usermod -a -G fuse USERNAME
4. mkdir -p /home/username/remote
5. sudo vi /etc/fuse.conf, enable _user_allow_other_ option
6. sudo vi /etc/fstab
```
sshfs#username@hostname:/home/username/    /home/username/remote/    fuse    delay_connect,comment=sshfs,users,exec,uid=1000,gid=1000,allow_other,reconnect,transform_symlinks,BatchMode=yes 0 0
```
7. copy mountsshfs to /etc/networking/if-up.d/mountsshfs and change permissions to 755
8. copy umountsshfs /etc/networking/if-down.d/umountsshfs and change permissions to 755
9. restart system, enjoy :-)
