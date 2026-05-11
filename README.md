# OSPF-Part-1
In This project, I will enable OSPF on the routers, and configure them to make sure that the PC reaches the Internet.

## Platforms Leveraged
- Cisco Packet Tracer

##  Scenario

My job is to configure all the routers in network and enable OSPF on them so that PC1 can send traffic through the devices in a timely manner as well as connect to the internet.

<img width="753" height="332" alt="Screenshot 2026-03-21 at 6 23 48 PM" src="https://github.com/user-attachments/assets/cff0b307-69c5-43f1-a90b-ac6f0bed3260" />

---

## Steps Taken

### 1. Assign the largest subnet at the start of the address space. Then assign the second-largest subnet after it. Repeat the process until all subnets have been assigned.

In the lab, the largest subnet is LAN 2 with 64 hosts so this is the first subnet chosen. I borrowed seven bits so all 64 hosts can fit in the subnet. The borrowed hosts came out to 126 hosts, making LAN 2 a /25 subnet. The network address of LAN 2 is 192.168.5.0/25 when you turn all the borrowed bits into zeros. The first usable address is 192.168.5.1/25. The broadcast address is 192.168.5.127/25 because I turned all the borrowed bits into ones. Making the last usable address 192.168.5.126/25.

I repeated the process for the other three LANs including the point-to-point connection. I did the subnetting process in the screenshot below.

![IMG_3201](https://github.com/user-attachments/assets/197a3536-3a59-4fac-b6bf-451fe39e3739)

### 2. Assign the first usable address to the PC in each LAN

I went into the "Config" settings for each PC. I added the first usable address to the PC, then I added the last usuable address to the default gateway, aka the router. I repeated the steps for LAN 1, 3, and 4.

<img width="1690" height="1035" alt="Screenshot 2026-03-21 at 11 05 20 PM" src="https://github.com/user-attachments/assets/5ff7ffc0-4156-4de2-bd23-dcf4240ac781" />

### 3. Assign the last usable address to the router's interface in each LAN

I went into the router's CLI. I went into each interface, turned on the port with the command "no shutdown." I added the last usable address to the respected interface, and repeated the process for the other LANs, as well as the point-to-point connection.

<img width="1027" height="277" alt="Screenshot 2026-03-22 at 12 46 00 PM" src="https://github.com/user-attachments/assets/e32fe9b7-48b0-4123-a921-571dbb103e51" />

### 4. Configure static routes on each router so that all PCs can ping each other.

I went into each router's CLI once more and I confired the static routes so that I have a route to each LAN on the other router.

<img width="854" height="69" alt="Screenshot 2026-03-22 at 12 58 14 PM" src="https://github.com/user-attachments/assets/bed9f143-085f-4b45-93de-299f33143f18" />

### 5. Test the connection by sending pings from one PC to the next

I tested the connection to see if the PCs can oing each other. Sure enough, they did.

<img width="1090" height="860" alt="Screenshot 2026-03-22 at 1 05 01 PM" src="https://github.com/user-attachments/assets/a1f2172c-076f-4dbf-823a-e7e8c7196db7" />
