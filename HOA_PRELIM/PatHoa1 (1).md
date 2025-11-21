**Name: Cruz, Patrick Danielle C. Date Performed: Aug 8, 2025 Course/Section: CPE212 CPE31S4 Date Submitted: Aug 8, 2025 Instructor: Engr. Robin Valenzuela Semester and SY: 1st semester Activity 1: Configure Network using Virtual Machines** 

**1. Objectives:** 1.1. Create and configure Virtual Machines in Microsoft Azure or VirtualBox 1.2. Set-up a Virtual Network and Test Connectivity of VMs 

**2. Discussion: Network Topology:**     Assume that you have created the following network topology in Virtual Machines,        _provide screenshots for each task_. (Note: _it is assumed that you have the prior_           _knowledge of cloning and creating snapshots in a virtual machine_ ). **Task 1** : Do the following on Server 1, Server 2, and Local Machine. In editing the file using nano command, press control + O to write out (save the file). Press enter when asked for the name of the file. Press control + X to end. 

1. Change the hostname using the command _sudo nano /etc/hostname_     1.1 Use server1 for Server 1     1.2 Use server2 for Server 2     1.3 Use workstation for the Local Machine 



2. Edit the hosts using the command _sudo nano /etc/hosts._ Edit the second line.     2.1 Type 127.0.0.1 server 1 for Server 1     2.2 Type 127.0.0.1 server 2 for Server 2     2.3 Type 127.0.0.1 workstation for the Local Machine 



**Task 2** : Configure SSH on Server 1, Server 2, and Local Machine. Do the following: 

1. Upgrade the packages by issuing the command _sudo apt update_ and _sudo apt_     _upgrade_ respectively. 

2. Install the SSH server using the command _sudo apt install openssh-server_. 


3. Verify if the SSH service has started by issuing the following commands:     3.1 _sudo service ssh start_     3.2 _sudo systemctl status ssh_ 


4. Configure the firewall to all port 22 by issuing the following commands:     4.1 _sudo ufw allow ssh_     4.2 _sudo ufw enable_     4.3 _sudo ufw status_ 



**Task 3:** Verify network settings on Server 1, Server 2, and Local Machine. On each device, do the following: 

1. Record the ip address of Server 1, Server 2, and Local Machine. Issue the     command _ifconfig_ and check network settings. Note that the ip addresses of all     the machines are in this network 192.168.56.XX.     1.1 Server 1 IP address: 192.168.56.104     1.2 Server 2 IP address: 192.168.56.107     1.3 Server 3 IP address: 192.168.56.108 

2. Make sure that they can ping each other. 


2.1 Connectivity test for Local Machine 1 to Server 1: ✓ Successful ☐ Not Successful 2.2 Connectivity test for Local Machine 1 to Server 2: ✓ Successful ☐ Not Successful 2.3 Connectivity test for Server 1 to Server 2: ✓ Successful ☐ Not Successful **Task 4:** Verify SSH connectivity on Server 1, Server 2, and Local Machine. 

1. On the Local Machine, issue the following commands: 1.1 ssh username@ip_address_server1 for example, _ssh jvtaylar@192.168.56.120_ 1.2 Enter the password for server 1 when prompted 


1.3 Verify that you are on server 1. The user should be in this format user@server1. For example, _jvtaylar@server1_ 

2. Logout of Server 1 by issuing the command _control + D._ 

3. Do the same for Server 2. 


4. Edit the hosts of the Local Machine by issuing the command _sudo nano_     _/etc/hosts._ Below all texts type the following: 4.1 IP_address server 1 (provide the ip address of server 1 followed by the     hostname) 4.2 IP_address server 2 (provide the ip address of server 2 followed by the     hostname) 


4.3 Save the file and exit. 

5. On the local machine, verify that you can do the SSH command but this time,     use the hostname instead of typing the IP address of the servers. For example,     try to do _ssh jvtaylar@server1_. Enter the password when prompted. Verify that     you have entered Server 1. Do the same for Server 2. 


**Reflections:** Answer the following: 

1. How are we able to use the hostname instead of IP address in SSH commands? 


 ● In SSH commands the hostname may be used in place of an IP address since the SSH client relies on the name resolving system of the operating system providing the translation of the hostname to its IP address equivalent. This resolution is normally achieved by use of DNS servers, local /etc/hosts file or other services involved in globally discovering names in the network. When you enter in ssh user@hostname your system queries the IP address that is mapped to hostname in these ways without connecting to the SSH daemon on the remote machine. 

2. How secured is SSH?     ● When properly set up, SSH is regarded to be extremely secure. It employs        encrypted authentication credentials to guard against eavesdropping and        man-in-the-middle attacks by encrypting all communication between the client        and the server. SSH supports authentication mechanisms that need a high        level of authentication, such as public-key authentication and multi-factor        authentication. It employs powerful encryption techniques and safe key        exchange, ensuring data security and integrity. The security relies on        recommended practices such as blocking root login via SSH, using strong        passwords or keys, keeping the server up to date, and carefully managing user        access. When properly implemented, SSH is a tried-and-true method for        providing secure remote services and administration. 


