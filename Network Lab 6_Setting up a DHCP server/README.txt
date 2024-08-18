Objective: This is another simple lab to configure and setup a simple network
wanted to practice setting up a DHCP server on the router and getting IP addresses
to client machines automatically. So far I've been manually setting them up which
has been less than ideal.

Step 1: Setup the network with a simple router, switch and 3 PC's.


Step 2: Setup the actual DHCP functionality on the router, did this with the following
	commands while in the configuration terminal.

	
	Router(config) ip dhcp pool LAN
	Router(dhcp-config)# network 192.168.1.0 255.255.255.0
	Router(dhcp-config)# default router 192.168.1.1


The First command setup the DHCP pool and names it LAN

The Second command sets up the range for what the DHCP pool is going to be

The Third command sets the default gateway for the DHCP server



	
	