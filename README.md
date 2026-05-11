# OSPF-Part-1
In This project, I will enable OSPF on the routers, and configure them to make sure that the PC reaches the Internet.

## Platforms Leveraged
- Cisco Packet Tracer

##  Scenario

My job is to configure all the routers in network and enable OSPF on them so that PC1 can send traffic through the devices in a timely manner as well as connect to the internet.

<img width="894" height="288" alt="Screenshot 2026-05-11 at 1 23 11 PM" src="https://github.com/user-attachments/assets/7ab28300-ab77-4388-af8e-dc34fd287d63" />


---

## Steps Taken

### 1. Configure the routers and enable them.

I first configured hostnames for each router using the "hostname" command in the CLI command. I called the first Router R1, I called the second Router R2, etc. Then I configured the ip address and the subnet mask on each interface, then  I enabled them using the "no shutdown" command.

I repeated the process for the other three routers.

<img width="835" height="525" alt="Screenshot 2026-05-11 at 1 34 01 PM" src="https://github.com/user-attachments/assets/b29d15b2-d833-4ad7-9b01-1a1f9e809e6b" />


### 2. Configure a loopback interface on each router.

I configured a loopback interface on each router through the "interface l0" command. I added a loopback interface (which is a virtual interface) on each router as a backup interface for the physical interface. I configured the ip address 1.1.1.1/32 for R1. 2.2.2.2/32 for R2. Etc.

<img width="835" height="525" alt="Screenshot 2026-05-11 at 1 34 01 PM" src="https://github.com/user-attachments/assets/7f2d9e0c-f4f3-4e6a-afa4-42dde3a7a10b" />


### 3. Enable OSPF on each interface of the routers.

I then enabled OSPF on each interface of each router by going into the interface and applying the "ip ospf 1 area 0" command in the CLI. I added a "passive-interface" command on the routers connected to end hosts so that no unnecessary OSPF traffic is being sent.

<img width="793" height="187" alt="Screenshot 2026-05-11 at 2 21 09 PM" src="https://github.com/user-attachments/assets/8d7a8c68-0c5b-43be-b2a7-14f3e211c1a2" />

<img width="586" height="186" alt="Screenshot 2026-05-11 at 2 21 22 PM" src="https://github.com/user-attachments/assets/3ffef31f-40ff-4b42-bf65-c75e6301c31f" />



### 4. Configure the reference bandwidth on each router so a FastEthernet interface has a cost of 100.

The OSPF cost is calculated by dividing the reference bandwidth by the interface's bandwidth. The default reference bandwidth is 100 mps. If I calculate the cost of an OSPF, and the value is less than one, the cost will be converted to one. So the default cost of an Ethernet interface will be 10 (100 mps / 10 mps). The default cost of a Gigabit interface would be one (100 mps / 1000 mps). Our job is to make sure that a FastEthernet interface has a cost of 100. And every router in the network has to have a matching reference bandwidth. So I changed the reference bandwidth to 10,000 using this command "auto-cost reference-bandwidth."

<img width="925" height="73" alt="Screenshot 2026-05-11 at 3 00 45 PM" src="https://github.com/user-attachments/assets/d3e4a430-c42a-4768-99c7-40b1582a8a00" />


### 5. Configure R1 as an ASBR that advertises a default route in to the OSPF domain.

I applied a "default-information originate" command into R1 which turns the Router into an ASBR.

<img width="716" height="172" alt="Screenshot 2026-05-11 at 3 00 36 PM" src="https://github.com/user-attachments/assets/cbb2e5a0-3225-4015-a827-f172d62b02c7" />

I also created a default route in R1 so that the routers and the PC can connect to the Internet using the "ip route" command and connecting it to the ISPR device as the next route.

<img width="824" height="126" alt="Screenshot 2026-05-11 at 3 17 07 PM" src="https://github.com/user-attachments/assets/83a8a9a5-9703-4378-8e94-64cabfc861df" />


