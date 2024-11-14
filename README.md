# Design and Implementation of a Small Office Home Office Network 

## Networking simulation software used:

Cisco Packet Tracer 8.2.2

## Scenario & Requirements:

XYZ company is a fast-growing company in Eastern Australia with more than 2 million customers globally. The company deals with selling and buying food items, which are basically operated by the headquarters. The company is intending to open a branch near the local village Bonalbo. Thus, the company requires young IT graduates to design the network for the branch. The network is intended to operate separately from the HQ network. Being a small network, the company has the following requirements regarding implementation:

•	One router and one switch to be used (all CISCO products).

•	3 departments (Admin/IT, Finance/HR and Customer service/Reception).

•	Each department is required to be in different VLANS.

•	Each department requires a wireless network for the users.

•	Host devices in the network are required to obtain IPv4 address automatically.

•	Devices in all the departments are required to communicate with each other.


Assume the ISP gave out a base network of 192.168.1.0, you as the young network engineer who has been hired, design and implement a network considering the above requirements.

## Technologies Implemented:
1.	Creating a Simple Network using a Router and Access Layer Switch.
2.	Connecting Networking devices with Correct cabling.
3.	Creating VLANs and assigning ports VLAN numbers.
4.	Subnetting and IP Addressing.
5.	Configuring Inter-VLAN Routing (Router on a stick).
6.	Configuring DHCP Server (Router as the DHCP Server).
7.	Configuring WLAN or wireless network (Cisco Access Point).
8.	Host Device Configurations.
9.	Test and Verifying Network Communication.


## Subnetting the network:

Base Network: 192.168.1.0

No. of subnets required: 3

No. of subnets = 2^n 

2^n=3   (n = number of bits borrowed)

2^2=4

Therefore: n = 2

Class C Address: 

255.255.255.0 = 11111111.11111111.11111111.00000000

Borrowing 2 bits from the host portion:

11111111.11111111.11111111.11000000 

New subnet mask: 255.255.255.192 OR /26

Block Size = 64

## Subnets:
#### 1st Subnet

Network ID: 192.168.1.0

Broadcast ID: 192.168.1.63

Host range: 192.168.1.1 - 192.168.1.62


#### 2nd Subnet

Network ID: 192.168.1.64

Broadcast ID: 192.168.1.127

Host range: 192.168.1.65 - 192.168.1.126


#### 3rd Subnet

Network ID: 192.168.1.128

Broadcast ID: 192.168.1.191

Host range: 192.168.1.129 - 192.168.1.190


## Network Layout:
 ![image](https://github.com/user-attachments/assets/d42eb82f-6863-4717-b75d-59e99ca1a7d9)

 ## Configuration
Configuring VLANs on switch:

![image](https://github.com/user-attachments/assets/c6430d30-07ef-4597-8c90-d866985693f2)
![image](https://github.com/user-attachments/assets/9662fabc-8690-4833-aeca-4b566973b842)


Configuring wireless access points for each VLAN:

![image](https://github.com/user-attachments/assets/0d6b9915-2fa0-4cbd-b06e-16505547753b)
![image](https://github.com/user-attachments/assets/a461afd2-f83b-4931-bf13-08afeb91694b)
![image](https://github.com/user-attachments/assets/09ac8f88-b672-4761-bde2-b451248a9af8)


Turning on interface gig0/0 on the router:

![image](https://github.com/user-attachments/assets/23820775-5c73-4de6-bbbf-c72839242337)
 
Creating sub-interfaces for each VLAN:

![image](https://github.com/user-attachments/assets/6a76fa4b-9eb2-4185-a63b-7d880bf37055)
![image](https://github.com/user-attachments/assets/17dd6eda-851d-49b5-a35b-19c72d8dbae1)

Checking the sub-interfaces on the router:

![image](https://github.com/user-attachments/assets/23aac1aa-71a3-48e5-86ad-32c8aee0788b)

Creating DHCP pools:

![image](https://github.com/user-attachments/assets/7e70194b-cefb-4435-866e-2f48878a0129)

Ensuring DHCP is successful:
 
![image](https://github.com/user-attachments/assets/2f5dde4e-e750-48d2-bf02-75dbf745aaba)
![image](https://github.com/user-attachments/assets/50f6640d-2970-453d-af44-e7ff5b0fb32e)
![image](https://github.com/user-attachments/assets/9f169e0f-27c5-48a5-be3a-ca61c69311b3)

Ensuring wireless clients can connect to VLANS successfully:

![image](https://github.com/user-attachments/assets/01a41c86-0362-4440-a17c-170fde9964f5)

Testing successful connection between a wireless device in VLAN 10 and a wireless device in VLAN 30:
 
![image](https://github.com/user-attachments/assets/7bf1e894-90fd-49ba-bdc7-fc068719a74c)

Final network layout:

![image](https://github.com/user-attachments/assets/1d595671-d382-4976-9e0f-77295af3fcd8)


