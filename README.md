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


### 3. Assign the last usable address to the router's interface in each LAN

I went into the router's CLI. I went into each interface, turned on the port with the command "no shutdown." I added the last usable address to the respected interface, and repeated the process for the other LANs, as well as the point-to-point connection.

<img width="1027" height="277" alt="Screenshot 2026-03-22 at 12 46 00 PM" src="https://github.com/user-attachments/assets/e32fe9b7-48b0-4123-a921-571dbb103e51" />

### 4. Configure static routes on each router so that all PCs can ping each other.

I went into each router's CLI once more and I confired the static routes so that I have a route to each LAN on the other router.

<img width="854" height="69" alt="Screenshot 2026-03-22 at 12 58 14 PM" src="https://github.com/user-attachments/assets/bed9f143-085f-4b45-93de-299f33143f18" />

### 5. Test the connection by sending pings from one PC to the next

I tested the connection to see if the PCs can oing each other. Sure enough, they did.

<img width="1090" height="860" alt="Screenshot 2026-03-22 at 1 05 01 PM" src="https://github.com/user-attachments/assets/a1f2172c-076f-4dbf-823a-e7e8c7196db7" />
