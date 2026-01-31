📌 Project Overview

This lab uses:

2 Routers (Cisco 2911)

2 Switches (Cisco 2960)

4 End Devices (Laptops)

Point-to-point router interconnection

Each router serves its own LAN, and static routes are configured using the
ip route command to allow communication between the two LANs.

🖧 Network Topology
LAN 1 ── Switch ── Router0 ── Router1 ── Switch ── LAN 2


The full topology diagram is available in the topology/ folder.

🌐 IP Addressing Scheme
🖥️ Left LAN (192.168.1.0/24)
Device	IP Address	Default Gateway
Laptop0	192.168.1.2	192.168.1.1
Laptop1	192.168.1.3	192.168.1.1
Router0	192.168.1.1	    —

🖥️ Right LAN (192.168.3.0/24)
Device	IP Address	Default Gateway
Laptop2	192.168.3.2	192.168.3.1
Laptop3	192.168.3.3	192.168.3.1
Router1	192.168.3.1	    —

🔁 Router-to-Router Link
Router	Interface IP
Router0	10.0.0.1/30
Router1	10.0.0.2/30

🔧 Static Routing Configuration
Router0
ip route 192.168.3.0 255.255.255.0 10.0.0.2

Router1
ip route 192.168.1.0 255.255.255.0 10.0.0.1

✅ Verification

Use the following commands to verify connectivity and routing:

From PCs
ping 192.168.3.2
ping 192.168.1.2

From Routers
show ip route
show ip interface brief


Successful pings confirm that static routing is working correctly.
