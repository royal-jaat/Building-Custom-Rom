So server you could try is gcp (Google'scloud console)

# Specs

500 GB storage 
32GB Ram 
V8 Cpu cores
I used UBUNTU v22.04 jammy lts x86/64

# Setup For gui (graphical user interface)
```
sudo apt update && sudo apt upgrade
```
```
sudo apt install ubuntu-gnome-desktop
```
```
sudo adduser <username>
```

   then give it password (don't leave empty)
    then enter enter until user is build 

   now give it superuser rights
```
sudo usermod -aG sudo,adm <username>
```
  now get into root directory of super user
```
sudo -i
```
  now we have to check whether the user is with password or not
```
cat /etc/ssh/sshd_config
```
 now we have to search for PasswordAuthentication if it is yes you are good to go but if it's not you have to modify it to yes

~ if it is no then let me show how to change it
```
nano /etc/ssh/sshd_config
```
 now remove # before PasswordAuthentication and then change no to yes
 and then click ctrl+x then Y after that you are good to go 

  now we have to download nomachine to control VM via any device with gui
```
wget <download link for nomachine deb file for x86/64>
```
  now we have to run nomachine in VM
```
sudo dpkg -i <name of the nomachine file you downloaded above>
```
```
reboot
```
# now stop the VM via website 

 # now we have to add some firewall rules

1) go to vpc network on website 

2) click on firewall 

3)create a new firewall rules

4) Name - nomachine-fw
Description - nomachine-fw
logs - off
Target Tags - nomachine-fw
source IPv4 Ranges - 0.0.0.0/0
tick/turn on the TCP then Ports - 4000

now click on create

now go back to VM setting (VM should be off)

1) Edit the VM

2) scroll down to Firewall 

3) add "nomachine-fw" to network tags

4) now save

# running VM on your device 

1) start the VM and copy the external IP

2) download nomachine in your device 

3) click on add device

4) give the machine name and paste the external IP at Host then click add

5) double click the device you added 

6) click ok ok yes yes ok ok

7) now you can see that you are connected 

8) whenever you stop and then start the VM external IP changes so make sure to edit Host to the new one everytime.




