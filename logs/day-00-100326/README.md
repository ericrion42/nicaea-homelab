# 10/03/2026: OS Installs and BIOS Work



Team lab day. We set up the lab space, worked in the BIOS on the Lenovo tiny PCs, and ran a FreeBSD install. 



## Lab crew
- Brian Ayiteyfio

- Darius Phillips

- Eric Rion

- Mary Harbin

- Matthew Murray

- Shannon Jordan

## What we did



- Set up a shared workspace with ESD mats, monitors, keyboards and the machines we were working on.

- Opened up a Lenovo tiny PC and used the startup interrupt menu to get into the BIOS and boot options.

- Hit a BIOS password prompt on one machine. 

- Installed FreeBSD and used its partition editor to wipe and repartition the target drive.




## Troubleshooting



| Problem | Cause | Fix |
| --- | --- | --- |
| BIOS asked for a password | Old owner used a password and didn't give it to me when I purchased the unit | This was a tough one. I tried removing the CMOS battery but that didn't work. Eventually I had to locate the BIOS jumper and remove it. |




## Lessons learned



- It seems like  fewer and fewer computers can bypass the BIOS password issue just by removing the BIOS.



## Photos



<table>

<tr>

<td><img src="images/lab-space-01.jpg" width="250"><br>Lab space</td>

<td><img src="images/lab-space-02.jpg" width="250"><br>Lab space</td>

<td><img src="images/lab-space-03.jpg" width="250"><br>Lab space</td>

</tr>

<tr>

<td><img src="images/installation-os.jpg" width="250"><br>Startup interrupt menu on a tiny PC</td>

<td><img src="images/lenovo-BIOS.jpg" width="250"><br>Lenovo BIOS setup</td>

<td><img src="images/password.jpg" width="250"><br>BIOS password prompt</td>

</tr>

<tr>

<td><img src="images/installation-freebsd.jpg" width="250"><br>FreeBSD partition editor</td>

<td><img src="images/projects-01.jpg" width="250"><br>Team projects</td>

<td><img src="images/projects-02.jpg" width="250"><br>Team projects</td>

</tr>

<tr>

<td><img src="images/20261003_141430.jpg" width="250"><br>Laptop Diagnostics</td>

</tr>

</table>

