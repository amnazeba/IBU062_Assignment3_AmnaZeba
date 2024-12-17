Computer network setup

Device Name: Router0
Device Model: 1941
Host Name: Router 
Port: GigabitEthernet 0\0
      GigabitEthernet 0\1

Device Name: Switch
Custom Device Model: 2960 IOS15
Host Name: Switch

Device Name: PC1
Device Model: PC-PT
Port: FastEthernet 0
IP address: 169.254.109.238

Device Name: PC0
Device Model: PC-PT
Port: FastEthernet 0
IP address: 169.254.54.53

Device Name: PC1
Device Model: PC-PT
Port: FastEthernet 0
IP address: 169.254.109.238

Device Name: Laptop 0
Device Model: Laptop - PT
Port: FastEthernet 0
IP address: 169.254.102.235

Device Name: Server 
Device Model: Server - PT
Port: FastEthernet 0
IP address: 169.254.140.176

Device Name: Switch 1
Custom Device Model: 2960 IOS15
Host Name: Switch

Device Name: Server 1
Device Model: Server - PT
Port: FastEthernet 0
IP address: 169.254.40.104

Device Name: Server 0
Device Model: Server - PT
Port: FastEthernet 0
IP address: 169.254.103.187

Device Name: PC2
Device Model: PC - PT
Port: FastEthernet 0
IP address: 169.254.231.22

Device Name: PC3
Device Model: PC - PT
Port: FastEthernet 0
IP address: 

Device Name: PC4
Device Model: PC - PT
Port: FastEthernet 0
IP address: 



Setting up DHCP on the router
Access the router:
First I connected to the router and accessed the command line. I typed enable to switch to privileged mode.Then I typed configure terminal to enter configuration mode.
To create a DHCP pool:
I created a DHCP pool called LAN and assigned the following settings to it:
Network range: 192.168.1.0 with mask 255.255.255.0.
Default gateway (default router): 192.168.1.1.
DNS server: 8.8.8.8.

The commands I used were:
ip dhcp pool LAN  
network 192.168.1.0 255.255.255.0  
default-router 192.168.1.1  
dns-server 8.8.8.8  
exit  
Exclusion of static IP addresses:

To avoid DHCP assigning IP addresses intended for devices with static addresses, I excluded the range from 192.168.1.1 to 192.168.1.10. I achieved this using the command:

ip dhcp excluded-address 192.168.1.1 192.168.1.10  
Save configuration:
After I finished the setup, I saved the configuration using the command:
write memory  
Configuration check:
To verify that everything is working correctly, I used the commands to display the current configuration and assigned IP addresses: 
show ip dhcp binding  
show running-config | include dhcp


End of a document
