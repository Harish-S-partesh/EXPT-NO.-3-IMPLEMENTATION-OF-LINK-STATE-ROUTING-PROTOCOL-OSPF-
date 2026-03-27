# EXPT NO.3 IMPLEMENTATION OF LINK STATE ROUTING PROTOCOL OSPF
# AIM

To connect computers in multiple networks using Open Shortest Path First Routing Protocol and to verify the connectivity between computers.

# EQUIPMENTS REQUIRED
1. Desktop Computer
2. Cisco Packet Tracer 5.0 Software

# IP ASSIGNMENT
<img width="829" height="519" alt="Screenshot 2026-03-17 112219" src="https://github.com/user-attachments/assets/fda34abb-6679-4ac6-86c8-2d3106334b24" />

# NETWORK DIAGRAM
<img width="678" height="468" alt="image" src="https://github.com/user-attachments/assets/d85345bb-1dff-485f-8fb4-db6a2a89aa88" />


# PROCEDURE
STEP 1: Open a Packet Tracer Software.

STEP 2: Drag two 2900 Switches, two Cisco 1800 Routers, and four PC Terminals from the tool bar and drop them into the work area.

STEP 3: Connect all the PC Terminals and Routers through Switches as shown in the network diagram using CAT 6 Patch cables.

STEP 4: Configure the IP address and Gateway in all PC Terminals.

STEP 5: Configure the Delhi router IP address, save the configuration, and restart the Delhi router.

STEP 6: Configure the Chennai router IP address, save the configuration, and restart the Chennai router.

STEP 7: Check the connectivity between the computers in the network.

STEP 8: Configure OSPF in the Delhi router, save the configuration, and restart the Delhi router.

STEP 9: Configure OSPF in the Chennai router, save the configuration, and restart the Chennai router.

STEP 10: Verify the connectivity between PC Terminals in different networks using the ping command.

STEP 11: Check the routing table in the Delhi router and Chennai router using the show ip route command.

# PROGRAM
### Router 0 Program
```
Router0> enable 
Router0# configure terminal 
Router0(config)# interface FastEthernet0/0 
Router0(config-if)# ip address 192.168.1.1 255.255.255.0 
Router0(config-if)# no shutdown 
Router0(config-if)# exit 
Router0(config)# interface Serial2/0 
Router0(config-if)# ip address 192.168.2.1 255.255.255.0 
Router0(config-if)# clock rate 64000 
Router0(config-if)# no shutdown 
Router0(config-if)# exit 
Router0(config)# router ospf 1 
Router0(config-router)# router-id 1.1.1.1 
Router0(config-router)# network 192.168.1.0 0.0.0.255 area 0 
Router0(config-router)# network 192.168.2.0 0.0.0.255 area 0 
Router0(config-router)# exit 
Router0# write memory
```
### Router 1 Program
```
Router1> enable 
Router1# configure terminal 
Router1(config)# interface FastEthernet0/0 
Router1(config-if)# ip address 192.168.3.1 255.255.255.0 
Router1(config-if)# no shutdown 
Router1(config-if)# exit 
Router1(config)# interface Serial2/0 
Router1(config-if)# ip address 192.168.2.2 255.255.255.0 
Router1(config-if)# no shutdown 
Router1(config-if)# exit 
Router1(config)# router ospf 1 
Router1(config-router)# router-id 2.2.2.2 
Router1(config-router)# network 192.168.3.0 0.0.0.255 area 0 
Router1(config-router)# network 192.168.2.0 0.0.0.255 area 0 
Router1(config-router)# exit 
Router1# write memory
```

# OUTPUT

### Router 0 Table 
<img width="1161" height="462" alt="image" src="https://github.com/user-attachments/assets/f0e31882-3aeb-4ec3-8995-d76234a026fc" />


### Router 1 Table 
<img width="755" height="349" alt="image" src="https://github.com/user-attachments/assets/06961795-611a-4d3a-8751-9825b78b66e0" />




# RESULT
Thus the computers in multiple networks using Open Shortest Path First Routing Protocol is connected and the connectivity between the computers is verified.
