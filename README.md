<h1>Installing VM & Active Directory</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
A project created within Oracle VirtualBox, in which i created two seperate virtual machines, one running Windows Server 2022 to manage Active Directory, and the second running Windows Enterprise. I also show how to configure an internal network inside of Windows Server 2022.

During this section. I will go over how to install your Windows Server 2022 virtual machine, as well as configure the internal network and install active directory.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Windows Server 2022</b> 
- <b>Windows 11 Enterprise</b> 

<h2>Program walk-through:</h2>

<p align="center">
First, we will Create the Windows Server 2022 VM. Select the "ISO image" option and select your Windows Server 2022 ISO, make sure to check the desktop expirience under the "Type" section inside of Oracle VirtualBox  <br/>
<img src="https://imgur.com/R6Hd4qY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next, we will setup an admin username and password to boot into Windows with.  <br/>
<img src="https://imgur.com/4KN0ihY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
It's important to allocate the right amount of system memory, as well as CPU threads here. My system contains 16GB RAM, as well as a CPU containing 16 threads. Since we are not running any demanding applications on the Virtual Machine, i will allocate a quarter of RAM & CPU threads to be safe.   <br/>
<img src="https://imgur.com/3avB9Lc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Within Oracle VirtualBox, i will head to the advanced network tab and create a second network adapter under the option internal network. <br/>
<img src="https://imgur.com/Hpzae80.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Installing Windows Server 2022.  <br/>
<img src="https://imgur.com/v8uWdDq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once Windows boots into the start menu, go to settings, and then under the "Network & Internet" option, select "Adapter Settings":  <br/>
<img src="https://imgur.com/sJxxgsI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now, click on the first ethernet adapter and "Properties" pay attention to the "IpV4 address" an address starting with (example 10.0.8.12) will be the nat adapter   <br/>
<img src="https://imgur.com/8isXdtW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Once that's done, rename the second network adapter to "internal" so you can clearly differenciate between the internal network, and traffic going through the nat adapter. <br/>
<img src="https://imgur.com/T3uXGU4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now we are ready to install Active Directory, search for "Server Manager" through the Windows search bar and open it. <br/>
<img src="https://imgur.com/4BQZC7i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click on the "Manage Tab" and then "Add Roles & Features" Make sure to click the "Active Directory Domain Services" checkbox to ensure the directory is installed properly. <br/>
<img src="https://imgur.com/iuwVoXs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Click next to any further prompts, and click the "Install" button once reaching the results page.  <br/>
<img src="https://imgur.com/dAFzyPp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After that, a new page will open, here we are going to check "Add a new forest" and type in the name of our new local domain! Make sure to add .local to the end of your chosen name in order to create an internal domain.  <br/>
<img src="https://imgur.com/nGw4CzN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Continue to press next on the following prompts, and then hit the "Install" button on the "prerequisites check" page.  <br/>
<img src="https://imgur.com/nGw4CzN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
You will then be asked to restart your machine, if not then manually press windows logo, the power button and restart your machine. After doing so, the machine will apply the needed computer settings.  <br/>
<img src="https://imgur.com/UzIzOVm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Finally, open "Server Manager" again, and if successful your AD DS will be marked green, as well as anything else installed during the creating of your internal domain!  <br/>
<img src="https://imgur.com/gxBpXHt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
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
