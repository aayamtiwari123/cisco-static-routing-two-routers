# cisco-static-routing-two-routers
Cisco Packet Tracer lab demonstrating static routing between two LANs using two routers, switches, and end devices.

# Cisco Static Routing Project (2 Routers, 2 Switches)

## 📌 Project Overview
This project demonstrates **static routing** in a small network using Cisco Packet Tracer.
The topology consists of **two routers connected together**, each serving its own LAN
through a switch, with end devices on both sides.

Static routes were manually configured using the `ip route` command to enable
end-to-end communication between the two networks.

---

## 🖧 Network Topology
- 2 Cisco 2911 Routers
- 2 Cisco 2960 Switches
- 4 End Devices (Laptops)
- Point-to-point router interconnection

Topology diagram is available in the `topology/` folder.

---

## 🌐 IP Addressing Scheme

### Left LAN (192.168.1.0/24)

| Device | IP Address | Default Gateway |
|------|-----------|----------------|
| Laptop0 | 192.168.1.2 | 192.168.1.1 |
| Laptop1 | 192.168.1.3 | 192.168.1.1 |
| Router0 (LAN) | 192.168.1.1 | — |

---

### Right LAN (192.168.3.0/24)

| Device | IP Address | Default Gateway |
|------|-----------|----------------|
| Laptop2 | 192.168.3.2 | 192.168.3.1 |
| Laptop3 | 192.168.3.3 | 192.168.3.1 |
| Router1 (LAN) | 192.168.3.1 | — |

---

### Router-to-Router Link

| Router | Interface IP |
|------|--------------|
| Router0 | 10.0.0.1/30 |
| Router1 | 10.0.0.2/30 |

---

## 🔁 Static Routing Configuration

### Router0
```bash
ip route 192.168.3.0 255.255.255.0 10.0.0.2
