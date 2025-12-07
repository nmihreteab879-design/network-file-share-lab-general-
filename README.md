<p align="center">
<img width="241" height="217" alt="image" src="https://github.com/user-attachments/assets/f8ef654c-2f0e-4fab-9086-6fa791e13822" />
</p>

# Network File Shares Lab


## Environments and Technologies Used
- Microsoft Azure (Virtual Machines)
- Active Directory Domain Services (AD DS)
- File Explorer & NTFS Permissions
- SMB Network File Sharing

## Operating Systems Used
- Windows Server (2019+)
- Windows 10 (21H2)

## Objectives
- Create organizational file shares  
- Apply NTFS and Share permissions correctly  
- Assign access based on security groups  
- Test user permissions and access restrictions  
- Troubleshoot unauthorized access scenarios  
- Demonstrate practical Windows file server management  

# Core Configuration Overview

What I did: 

On DC-1, I created four folders and assigned different permission levels:

- read-access → Domain Users (Read)
- write-access → Domain Users (Read/Write)
- no-access → Domain Admins only
- accounting → Left unconfigured initially

<img width="682" height="620" alt="image" src="https://github.com/user-attachments/assets/c3f2f261-7200-4f7a-8250-88cf6107c040" />


<img width="596" height="414" alt="image" src="https://github.com/user- attachments/assets/c8db5a93-28c4-45c7-a7a8-4385f2036113" />

  
<img width="912" height="675" alt="image" src="https://github.com/user-attachments/assets/4d0ce406-9eac-4f3f-836d-4b9e51026d71" />


<img width="947" height="654" alt="image" src="https://github.com/user-attachments/assets/4310b265-b6c0-44a1-87d5-d34f098a4a51" />


<img width="846" height="624" alt="image" src="https://github.com/user-attachments/assets/a9195e4a-610c-4b1d-8a14-4fa321a10496" />

 Why this matters:
 
Shared folders are core to how companies store and protect data.  
Being able to configure permissions correctly ensures employees only access what they’re authorized to see, preventing data exposure or accidental modification.

 Skills demonstrated:
 
- Creating network shared folders  
- Applying NTFS and share permissions  
- Understanding how group-based access control works  


 ## Testing Access from a Normal User (Client-1)

 What I did:  
 
Logged into Client-1 as a normal domain user and accessed `\\DC-1`.  
I tested which folders I could open and which I could create files in.

<img width="1136" height="639" alt="image" src="https://github.com/user-attachments/assets/171f5d6c-03df-4b2f-b202-06c8af38cdfe" />
  <img width="1128" height="635" alt="image" src="https://github.com/user-attachments/assets/1af22903-9e38-4739-aefb-856e730f7755" />
  <img width="1122" height="645" alt="image" src="https://github.com/user-attachments/assets/f93ad86f-fbc6-4d21-9951-b4a1b33456db" />
  <img width="1129" height="638" alt="image" src="https://github.com/user-attachments/assets/3f4e01f0-30a1-404b-a6d1-2dd37324d028" />


 Why this matters:
 
Testing access as a normal user confirms whether your permissions are set correctly.  
If an organization misconfigures this, users could accidentally gain access to confidential files.

 Skills demonstrated:
 
- Testing share permissions from a client device  
- Verifying access behavior matches the intended security design  
- Troubleshooting permission errors
  

 ## Creating an ACCOUNTANTS Security Group

  What I did: 
  
I created a security group called ACCOUNTANTS in ADUC.  
Then I gave this group Read/Write permission to the accounting network share.

<img width="757" height="529" alt="image" src="https://github.com/user-attachments/assets/3d4baabd-67c0-46ed-8c40-6e0f4a9192cf" />
<img width="632" height="451" alt="image" src="https://github.com/user-attachments/assets/4bbfc30f-417e-4fdd-a2f7-8fe47c059744" />


 Why this matters:
 
Businesses assign permissions to groups—not individual users.  
This keeps environments manageable and scalable.  
Adding a new employee to a department should automatically give them the correct access.

 Skills demonstrated:
 
- Creating AD security groups  
- Applying group-based permissions to network shares  
- Designing role-based access
  

## Assigning a User to ACCOUNTANTS & Retesting
 
What I did:  

Added the user to the ACCOUNTANTS group → access granted to the accounting folder.

<img width="404" height="461" alt="image" src="https://github.com/user-attachments/assets/8eb58a3a-7e05-4a6b-9e0f-d7b144c4f1fd" />

<img width="1131" height="638" alt="image" src="https://github.com/user-attachments/assets/92019cb9-dfa6-43cb-8601-c42cc1a856a9" />


 Why this matters:
 
This demonstrates how access is instantly changed by group membership—no reconfiguring folders.  
This is exactly how real companies automate access control at scale.

 Skills demonstrated:
 
- Managing user group membership  
- Verifying permission changes through Active Directory  
- Understanding security group propagation and access control  

 Summary:

In this lab, I configured shared folders, assigned NTFS and share permissions, created AD security groups, and verified access from a client device. These are core skills used daily in help desk, system administration, and security roles.

