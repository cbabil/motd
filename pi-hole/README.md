# Pi-hoel custom banner / MOTD

![motd-PiHole](https://github.com/cbabil/motd/blob/master/pi-hole/motd.png)


## Installation

Get this welcome banner:
```
wget https://github.com/cbabil/motd/pi-hole/master/10-uname
```

Move the file to the foler:
```
sudo mv 10-uname /etc/update-motd.d/
```

Change the permision on the file
```
sudo chmod +x /etc/update-motd.d/10-uname
```

Remove the old motd
```
sudo rm /etc/motd
```

Edit the sshd_config
```
sudo nano /etc/ssh/sshd_config
```

uncomment 
```
#PrintLastLog yes
```

Replace the existing value
```
PrintLastLog no
```

Restart the sshd service
```
sudo systemctl restart sshd
```

### License
see License file.