# Creating OUs and Groups
- On the search bar type in Active Directory Users and Computers
- Expand the .local domain and right click on it and select hover over New and click on Organizational Unit
- In the New Object - Organizational Unit, an example would be HR, Sales and Marketing but we are going to use Company A
- Now we are going to great a new OU named Users and Computer, right click on the Marketing OU and hover over New and click on Organizational Unit again and type in User
- Right click on the Marketing OU again and over over New and click on Organizational Unit again and type in Computers
- Now create an sub OU for Users named IT, HR and Accounting under User

# Creating User Domain Admin & Regular User
- Right click on IT and hover over New and click on User and fill out with any name you like and any logon name that you like and then click on next
- Then pick a password and de-select User must change password at next logon and select password never expires and click on next and then click on finish
- To add to the Domain Admin group right click on the newly created user, click on properties, and then go to the Member Of tab, click on Add, type in Domain Admin and click on Check Names and select ok, you will see Domain Admins .local Admins along with .local Users, then click Apply and then click on Okay

- To create a Regular User click on HR, hover over New, click on User and fill out the form, pick the first name for the User logon name, and click on next, type in a password for the user and de-select user must change password at next logon and select password never expires and click on Next and then Finish

# Create a Windows 11 Client
- Download Windows 11 ISO
- Go to google and type in Download Windows 11 and click on the first link
- Scroll down and under Download Windows 11 Disk Image (ISO) for x64 devices select Windows 11 and click on confirm
- Select a product language and select confirm again
- Click on 64-bit Download and save it

# Creating a New VM
- Click on File on the VMware Workstation and click on New Virtual Machine
- Click on Custom and click on next
- Under Guest Operating System Installation, select I will install the operating system later and click on next
- Under Guest operating system select Microsoft Windows and for version select Windows 11 x64
- Under virtual machine name click on next
- Under Configure Encryption  type in a password and then click on Next
- Under Firmware Type click on next
- Under Processor Configuration click on next
- Under Memory for the Virtual Machine click on next
- Under Network Type click on Next
- Under Select I/O Controller Types click on Next
- Under Select a Disk Type click on Next
- Under Select a Disk click on Next
- Under Specify Disk Capacity type in 80Gb and click on Next
- Under Specify Disk File click on Next
- Under Ready to Create Virtual Machine click Customize Hardware and click on New CD/DVD (SATA), click on Use ISO image file and select the windows 11 ISO file and then select Close
- Under New Virtual Machine Wizard click on Finish
- Select Power on this virtual machine

# Windows 11 Pro Installation
- Press any key
- Under Select language settings click on next
- Under Select keyboard settings click on next
- Under Select setup option click on I agree and then click on next
- Under Product key click on I don't have a product key
- Under Select Image select Windows 11 Pro as Home version cannot join a domain and click on next
- Under Applicable notices and license terms click on Accept
- Under Select location to install Windows 11 click on next
- Under Ready to install click on Install

# Windows 11 Pro Installation
- Under Is this the right country or region click on Yes
- Under Want to add a second keyboard layout click on Skip
- Under Name your device type in Computer01
- Under How would you like to set up this device click on Set up for work or school to join it on a domain
- Under Let's set things up for your work or school click on Sign-in options and then click on Domain join instead
- Under Who's going to use this device enter one of the names of the user that was created earlier and the password
- Under Now add security questions, fill those out
- Under Choose privacy settings for your device click on next and then click on Accept
- Let windows update
- Once it's done sign in

# After Installion
- In Terminal type in hostname, it should say Computer01
- Type in settings in the search bar, click on Network & internet and then Ethernet
- Scroll down to DNS server assignment and click on Edit and select Manual
- Under Edit DNS settings type in the IP address of the Windows 2025 Server and then click on Save
- Go back to the Terminal and ping the Windows 2025 Server: ping Windows 2025 Server

# Joining the Domain
- Click on the file explorer, right click on This PC, click on properties, scroll down and click on Domain or workgroup
- Under System Properties click on Change and select Member of Domain and type in the domain name of the server
- Under Windows Security type in the domain admin user and press okay
- You will see a message that says Welcome to the homelab.local domain
- You will need to restart the computer

# Logging in
- The username that you will see is the domain admin user
- Click on other user and type in the user name that was created earlier
- If you are able to sign in that means that you where able to successfully able to join the domain

# Moving the computer to the appropriate OU
- On the Windows Server go to the Active Directory Users, click on the default Computers group, you will see COMPUTER01
- As best practice you will need to move it from the default Computers group to the OU that was created called Computer
- Right click on the COMPUTER01 under the default Computers group, select Move, find the Computer OU that was created earlier under Company A and select ok
- So when a computer is newly domain joined move it to the appropriate OU

# Adding a description
- Another best practice is to add a description to the computer that is newly domain joined
- TO add a description double click on it, under description you can add the user that is assigned to that computer and where its located, example: Lucas Clyne 4th floor, click on apply and then okay
