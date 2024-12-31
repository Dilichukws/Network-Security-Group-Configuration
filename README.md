# Network-Security-Group-Configuration
Creating a network security group to limit (allow or deny) access to a virtual machine via Azure, in a nutshell, is as follows:

1. Create a virtual machine: A virtual machine is required to test the network security created and hence,
   a window server virtual machine is created devoid of any inbound port rules and an NIC ( Network Interface Card) Network Security Group (NSG)

2. Create an NSG: After verifying that the virtual machine has been created and ensuring that no port rules or NIC security group is associated with the virtual machine,
   an NSG resource is created and linked with the virtual machine's NIC. This enables the definition of network security group rules on the virtual machine.

3. Configure an inbound rule to enable Remote Desktop Protocol (RDP): Disabling any inbound port also disables Remote desktop connection to the virtual machine, and hence,
   renders a user unable to connect to it remotely. To connect, an inbound port rule to allow RDP to the virtual machine is created on port 3389 with a priority value lower than the default rules.

4. Configure an outbound rule that denies connection to the internet: Once it is verified that the virtual machine can connect to the internet,
   a test outbound rule is then created to deny access to the internet, using a service tag as the destination under all destination port ranges, and also with priority value
   lower than the default.

   lastly, verify that you can no longer access the internet.
   
