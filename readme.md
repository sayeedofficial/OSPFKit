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

## PREREQUISITES

### 1. IP connectivity between the PC running the script and a device already running OSPF in the network.

### 2. PC settings: IP, Mask, Gateway (the IP address of the OSPF router interface it is connected to).

### 3. The router must advertise the PC subnet to the rest of the network via OSPF:
(config)#router ospf X
(config-router)#network A.B.C.D wildcard_mask area Y

Also, remove the IP address from R2, R3, R4 and R5's FastEthernet0/0 interfaces, so they will be able to access the virtual machine through R1, using the OSPF route they receive.

### 4. Have the same SNMPv2 community string (Read-Only) configured on all devices in the network (or don't configure anything and use the default "public" string).
For Cisco devices: http://www.cisco.com/c/en/us/td/docs/ios/12_2/configfun/configuration/guide/ffun_c/fcf014.html
(config) snmp-server community public RO



### 5. Install all the necessary (non-default) Python modules:
```https://pypi.python.org/pypi/networkx```
```https://pypi.python.org/pypi/matplotlib```
```https://pypi.python.org/pypi/pysnmp```
```https://pypi.python.org/pypi/colorama```

The script notifies the user for each module that is necessary and provides the download link. Example:

Note: For easier installation of Python modules use setuptools/easy_install. Download it from: https://pypi.python.org/pypi/setuptools

### 6. In Linux, configure the permissions on the script first: chmod 755 script.py