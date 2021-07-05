#### script.py is an OSPF network discovery script written in Python 2.7.3.
#### It allows the discovery of all OSPF network devices in the network, without connecting to each of them or knowing all their IP addresses. 
#### The user must provide the IP and SNMP community string of a single OSPF device in the network (for example, a device in the core) and the script searches for all other OSPF routers. 
#### Prior to running the script, the user should configure SNMPv2 community string on the device and also include the subnet between his PC and the router into the OSPF process, so he has IP connectivity to all other OSPF nodes.

After providing the necessary info and the OSPF data is gathered, the user has three choices: 


### a. Display the OSPF routers info on the screen.
### b. Export the data to a file. 
### c. Generate the OSPF topology showing neighborships, router IDs and neighbor IPs.

## Logical Flow Diagram

![](https://i.ibb.co/Fn86j1s/3-APPLI-1-1-1.jpg)