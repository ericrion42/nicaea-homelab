# Nicaea Homelab

This is a homelab environment I'm building to learn the kind of IT technician skills needed to set up, network, secure, monitor, and troubleshoot computer systems. I'm using a 10-inch mini rack to get hands-on experience as I prepare for IT and data center technician roles.

## Goals

::white_check_mark:: Obtain CompTIA A+ Certification
- [ ] Obtain CompTIA Network+
- [ ] Obtain CompTIA Security+
- [ ] Build hands-on experience in rack and stack, structured cabling, Windows Server, and Active Directory
- Maintain CompTIA A+ skills
- 


## Skills Demonstrated

- **Rack and stack:** planned rack layout, handling airflow and hardware placement to minimize heat
- **Structured cabling:** set a color-coded scheme, routed every connection through patch panel, terminated Cat6 cables to T568B, tested cables, and managed cable runs
- **Networking:** planned a /24 subnet with a router-to-switch topology, DHCP for clients, and a static IP for the server
- **Windows Server 2019:** installed Active Directory Domain Services and promoted a domain controller with PowerShell
- **Troubleshooting:** fixed missing drivers using hardware IDs, isolated DNS versus link problems, and verified downloads with SHA-256 checksums
- **Documentation:** wrote build logs, a rack layout, and a cabling standard


## Hardware

The following hardware is housed in a Tecmojo 12U, 10-inch mini rack.

| ID Name    | Hardware                                    | Role                                   |
|------------|---------------------------------------------|----------------------------------------|
| N/A        | Tecmojo 12-Port Cat6 Patch Panel, 0.5U      | Network connection/cable management    |
| N/A        | NodeQore PDU/Surge Protector 4 Rear Outlets | Power and surge protection             |
| N/A        | GeeekPi 7.84" 1280x400 LCD 2U Touch Screen  | **PLANNED:** Monitor and input         |
| N/A        | 1U 3.5" dual HDD hot-swap enclosure         | **PLANNED:** Secondary NAS             |
| Pascal     | NETGEAR GS308E 8-port switch                | Core rack switch                       |
| Cerberus   | TP-Link TL-WR1512X Roam 6 AX1500 Router     | **PLANNED:**  Edge router and firewall |
| Decarabia  | Lenovo M910q Tiny, i5-6500T, 16GB RAM       | Windows Server 2019 domain controller  |
| Pixie      | Lenovo M710q, i3-6100T, 8GB RAM             | **PLANNED:** Proxmox hypervisor        |
| Jack Frost | Lenovo M710q, i3-6100T, 8GB RAM             | **PLANNED:** Proxmox hypervisor        |
| Mothman    | Lenovo M710q, Pentium, 4GB RAM              | **UNDECIDED**                          |
| Kobold     | Dell Wyse 3040 Thin Client                  | **PLANNED:** Thin client for RDP into lab servers |
| Lilim      | Raspberry Pi 3 Model B+ Board, 3B+ (1GB)    | **PLANNED:** Pi-hole (DNS ad blocking) |
  
The following hardware is independent of the mini rack.

| Hostname    | Hardware                                       | Role                                  |
|-------------|------------------------------------------------|---------------------------------------|
| Pyro Jack   | Lenovo P330 tower, i5-8500, 8GB RAM            | **PLANNED:** Workhorse running FreeBSD Unix   |
| Shadow Jack | Lenovo M720s SFF, i5-8400T, 16GB RAM           | **PLANNED:** Hackintosh               |
| N/A         | Lenovo ThinkPad X13 Yoga, i5-10210U, 16 GB RAM | **PLANNED:** Admin laptop             |
| Tartarus    | Lenovo Iomega ix4-300d 4x-Drive NAS            | RAID monitoring, rebuilds, and repair |
  