<h1>TASK 2: FORENSIC INVESTIGATION</h1>

<h2>Introduction</h2>

In today’s digital world, most fraud can be tracked electronically. In this task, you will use Basis Technology’s Autopsy application to analyze a storage device for evidence related to a possible violation of company policy. You will analyze the storage device for data files, deleted data files, directories, or drive partitions. You will need to provide screenshots of your evidence and then write a final report to present the findings to senior management.

To access the Autopsy application and the files you need to recover, you will use the “Performance Assessment Lab Area” (see Web Links section). Instructions for how to access the tools will be included in the lab area.

<h2>Software Used</h2>

- <b>Autopsy</b> 

<h2>Environments Used</h2>

- <b>Windows 10 Education virtual machine</b>

<h2>Task Walk-Through:</h2>

A. Network Topology

<p align="center">
Screenshots of running Nmap: <br/>
<img src="https://i.imgur.com/mbK9uXv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Screenshot of Zenmap Topology:  <br/>
<img src="https://i.imgur.com/zN2STZu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 
The network topology I found when running Nmap was the star topology, as shown above. This network consists of 6 hosts, with 3 of them being Linux machines, 2 of them being Windows Servers, and the last one being an unknown device. The addresses of these 6 hosts are:
 
-	10.168.27.10 (Microsoft Windows Server 2012 or Windows Server 2012 R2)
-	10.168.27.15 (Microsoft Windows Server 2008 R2 or Windows 8.1)
-	10.168.27.1 (Unknown device)
-	10.168.27.14 (Linux 2.6.32)
-	10.168.27.20 (Linux 2.6.32)
-	10.168.27.13 (Linux 2.6.32)

B. Summary of Vulnerabilities and Implications

<p align="center">
First vulnerability
and the potential implications:

Regarding 10,168.27.14, 10.168.27.20, and 10,168.27.13, I noticed that they were all running Linux 2.6.32 as their OS. The reason why I brought this up is because this specific version of Linux is actually vulnerable to DOS (Denial of Service) attacks, and this can be seen in the NVD (national Vulnerability Database), specifically in the CVE dictionary entry CVE-2019-17351.

The potential implications with this vulnerability are service disruptions and complete unavailability of the targeted service. By sending an overwhelming amount of traffic to the targeted system’s resources, the attacker can cause the victim to become incapable of responding to legitimate requests.

<p align="center">
<img src="https://i.imgur.com/gGqkZt1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/Qt3oxIZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<img src="https://i.imgur.com/g0jP07Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Second vulnerability
and the potential implications:

Regarding 10.168.27.15, I noticed that tcp port 21 (FTP) is open and is running FileZilla ftpd. FTP, aka File Transfer Protocol, is a protocol that transfers files in clear text rather than encryption, which makes it very easy for attackers to intercept the traffic and use the acquired information for malicious purposes since they can see exactly what it is they acquired.

<p align="center">
<img src="https://i.imgur.com/kXuDZts.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

<p align="center">
Third vulnerability
and the potential implications:
 
Once again, regarding 10.168.27.15, I noticed that this host was running Microsoft Windows 7 Professional or Windows Server 8 as their OS. I reason why I brought this up is because Windows 8 has reached it’s end-of-life cycle, meaning that it no longer receives critical security updates. In summary, although it is still usable, the vulnerabilities that are there won’t be able to be patched and will just remain there.

An example of a vulnerability here is specifically stated in the CVE dictionary entry CVE-2015-0014. In simple terms, this states that the Telnet service is open to buffer overflow, which allows remote attackers to execute arbitrary code via crafted packets, aka “Windows Telnet Service Buffer Overflow Vulnerability.” The problem with this is that since this OS has reached its end of life cycle, there is no patch to resolve this issue so the vulnerability will simply remain as a result.

C.  Wireshark Anomalies

<p align="center">
First Anomaly 
and evidence, plus the range of packets:

I used the Pcap1.pcapng file for this assignment. The first anomaly I discovered was a large amount of traffic being sent from 10.16.80.243 to the 10.168.27.0/24 network. The enemy was most likely trying to scan all the ports to map out the network and see what they could discover.

<p align="center">
<img src="https://i.imgur.com/K07byHd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Second Anomaly
and evidence, plus the range of packets:

The second anomaly I found is in relation to the previous nmap scan that we did. When filtering for the FTP protocol, I noticed that 10.168.27.10 was using FileZilla File Transfer Protocol. This protocol doesn’t use any encryption, therefore making it very easy for the enemy to intercept important information such as username and password credentials.

<p align="center">
<img src="https://i.imgur.com/b1EHZ3G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

D. Implications of each Wireshark Anomaly

Implications of taking no action 1:

In regards to the first anomaly, the implications of taking no action on the attacker sending mass amounts of traffic is the allowance of the attacker to see which ports were open, which OS were running, and as a result seeing what the path of least resistance would be for them to continue their attack.

Implications of taking no action 2:

In regards to the second anomaly, the implications of not taking action on the FTP server is a possible interception of sensitive information from users logging into the FTP server. In this case, as shown in Pcap1, this included passwords, usernames, and IP addresses. With this information open in clear text, an attacker can collect this information with ease and use it to manipulate the server settings, delete users and conduct unauthorized actions.

E.  Recommended Solutions

First Vulnerability:

Update it to the latest version or have it taken off the network completely. The recommended solution would be to upgrade the OS to version 5.3.2 (Snyk Vulnerability Database | Snyk. (n.d.). 

Second Vulnerability/Anomaly:

Block traffic coming from FTP and not allow any FTP software to be installed. The recommended solution would be to sue a more secure version of FTP, such as SFTP (What Is FTP (File Transfer Protocol)? Definition, Uses, and Best Practices for 2022. (n.d.).

Third Vulnerability:

Update it to the latest version of Windows that can receive security updates or remove it off the network completely. The recommended solution is to upgrade the OS to the latest version before the end of cycle is reached which was in January 2020. This was announced by Microsoft. (Windows Server 2008 (R2) End of Life | What to Do Now? (n.d.).

First Anomaly:

Use a port scanner to monitor the network on a regular basis as well as close unnecessary ports.

<p align="center">
References:

<p align="center">
NVD. (n.d.). https://nvd.nist.gov/vuln/detail/CVE-2019-17351

<p align="center">
NVD. (n.d.). https://nvd.nist.gov/vuln/detail/CVE-2015-0014

<p align="center">
The Linux Kernel Archives. (n.d.). https://cdn.kernel.org/pub/linux/kernel/v5.x/ChangeLog-5.2.3 

<p align="center">
SNYK vulnerability database: Snyk. Learn more about Unmanaged (C/C++) with Snyk Open Source Vulnerability Database. (n.d.). https://security.snyk.io/vuln/SNYK-UNMANAGED-TORVALDSLINUX-3006273

<p align="center">
FTP definition, uses, best practices. Spiceworks. https://www.spiceworks.com/tech/networking/articles/what-is-ftp/#:~:text=April%2012%2C%202022,ten%20best%20practices%20for%20operation.

<p align="center">
Maggie. (n.d.). Windows server 2008 (R2) end of life: What to do now?. Windows Server 2008 (R2) End of Life | What to Do Now? https://www.ubackup.com/windows-server/windows-server-2008-end-of-life-3889.html 
 
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
