<h1>Reconnaissance with Nmap & Amap</h1>


<h2>Description</h2>
In this lab I learned to introduce Nmap the “network mapper” and its usage to perform basic network port reconnaissance and scanning. Additionally, the use of the Amap “application mapper” tool in order to determine which applications are running on listening ports..
<br />



<h2>Environments Used </h2>

- <b>Kali GNU/Linux (2.0) sana 64-bit</b> 

<h2>Program walk-through:</h2>

<p align="center">
Open a new terminal by clicking on the Terminal icon located on the left panel.: <br/>
<img src="https://i.postimg.cc/DZ98fTDQ/Screen-Shot-2022-09-10-at-8-01-38-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
<br />
Open and review Nmap’s manual by typing the "man nmap" followed by
pressing Enter.:  <br/>
<img src="https://i.postimg.cc/nzkPpFMg/Screen-Shot-2022-09-10-at-8-04-12-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
<br />
Press Q t get back to the terminal window and then type "wireshark" in the command prompt : <br/>
<img src="https://i.postimg.cc/rw2WqSW0/Screen-Shot-2022-09-10-at-8-11-56-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  

  
  
  
<br />
Minimize wireshark and then open another terminal window:  <br/>
<img src="https://i.postimg.cc/SK2J8RWF/Screen-Shot-2022-09-10-at-8-18-03-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
 
 
 
 
 
 
 <br />
In the new Terminal window, initiate a general Nmap scan with no options with command "nmap 192.168.68.12".:  <br/>
<img src="https://i.postimg.cc/6p7vVMXm/Screen-Shot-2022-09-10-at-8-20-16-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
 
 
 
 
 
 
 
  
<br />
Navigate back to the Wireshark window by clicking on the Wireshark icon located in the left panel.:  <br/>
<img src="https://i.postimg.cc/SR2h1Yxk/Screen-Shot-2022-09-10-at-8-23-16-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
  
  
  
  
  
<br />
Clear the Wireshark scan results by clicking on the Capture menu item followed by clicking on Restart..:  <br/>
<img src="https://i.postimg.cc/q7T2k2PD/Screen-Shot-2022-09-10-at-8-29-57-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
  
 <br />
Navigate back to the Terminal that the Nmap scan was initiated from, if closed, open a new Terminal. This time, initiate a specific TCP connect scan. Type the command "nmap -sT 192.168.68.12" followed by pressing Enter.:  <br/>
<img src="https://i.postimg.cc/vTfnnz6V/Screen-Shot-2022-09-10-at-8-34-00-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
   
  
  
  
  
  
  
 <br />
Once the scan is completed, navigate back to the Wireshark window. In the given Wireshark output, notice a few connections are being attempted
using [SYN, ACK] followed by a [SYN].:  <br/>
<img src="https://i.postimg.cc/sDnjcW9Q/Screen-Shot-2022-09-10-at-8-37-14-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
  
  
  
  <br />
Navigate back to the Terminal that the Nmap scan was initiated from. Nmap scans can be noisy at times with its default port scanning range. Limit
Nmap to only scan to the most popular ports by initiating the command "nmap -F 192.168.68.12":  <br/>
<img src="https://i.postimg.cc/TYQVJt4V/Screen-Shot-2022-09-10-at-8-41-31-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  
  
<br />
Use Nmap to try to identify versions of software running on the ports. Type the command "nmap -A 192.168.68.12" followed by pressing Enter.:  <br/>
<img src="https://i.postimg.cc/x8BSwvst/Screen-Shot-2022-09-10-at-8-46-16-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 
  
  
  
  
  

<br />
Notice a lot more information is given about the target machine. Nmap has a set of scripts installed we can use to test for vulnerabilities. Initiate the command "nmap -sC 192.168.68.12" to run a general set of default scripts.:  <br/>
<img src="https://i.postimg.cc/VvkVKJm4/Screen-Shot-2022-09-10-at-8-50-04-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/> 







<br />
Using Amap for Reconnaissance: Using the same Terminal window, open and review Amap’s manual by typing the command "man amap" followed by pressing Enter.:  <br/>
<img src="https://i.postimg.cc/FzhVZ8g4/Screen-Shot-2022-09-10-at-8-55-05-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>







<br />
Once finished reviewing the man page, press the Q character to quit and bring the shell prompt back. From the previous task, using Nmap, the open ports are known. Initiate an Amap scan against port 80 by typing the command "amap -A 192.168.68.12 80" followed by pressing Enter.:  <br/>
<img src="https://i.postimg.cc/zf17vybv/Screen-Shot-2022-09-10-at-8-59-08-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>






<br />
Using the same scan type, initiate a scan against port 22 by typing the command "amap -A 192.168.68.12 22". Press Enter.:  <br/>
<img src="https://i.postimg.cc/Y2fvBhk8/Screen-Shot-2022-09-10-at-9-02-40-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>








<br />
Initiate a banner grabbing command for port 22 by using the "amap -B 192.168.68.12 22".:  <br/>
<img src="https://i.postimg.cc/KzVDXfTK/Screen-Shot-2022-09-10-at-9-07-39-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
















  
  
  
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
