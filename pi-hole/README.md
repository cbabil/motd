# Pi-hole custom banner / MOTD

![motd-Pi-hole](https://github.com/cbabil/motd/blob/master/pi-hole/motd.png)

### Pre-installation (Not Using PAM)
Disable any kind of preconfigured MOTD:
~~~bash
sudo nano /etc/ssh/sshd_config
UsePAM no #UsePAM slows the login
PrintMOTD no #PrintMOTD is used only in case of static MOTD.
PrintLastLog no
~~~

---

### Installation (Not Using PAM)
To install the latest version. Choose one of this options:

#### All in one:
~~~bash
wget https://raw.githubusercontent.com/cbabil/motd/master/pi-hole/10-uname && sudo mv 10-uname /etc/motd.sh && sudo chmod +x /etc/motd.sh && sudo rm -f /etc/motd && sudo printf "# MOTD\n/etc/motd.sh\n" | sudo tee -a /etc/profile  > /dev/null 2>&1 &&sudo systemctl restart sshd && echo "PI-Hole MOTD installed"
~~~

#### Step by step:
~~~bash
wget https://raw.githubusercontent.com/cbabil/motd/master/pi-hole/10-uname
sudo mv 10-uname /etc/motd.sh
sudo chmod +x /etc/motd.sh
sudo rm -f /etc/motd
sudo printf "# MOTD\n/etc/motd.sh\n" | sudo tee -a /etc/profile  > /dev/null 2>&1
sudo systemctl restart sshd && echo "PI-Hole MOTD installed"
~~~

---

### Pre-installation (Using PAM)
Disable any kind of preconfigured MOTD:
~~~bash
sudo nano /etc/ssh/sshd_config
UsePAM yes
PrintMOTD no
PrintLastLog no
~~~

---

### Installation (Using PAM)
To install the latest version. Choose one of this options:

#### All in one:
~~~bash
wget https://raw.githubusercontent.com/cbabil/motd/master/pi-hole/10-uname && sudo mv 10-uname /etc/update-motd.d/ && sudo chmod +x /etc/update-motd.d/10-uname && sudo rm -f /etc/motd && sudo systemctl restart sshd && echo "PI-Hole MOTD installed"
~~~

#### Step by step:
~~~bash
wget https://raw.githubusercontent.com/cbabil/motd/master/pi-hole/10-uname
sudo mv 10-uname /etc/update-motd.d/
sudo chmod +x /etc/update-motd.d/10-uname
sudo rm -f /etc/motd
sudo systemctl restart sshd && echo "PI-Hole MOTD installed"
~~~

---

### License
Distributed under the MIT License. See `LICENSE` for more information.