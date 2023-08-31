# Python-SSH-password-cracking
The purpose of this project is to showcase the application of Python and its Paramiko library in automating the process of conducting an attack to break into a target server by cracking the password that is used for login via SSH. The vulnerabilities being exploited in this case are: 1) SSH is configured with the password-based authentication mechanism enabled, which is less secure and robust compared to the key-based SSH authentication; 2) The password used for the SSH login is weak. The intention is not only to exploit vulnerabilities but also to highlight the importance of secure SSH configuration and best practices while also creating awareness about potential security risks, in network environments.

Devices and/or Technologies
-Attacker Machine: A Kali Linux (virtual machine) with Python 3 (and the Paramiko library) installed.
-Target Machine: KALI Linux properly configured as an SSH server, accepting password-based remote login (the username is “kali”, and the password is “kali”).

Summary of How Devices and/or Technologies Will Be Used
The project revolves around a controlled LAN setup comprising of an Attacker Machine and a Target Machine through the use of VirtualBox. The Attacker Machine, which is equipped with Python 3, and the Paramiko library is responsible for running a Python script that automates SSH connections and performs command execution for a designed dictionary attack, on the Target Machine., specifically the port 22 for the SSH remote login and connection. These two machines in the nominated VM environment could simulate the practical SSH connection and login in the real-world network environment, where internal IP addresses of these VMs are replaced by public ones adopted by real servers and remote users. In this regard, the demonstrated experimental process could be representative to showcase the effectiveness of the developed script.

The Attacker Machine is designated to execute the developed Python3 script to establish SSH plausible legitimate connections to the Target Machine, and automatedly perform the pre-constructed password cracking process. The script prompts the user for manual inputs, including the Target Machine’s IP address, SSH port, and username, where the Paramiko library is utilized to facilitate the establishment of SSH connections and ongoing communication, thereby enabling the automated execution of the remote login attempts. To clarify, a text file rockyou.txt (which is a simplified version with much less passwords contained for the convenience of test and demonstration) is used to feed the password list for the script to automate the password attempting process. 

The specific process of this experiment or demonstrate are as follows.
1)	In VMware, the Kali Linux VM is set up and configured as the Attacker Machine, where Python 3 and the Paramiko library are also installed.
2)	In VMware, the Kali is set up and configured as the Target Machine, where SSH service is installed, updated and configured to enable remote password-based authentication and login with the port 22 open for the ongoing use.
3)	Develop and deploy the Python3 script “SSHCracker.py” in the Kali Linux VM.
4)	Download and deploy the “Rockyou.txt” as the loading password list of the required password cracking automation.
5)	With both the Attacker Machine and Target Machine up (and all the mentioned essential services), execute the Python3 script “SSHCracker.py” in the Attacker Machine.
6)	Enter the IP address of the Target Machine (this may vary in different setting), target port number (22 in this case, which is the default port number for SSH), and the target username (“server” in this case, as pre-configured in the step 2).
7)	Wait for the end of the script execution:
  a)	If the output is “Password not found in the list.”, it indicates that the SSH password of the target is not contained in this password list provided by the “rockyou.txt”;
  b)	If the output is “Success! Password found: server”, it indicates that the SSH password of the target is successfully uncovered (as “server” in this case);
  c)	If the output is “Error: …”, it indicates that the automation has been terminated or disrupted by some reasons (network disconnection, malfunction of the VMs or  VirtualBox). Check all essentially required processes and experimental setup again.
