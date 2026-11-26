# DAY 1: Rack build and Active Directory



## Summary



Day 1 took the rack from bare hardware to a working Active Directory domain. I re-laid the rack, built a cabled local network through the patch panel, and promoted a Windows Server 2019 domain controller on Decarabia. The rack had no internet uplink yet, so most of the work was done offline. Using Claude.ai to advise and take notes on the process.



## What I did



### Rack layout

- Existing arrangement of the 12U rack bottom to top: power strip, switch, patch panel, Pi shelf, then the 4x tiny PCs and the touch display.

- Moved the 0.5U vent between the switch and the patch panel to give the switch more airflow.



### Cabling

- Set a color scheme: red for front patch cables, blue for rear runs, yellow for the router uplink.

- Checked existing connections through the patch panel: device → back of panel → front of panel → switch.

- Tested a spare cable before use. It was folded/bent during storage, and that likely damaged the internal wires. I threw the non-operational cable away.



### Network

- Rack LAN on 192.168.0.0/24, with DHCP from the TP-Link router (an Archer AX1300, planning to replace with a TP-Link Roam 6 AX1500).

- Gave Decarabia a static IP of 192.168.0.10, with DNS pointing at itself.



### Windows Server and Active Directory

- Renamed the server with `Rename-Computer -NewName "DECARABIA" -Restart` after the GUI rename didn't stick.

- Installed AD DS with `Install-WindowsFeature AD-Domain-Services -IncludeManagementTools`.

- Promoted it to a new forest: `Install-ADDSForest -DomainName "nicaea.local" -DomainNetbiosName "NICAEA" -InstallDns`.

- Confirmed it with `Get-ADDomain`.

- Created a personal domain admin account and kept the built-in Administrator as a break-glass account.



### Updates and drivers

- Activated Windows over a temporary USB Wi-Fi adapter, then ran Windows Update in rounds.

- Used hardware IDs in Device Manager to find the missing drivers. The Intel Management Engine driver fixed five of six unknown devices.

- Verified driver downloads with SHA-256 checksums.



## Troubleshooting

| Problem | Cause | Fix |
| --- | --- | --- |
| No way to get internet to the rack | The AX1300 only supports Router and Access Point modes, and both need a wired uplink. The ISP gateway doesn't support EasyMesh. | Ordered a TP-Link Roam 6 travel router with Hotspot (WISP) mode to replace it as Cerberus |
| Domain promotion failed the prerequisite check | AD Certificate Services was already installed | `Uninstall-WindowsFeature AD-Certificate`, reboot, retry |
| Roles wizard wouldn't advance | The GUI wizard stalled | Used PowerShell instead |
| "Inadequate user rights" in PowerShell | The shell wasn't elevated | Ran PowerShell as Administrator |
| Evaluation license expired | The eval period ran out | `slmgr /rearm` for a 10-day grace period, then activated with `slmgr /ato` |
| No Wi-Fi networks listed | Wireless LAN Service was missing | `Install-WindowsFeature Wireless-Networking`, then `Start-Service WlanSvc` |
| Wi-Fi connected but no internet | Weak 5 GHz signal through walls | Set the adapter to prefer 2.4 GHz |
| Slow updates and DNS timeouts | The weak Wi-Fi link was saturated, not a DNS misconfiguration | Downloaded drivers on the laptop and moved them by USB |
| Unknown devices in Device Manager | Missing chipset drivers | Intel Management Engine driver fixed five of six. The last one (LEN4001) is non-critical |
| Driver download wouldn't open | Corrupted download | Re-downloaded and verified it with a SHA-256 checksum |



## Lessons learned

- Check a router's operating modes before relying on it for a wireless uplink.
- PowerShell is more reliable than the GUI wizards, and easier to document.
- A domain controller shouldn't stay multihomed. Any extra network adapter is temporary.
- Troubleshoot in layers: ping the gateway, then a public IP, then a hostname. That separates link, routing and DNS problems.
- Verify downloads with checksums before trusting them.
- Run `git pull` before editing, so local and GitHub changes don't conflict.



## Next steps

- [ ] Set up the Roam 6 as Cerberus and retire the AX1300
- [ ] Remove the temporary Wi-Fi adapter from Decarabia and clean up any stray DNS records
- [ ] Install the SCCM driver pack to cover the last unknown device (LEN4001)
- [ ] Move DHCP to Decarabia and set up PXE network installs
- [ ] Install Proxmox on Pixie and Jack Frost
- [ ] Join machines to the `nicaea.local` domain
- [ ] Label the tiny PCs and swap in a yellow uplink cable

