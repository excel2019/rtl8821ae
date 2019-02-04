# rtl8821ae

How to fix issues with realtek wifi card rtl8821ae on Ubuntu - at least is how I fixed it

1 - Upgrade to Ubuntu 18.04.1

2 - Follow the tutorial at https://github.com/lwfinger/rtlwifi_new/blob/master/README.md

3 - Reboot your computer

4 - Open terminal and type "sudo iwconfig wlp3s0 power off" to disable power management

5 - Type "sudo nano /etc/NetworkManager/conf.d/default-wifi-powersave-on.conf" on terminal, change the value from 3 to 2 and save, this will save your power management settings

6 - If only this works for you, stop here, else continue

7 - Type "sudo service network-manager restart" on terminal to restart network manager

8 - Type "sudo ip link set wlp3s0 down"

9 - Type "sudo modprobe -rv rtl8821ae"

10 - Type "sudo modprobe -v rtl8821ae swenc=Y"

11 - This should work, but when you reboot and wifi doesn't work try to type this commands on terminal:
	
	sudo service network-manager restart
	sudo ip link set wlp3s0 down
	sudo modprobe -rv rtl8821ae
	sudo modprobe -v rtl8821ae swenc=Y
      
 If this does not work then you're cursed. F*ck realtek
