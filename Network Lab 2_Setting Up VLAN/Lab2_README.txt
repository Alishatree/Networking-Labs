Lab 2 Creating a basic VLAN setting

Objective: This lab I want to create a basic VLAN setup using a single switch. The switch 
should be connected to a router where traffic from VLAN1 and VLAN2 can send it's data. Will 
successfully complete the lab if both VLAN's can communicate to the router, but can't send 
data to each other. 

Step 1: Setting up the switch and ports for VLAN1 and VLAN2 using the CLI.
	
	Switch0
	VLAN1 = Port 1-10
	Vlan2 = Port 11-20

	#Below is the specific code for setting up the VLAN's through the CLI
	
	Switch> enable
	Switch# configure terminal
	Switch(config)#
	Switch(config)# interface range {type} {port-range}
	Switch(config-if-range)# switchport mode access
	Switch(config-if-range)# switchport access vlan 10
	Switch(config-if-range)# exit
	Switch(config)# exit
	Switch# write memory

	
Step 2: Setup the router, setting it up as the default gateway and connecting it to 
	the switch.
	
	Router1
	Gateway = 192.168.1.1
	Port = (router) GigabitEthernet0/0/0 -> (switch) GigabitEthernet0/0 

	#Below are the commands to setup the default gateway

	Router> enable
	Router# configure terminal
	Router(config)# interface GigabitEthernet0/0
	Router(config-if)# ip address 192.168.1.1 255.255.255.0
	Router(config-if)# no shutdown
	Router(config-if)# exit
	Router(config)# exit
	Router# write memory


Step 3: Setup VLAN1 and VLAN2, connect them to the switch and configure them to send there
	IP packets to Router1.

	VLAN1 = 1-3
	VLAN2 = 11-13


Step 4: Test the network and verify it's set up properly by using a PC to ping the router 
	then ping the other VLAN.


Complete: Was able to get everything setup, did have to do this twice which was a bit frustrating
	  but I'm finished now and learned a lot. Know I could have only done one VLAN command to
	  set up VLAN2 since VLAN1 already existed. Also realized I could do both commands the second
	  time I set this up at once and then write it to memeory. 

	  Was a simple lab but it's given me a better understanding of how to work with the CLI and 
	  how to create and do this style of labwork.




	