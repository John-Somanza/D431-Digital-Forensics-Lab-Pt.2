<h1>TASK 2: FORENSIC INVESTIGATION</h1>

<h2>Introduction</h2>

In today’s digital world, most fraud can be tracked electronically. In this task, you will use Basis Technology’s Autopsy application to analyze a storage device for evidence related to a possible violation of company policy. You will analyze the storage device for data files, deleted data files, directories, or drive partitions. You will need to provide screenshots of your evidence and then write a final report to present the findings to senior management.

To access the Autopsy application and the files you need to recover, you will use the “Performance Assessment Lab Area” (see Web Links section). Instructions for how to access the tools will be included in the lab area.

<h2>Software Used</h2>

- <b>Autopsy</b> 

<h2>Environments Used</h2>

- <b>Windows 10 Education virtual machine</b>

<h2>Task Walk-Through:</h2>

A1: Case Creation

<p align="center">
1.	Once I entered Autopsy, the first thing I did was create a new case. <br/>
<img src="https://i.imgur.com/MTFxVqY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
2.	I put the case name as 383064568 and the base directory to C:\Users\LabUser\Desktop\Evidence Files. <br/>
<img src="https://i.imgur.com/WVRq8zM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
3.	I set the case number and name to 383064568. <br/>
<img src="https://i.imgur.com/KHmOw09.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
4.	On the Select Host page I used the default settings. <br/>
<img src="https://i.imgur.com/0vsLJF9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
5.	For the data source type, I selected Disk image or VM file. <br/>
<img src="https://i.imgur.com/l7kZw8y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
6.	For the Data Source path, I used C:\Users\LabUser\Desktop\Evidence Files\JSmith_Q1.001. For Select Data Source I accepted the defaults. <br/>
<img src="https://i.imgur.com/cnbESuP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
7.	For the Configure Digest, I accepted the defaults. <br/>
<img src="https://i.imgur.com/yG5yHlJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

A2: Analysis

<p align="center">
8.	After the Autopsy was fully loaded, I first began my analysis by expanding the tree on  the left so that I can see what the program was able to find. <br/>
<img src="https://i.imgur.com/0MMuqwX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
9.	I then went to see the arrangement of the image under the Host Section. <br/>
<img src="https://i.imgur.com/2WOXm16.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
10.	The next step I took was to take a look at the breakdown of the file types on the image. <br/>
<img src="https://i.imgur.com/n0fvixP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
11.	Based on the results, it shows that there were 11 PDF files and 379 image files found. <br/>
<img src="https://i.imgur.com/kUaMVNB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/PhKUuG0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
12.	After this, I decided to take a look at the deleted files. From what I saw, there seemed to be very important and confidential information, including business strategies, oil strategies, etc. These files were exported into the evidence folder. <br/>
<img src="https://i.imgur.com/22AqaDe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
13.	Next, I used the keyword search for the word “confidential” to see if there were any additional sensitive information. I saved the resulting files to the Export Folder, C:\Users\LabUser\Desktop\Evidence Files\Example\Export. <br/>
<img src="https://i.imgur.com/bGv6qrC_d.webp?maxwidth=760&fidelity=grand" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
14.	Next, I used the keyword search for the word “restricted” to see if there were any additional sensitive information. I saved the resulting files to the Export Folder, C:\Users\LabUser\Desktop\Evidence Files\Example\Export. <br/>
<img src="https://i.imgur.com/C52JoAP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
15.	Next, I used the keyword search for the word “proprietary” to see if there were any additional sensitive information. I saved the resulting files to the Export Folder, C:\Users\LabUser\Desktop\Evidence Files\Example\Export. <br/>
<img src="https://i.imgur.com/X2Gzwlj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
16.	I also noticed that there were a few files about cryptocurrency, so I decided to take a look into that as well. I found that these files contained information about how to hide something in plain sight (crypto laundering), as well as how to buy bitcoin anonymously. <br/>
<img src="https://i.imgur.com/hIZh7ds.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

A3: Summary of Findings

After going through my analysis, I was presented with multiple pieces of information and evidence that could link to John Smith being involved with theft of sensitive information and unauthorized access. This is because the image of his workstation showed proprietary and sensitive documents that John had no business having access to. Some of these included business plans, oil strategies, and trade secrets. This leads us to believe that he is involved in policy violations. What was also interesting was the fact that he was looking for ways to hide information in plain sight (crypto laundering), as well as looking for ways to buy bitcoin anonymously. This leads us to believe that John was potentially trying to sell these important documents in exchange for bitcoin. With all of this evidence, it is almost, if not, certain that John Smith is in clear violation of company policies and that he is a threat to it.
 
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
