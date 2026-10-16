# Creating a Shared Data Folder
- Go to Windows Server and open File explorer
- Click on this PC
- Double click on Local Disk
- Create a new folder called CompanyData
- Inside of the CompanyData folder create 4 different folders called HR, IT, Finance and Public

# Create Security Groups in AD
- Right click on the User folder under Company A and hover over New and click on Group
- Name the group HRGroup with Global and Security selected and click on Ok
- Make the other groups for IT, Finance and Public
- Note: We assign permissions to groups

# Creating Test Users
- Right click on User under Company A and hover over New and click on User
- Create a new user and name it Ash Ketchum, give it a password, de-select User much change password at next logon, and select Password never expires and click on Next and then click on Finish
- Do another 2 users for the other 2 folders

# Moving the User into the Security Groups
- Right click on the user and select properties
- Click on member off and then click on Add
- Under Enter the object names to select, type in the group name and then click on Check Names and then click on Ok and then click on Apply

# Adding a group member
- Right click on the HR Group and click on properties
- Click on Members and click on add
- Under Enter the object names to select, type in the user name and then click on Check Names and click on Ok and then click on Apply and then click on OK
- Do this to the remaining user

# Configuring NTFS Permissions
- Note: Windows File Permissions - There are FTFS and Shared permissions
- Note: NTFS - NTFS are stored on drives formatted with the New Technology File System, they apply locally and over the network, there are different NTFS permission levels
- Note: Full Control - It has Read, Write, Modify, Delete and Change permissions
- Note: Modify - It can Read, Write, Edit and Delete permissions
- Note: Read & Execute - It can view files and Run programs
- Note: List Folder Contents - It can view files in a folder
- Note: Read - Open and view files
- Note: Write - Create files and Modify files

- Shared permissions - Control access when a folder is shared over the network, they apply only when accessing the folder through a network share
- Note: Example of accessing a shared folder -  \\FileServer\SharedFolder
- Note: Full Control - Read, Modify, Delete, and Change permission settings over a network
- Note: Change - Read, Write and Modify files
- Note: Read - View files & subfolders, Read data & files and Run Programs
- Note: - If someone connects to a shared folder from another computer, shared permissions determine their initial access

- How NTFS and Shared work together
- Note: When a user tries to access a shared folder on a Windows Server, NTFS permissions and Shared permissions are involved
- Note: First the user connects to the folder over the network using a path like \\FileServer\SharedFolder
- Note: The first layer of control is the share permission, share permission determine what a user can do when accessing a folder over the network
- Note: After the share permission is checked, the second layer of control is applies, which is the NTFS permission
- Note: NTFS permissions control access to the actual files and folders stored on the disk
- Note: When both permissions apply, the system calculates the effective permission and the most restrictive permission wins
- Note: Example - If the share permission allows change and the NTFS allows only read, the user will only be able to read the files
- Note: Example - If the share permission is read and NTFS is full control, the share permission is more restrictive and wins, so the user will only get read access

# Configuring NTFS
- Go back to the companydata folder and double click on it
- Right click on HR folder and click on properties
- We are going to assign HR users the modify permission and remove everyone from the HR folder so that only HR users can access
- Click on the Security tab and click Edit where it says To change permissions and then click on Add
- Under Enter the object name to select type in HRGroup and then click on Check Names, then click on Ok
- On the Permissions for HR windows, under the permission for HRGroup you can see the NTFS permission for the users
- Under Group or user names, click on HR, and then click on Modify under Allow and then click on Apply
- Now we are going to remove access to users from other departments because they currently have access to the HR folder due to inherited permissions, so we want to make sure that only the HR team can open it
- Right click on the HR folder and then click on properties again, go towards the Security Tab and then click on Advanced
- Under the Advanced Security Settings for HR, click on Disable inheritance, then click on Convert inherited permissions into explicit permissions on this object
- Note: This means it copies existing permission so we can safely modify them later on, because if you don't convert them, it will remove everything including your own access and the admin access
- Note: Converting will still keep all the permissions in place
- Now we want to do is to select all the unauthorized group that we don't want access to the HR folder
- Click on Users, there will be 2 users, and click on Remove
- Note: Best practice is to keep SYSTEM and Administrators in there as they are required for system and admin level access
- Now we are going to check the HR group still has its own permissions in here what we have set up earlier
- Click on Apply and then OK
- Do the same for Finance, IT and Public folders, give each one modify permission and then remove Users access from all 3 folders

# Configuring Share Permissions
- Go to the CompanyData folder and right click on the folder and select properties, click on the Sharing Tab and then click on Advanced Sharing
- Under the Advanced Sharing window, click on the Share this folder and then click on permissions and make sure everyone is selected and then click on Full control and Change under Permission for Everyone, click on Apply and then OK, click on Apply again and then OK, and then Close





