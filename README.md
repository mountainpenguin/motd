### Installing

# Disable SSHD motd

Edit `/etc/ssh/sshd_config` and modify the following lines:
```conf
PrintMotd no
PrintLastLog no
```

# Disable PAM motd

Edit `/etc/pam.d/login` and comment out the following line:
```conf
#session        optional    pam_motd.so
```

On gentoo instead edit `/etc/pam.d/system-login` and comment out the following line:
```conf
#session        optional    pam_motd.so motd=/etc/motd
```

# Install the script somewhere (optional)
```bash
cp motd /path/to/motd
```

# Modify your login profile to run the script

Edit `/etc/profile`
Add the following line to the bottom of the file:
```bash
/path/to/motd
```

zsh or other shell users should edit their corresponding profiles.
E.g. zsh uses `/etc/zsh/zprofile`

# Hope it works!

