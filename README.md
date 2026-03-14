<br>

<p align="center">
<img src="images/WiresharkPic.jpg" alt="Wireshark Logo" width="300">
</p>

<h2>Connecting to the Windows Virtual Machine and Installing Wireshark</h2>

<p>
In the previous section, we created two virtual machines inside Microsoft Azure:
</p>

<ul>
<li>A <b>Windows virtual machine</b> that will be used to capture and analyze network traffic.</li>
<li>A <b>Linux virtual machine</b> that will be used to generate traffic across the network.</li>
</ul>

<p>
Because both machines are located inside the same <b>Virtual Network (VNet)</b>, they can communicate with each other just like computers on a local network.
</p>

<p>
In this section, we will connect to the Windows virtual machine using <b>Remote Desktop Protocol (RDP)</b> and install <b>Wireshark</b>, a network packet analyzer that allows us to capture and inspect network traffic.
</p>

---

<h3>What is Remote Desktop Protocol (RDP)?</h3>

<p>
<b>Remote Desktop Protocol (RDP)</b> is a network protocol developed by Microsoft that allows a user to remotely control another computer over a network connection.
</p>

<p>
Instead of physically sitting at the machine, RDP allows you to interact with the computer’s desktop as if you were using it locally. This is especially useful when working with cloud environments such as Azure where the machines exist in remote data centers.
</p>

<p>
In this lab, we will use RDP to connect to the Windows virtual machine so that we can install Wireshark and analyze network traffic.
</p>

---

<h3>Locating the Windows Virtual Machine Public IP Address</h3>

<p>
First, return to the <b>Virtual Machines</b> dashboard inside the Azure portal.
</p>

<br>

<p>
<img src="images/29-VMSetUP.png" alt="Azure Virtual Machines dashboard showing both machines">
</p>

<p>
Here we can see both virtual machines that were created earlier:
</p>

<ul>
<li><b>Linux-VM</b> – Ubuntu machine used to generate traffic</li>
<li><b>WiresharkAnalysis</b> – Windows machine used to analyze traffic</li>
</ul>

<p>
Notice the <b>Public IP Address</b> assigned to the Windows VM. This address allows us to remotely connect to the system from our local computer using Remote Desktop.
</p>

---

<h3>Opening the Remote Desktop Client</h3>

<p>
To connect to the Windows VM, open the <b>Microsoft Remote Desktop</b> application on your computer.
</p>

<br>

<p>
<img src="images/30-VMSetUP.png" alt="Microsoft Remote Desktop application">
</p>

<p>
Inside the application, click the <b>+</b> icon and select <b>Add PC</b>.
</p>

<p>
This option allows you to create a new remote desktop connection to a computer using its IP address.
</p>

---

<h3>Configuring the Remote Desktop Connection</h3>

<p>
Enter the <b>Public IP Address</b> of the Windows virtual machine into the <b>PC name</b> field.
</p>

<br>

<p>
<img src="images/31-VMSetUP.png" alt="Adding PC in Microsoft Remote Desktop">
</p>

<p>
You can also enter a <b>Friendly name</b> such as <b>WindowsVM</b> to make the connection easier to identify later.
</p>

<p>
Leave the other settings at their default values and click <b>Add</b>.
</p>

---

<h3>Connecting to the Windows Virtual Machine</h3>

<p>
Once the connection has been added, the Windows VM will appear under <b>Saved Devices</b>.
</p>

<br>

<p>
<img src="images/32-VMSetUP.png" alt="Saved devices showing WindowsVM connection">
</p>

<p>
Double-click the device to begin the connection process.
</p>

---

<h3>Entering Your Login Credentials</h3>

<p>
When prompted, enter the username and password that were created earlier when the Windows virtual machine was deployed.
</p>

<br>

<p>
<img src="images/33-VMSetUP.png" alt="Entering Windows VM credentials">
</p>

<p>
These credentials allow Azure to verify that you have permission to access the system.
</p>

---

<h3>Security Certificate Warning</h3>

<p>
You may see a certificate verification message when connecting for the first time.
</p>

<br>

<p>
<img src="images/34-VMSetUP.png" alt="RDP certificate warning message">
</p>

<p>
This warning appears because the remote desktop client cannot verify the certificate used by the virtual machine.
</p>

<p>
Since this is a lab environment that we created ourselves, it is safe to click <b>Continue</b>.
</p>

---

<h3>Logging Into the Windows Virtual Machine</h3>

<p>
After authentication, the Windows operating system will begin loading inside the remote desktop session.
</p>

<br>

<p>
<img src="images/35-VMSetUP.png" alt="Windows VM login screen">
</p>

<p>
Once the login process completes, you will have full access to the Windows desktop environment running inside Microsoft Azure.
</p>

<p>
From here, we can install and run software just like we would on a physical computer.
</p>

---

<h3>Installing Wireshark</h3>

<p>
Now that we are connected to the Windows virtual machine, the next step is to install <b>Wireshark</b>.
</p>

<p>
Wireshark is a powerful <b>network protocol analyzer</b> that captures packets traveling across a network and displays their contents in detail.
</p>

<p>
Security analysts, network engineers, and incident responders use Wireshark to investigate network activity, troubleshoot connectivity issues, and analyze suspicious traffic.
</p>

<br>

<h3>Completing the Windows First-Time Setup</h3>

<p>
When connecting to the Windows virtual machine for the first time, Windows will display a privacy configuration screen. This is a standard setup process that allows users to choose how certain features and diagnostic data are handled.
</p>

<p>
Since this machine is being used only for a lab environment, the default options can remain enabled.
</p>

<br>

<p>
<img src="images/36-VMSetUP.png" alt="Windows privacy settings screen">
</p>

<p>
Review the available options and click <b>Next</b> to continue.
</p>

<br>

<p>
<img src="images/37-VMSetUP.png" alt="Additional Windows privacy settings">
</p>

<p>
After reviewing the remaining privacy options, click <b>Accept</b> to complete the Windows setup process.
</p>

<p>
Once this step is finished, the Windows operating system will finish loading and display the desktop environment.
</p>

---

<h3>Opening a Web Browser</h3>

<p>
After the Windows desktop loads, open the Microsoft Edge browser. This browser will be used to download Wireshark directly onto the virtual machine.
</p>

<br>

<p>
<img src="images/38-VMSetUP.png" alt="Microsoft Edge welcome screen">
</p>

<p>
If the Edge welcome screen appears, you can click through the setup prompts or simply close the setup tabs to continue.
</p>

---

<h3>Searching for Wireshark</h3>

<p>
In the browser search bar, type <b>Wireshark</b> and perform a search.
</p>

<br>

<p>
<img src="images/39-VMSetUP.png" alt="Searching for Wireshark">
</p>

<p>
Select the official Wireshark website from the search results.
</p>

<p>
The official website is maintained by the Wireshark Foundation and provides the latest stable versions of the software.
</p>

---

<h3>Downloading Wireshark</h3>

<p>
Once the website loads, scroll down to the <b>Download Wireshark</b> section.
</p>

<br>

<p>
<img src="images/40-VMSetUP.png" alt="Wireshark download page">
</p>

<p>
Select the <b>Windows x64 Installer</b>. This version is designed for 64-bit Windows operating systems, which is the configuration used by our virtual machine.
</p>

<p>
After clicking the installer link, the Wireshark setup file will begin downloading.
</p>

---

<h3>Download Progress</h3>

<br>

<p>
<img src="images/41-VMSetUP.png" alt="Wireshark installer download progress">
</p>

<p>
The download may take a few moments depending on network speed. Once the download completes, the installer can be opened to begin the installation process.
</p>

<br>

<h3>Opening the Wireshark Installer</h3>

<p>
Once the Wireshark installer has finished downloading, navigate to the <b>Downloads</b> folder inside the Windows virtual machine.
</p>

<br>

<p>
<img src="images/42-VMSetUP.png" alt="Wireshark installer in downloads folder">
</p>

<p>
Locate the installer file named <b>Wireshark-4.6.4-x64</b>. This file contains the setup wizard that will install Wireshark onto the Windows system.
</p>

<p>
Double-click the installer to begin the installation process.
</p>

---

<h3>Wireshark Setup Wizard</h3>

<p>
After opening the installer, the Wireshark setup wizard will appear. This wizard guides users through the steps required to install the application.
</p>

<br>

<p>
<img src="images/43-VMSetUP.png" alt="Wireshark setup welcome screen">
</p>

<p>
Click <b>Next</b> to continue.
</p>

---

<h3>License Agreement</h3>

<p>
Before installing the software, Wireshark displays the license agreement. Wireshark is distributed under the <b>GNU General Public License (GPL)</b>, which allows users to freely use, modify, and distribute the software.
</p>

<br>

<p>
<img src="images/44-VMSetUP.png" alt="Wireshark license agreement">
</p>

<p>
Review the license information and click <b>Noted</b> to proceed.
</p>

---

<h3>Selecting Installation Options</h3>

<p>
The installer will now present several configuration options. These options allow users to create shortcuts and associate certain file types with Wireshark.
</p>

<br>

<p>
<img src="images/45-VMSetUP.png" alt="Wireshark installation options">
</p>

<p>
For this lab environment, the default settings are sufficient. The options to create a <b>Start Menu item</b> and a <b>Desktop icon</b> make it easier to launch Wireshark later.
</p>

<p>
Click <b>Next</b> to continue.
</p>

---

<h3>Selecting the Installation Location</h3>

<p>
Next, choose the location where Wireshark will be installed on the system.
</p>

<br>

<p>
<img src="images/46-VMSetUP.png" alt="Wireshark installation directory">
</p>

<p>
By default, Wireshark installs into the following directory:
</p>

<p>
<b>C:\Program Files\Wireshark</b>
</p>

<p>
This default location is recommended for most installations, so no changes are required for this lab.
</p>

<p>
Click <b>Next</b> to continue.
</p>

---

<h3>Installing Required Packet Capture Drivers</h3>

<p>
Wireshark requires special drivers in order to capture network packets directly from a network interface.
</p>

<p>
The installer will prompt you to install <b>Npcap</b>, a packet capture library that allows Wireshark to monitor and capture network traffic.
</p>

<br>

<p>
<img src="images/47-VMSetUP.png" alt="Npcap installation prompt">
</p>

<p>
Npcap enables Wireshark to intercept packets traveling through the system’s network adapter. Without this component, Wireshark would not be able to capture network traffic.
</p>

<p>
Leave the default options selected and proceed with the installation.
</p>

<p>
After Npcap is installed, the Wireshark installation process will complete and the application will be ready to use.
</p>

<br>

<h3>Installing the Packet Capture Driver (Npcap)</h3>

<p>
Wireshark requires a packet capture driver in order to monitor network traffic traveling through the system’s network adapter. This driver allows Wireshark to intercept and analyze packets in real time.
</p>

<p>
During the installation process, the Wireshark setup wizard will prompt you to install <b>Npcap</b>. Npcap is a packet sniffing library developed by the Nmap Project and is required for capturing network packets on Windows systems.
</p>

<br>

<p>
<img src="images/48-VMSetUP.png" alt="Npcap installation prompt">
</p>

<p>
Ensure the option to <b>Install Npcap</b> is selected, then click <b>Next</b>.
</p>

---

<h3>Optional USB Capture Support</h3>

<p>
The installer may also prompt you with an option to install <b>USBPcap</b>, which allows Wireshark to capture USB traffic.
</p>

<br>

<p>
<img src="images/49-VMSetUP.png" alt="USBPcap installation option">
</p>

<p>
Since this lab focuses on network traffic analysis rather than USB traffic, this option can remain unchecked. Click <b>Install</b> to continue.
</p>

---

<h3>Npcap License Agreement</h3>

<p>
Before Npcap can be installed, the installer will display the license agreement.
</p>

<br>

<p>
<img src="images/50-VMSetUP.png" alt="Npcap license agreement">
</p>

<p>
Click <b>I Agree</b> to proceed with the installation.
</p>

---

<h3>Npcap Installation Process</h3>

<p>
The installer will now begin installing Npcap. This process may take a few moments to complete.
</p>

<br>

<p>
<img src="images/51-VMSetUP.png" alt="Npcap installation progress">
</p>

<p>
Once the installation finishes successfully, you will see a confirmation message.
</p>

---

<h3>Npcap Installation Complete</h3>

<br>

<p>
<img src="images/52-VMSetUP.png" alt="Npcap installation finished">
</p>

<p>
Click <b>Finish</b> to close the Npcap setup wizard and return to the Wireshark installation.
</p>

---

<h3>Completing the Wireshark Installation</h3>

<p>
After Npcap has been installed, the Wireshark setup wizard will finalize the installation.
</p>

<br>

<p>
<img src="images/53-VMSetUP.png" alt="Wireshark installation complete">
</p>

<p>
Click <b>Finish</b> to complete the Wireshark installation process.
</p>

<p>
At this point, Wireshark is now installed on the Windows virtual machine.
</p>

---

<h3>Launching Wireshark</h3>

<p>
After installation, you should see a <b>Wireshark desktop icon</b> on the Windows virtual machine.
</p>

<br>

<p>
<img src="images/54-VMSetUP.png" alt="Wireshark desktop icon">
</p>

<p>
Double-click the Wireshark icon to launch the application.
</p>

---

<h3>Starting a Packet Capture</h3>

<p>
When Wireshark opens, it will display the available network interfaces on the system. These interfaces represent the network adapters that Wireshark can monitor for traffic.
</p>

<br>

<p>
<img src="images/55-VMSetUP.png" alt="Wireshark main interface showing available adapters">
</p>

<p>
To begin capturing network traffic, locate the network interface labeled <b>Ethernet</b>.
</p>

<p>
Click on <b>Ethernet</b> to start capturing packets from the network adapter.
</p>

<p>
Once the capture begins, Wireshark will start displaying network packets in real time as they travel across the system’s network interface.
</p>

<p>
In the next section of this lab, we will begin analyzing specific types of network traffic including:
</p>

<ul>
<li>DHCP (Dynamic Host Configuration Protocol)</li>
<li>DNS (Domain Name System)</li>
<li>ICMP (Internet Control Message Protocol)</li>
<li>SSH (Secure Shell)</li>
<li>RDP (Remote Desktop Protocol)</li>
</ul>

<p>
Each of these protocols plays an important role in network communication and will help demonstrate how Wireshark can be used to analyze and troubleshoot network activity.
</p>
