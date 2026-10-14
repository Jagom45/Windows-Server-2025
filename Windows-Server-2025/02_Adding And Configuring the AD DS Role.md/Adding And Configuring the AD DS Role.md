# Enabling Remote Management
- Open Server Manager
- Click on Local Server
- Under Properties, click on Remote Desktop and under system properties select Allow remote connections to this computer and click on Allow connections only from computers running Remote Desktop with Network Level Authentication and select apply

# Renaming
- Go to the Server Manager Window
- Click on Local Server on the right
- Click on Computer Name on the top
- Click on the Change button
- On the Computer Name/Domain Changes, type in a new name for the server and click on Ok
- Restart the Windows Server 2025 machine

# Joining a domain
- Go to the Server Manager Window
- Click on the workgroup name
- Click on the Change button
- Select Domain under Member of
- Type in a domain and press OK

# Installing Active Directory Domain Services
- Open Server Manager and click on next
- Select Role-based or feature-based installation and click on next
- On Select destination server select a server from the server pool and click on next
- On the the Select server role click on Active Directory Domain Services and click on Add Features
- On the Server Roles click on next
- On Features click on next
- On AD DS click on next
- On Confirmation click on Install
- Let the installation finish and don't close the window yet
- Once the installation is done click on Promote this server to a domain controller

 # Active Directory Domain Services Configuration Wizard
 - On Deployment Configuration select Add a new forest and enter a desired name like homelab.local
 - On Domain Controller Options make sure that Forest functional leve and Domain functional level is set to Windows Server 2025 and enter a password under Type the Directory Services Restore Mode (DSRM) password and click on next
 - On DNS options click on next for now
 - On Additional Options you can edit the NetBIOS domain name or click on next
 - On Paths click on next
 - On Review Options review that everything is correct and click on next
 - On Prerequisites Check wait for it to run and you will see All prerequisites checks passed successfully and then click on Install and let it finish
 - On the You're about to be signed out click on Close and the computer will reboot itself
 - Once it reboots, you will see the domain name and then login
 - To check the active directory tool, click on the windows button, click on All, scroll down and click on Windows Tools and then click on Active Directory Administrative Center and also group policy

# Assigning a Static IP address to the Domain Controller
- Click on the search bar
- Type in Terminal and on the terminal type in ipconfig and note the IP address and subnet
- Click on the search bar and type in settings and press enter
- Click on Network & internet and click on Ethernet
- Click on Edit for IP assignment and under Edit IP settings type in the IP address that was found under earlier and the same for Subnet mask and Gateway as well
- Restart to check that the assigned static IP address is still the same
- After restarting, click on the search bar and type in Terminal and then in the terminal type in ipconfig /all
- Go back to the settings under Network & Internet and check that IP assignment is set to Manual
