# Network File Shares & Permissions (Active Directory Lab)

This lab focuses on creating network file shares, configuring NTFS and share permissions, and testing real-world access control using Active Directory security groups. The point of the lab is to understand how Windows organizations control who can access which folders on a company network.

---

## Creating Shared Folders on DC-1

**Screenshots to include:**
- The 4 folders on C:\ (`read-access`, `write-access`, `no-access`, `accounting`)
- The sharing/permissions windows for each folder

**What I did:**  
On DC-1, I created four folders and assigned different permission levels:
- **read-access** → Domain Users (Read)
- **write-access** → Domain Users (Read/Write)
- **no-access** → Domain Admins only
- **accounting** → Left unconfigured initially

### Why this matters
Shared folders are core to how companies store and protect data.  
Being able to configure permissions correctly ensures employees only access what they’re authorized to see, preventing data exposure or accidental modification.

### Skills demonstrated
- Creating network shared folders  
- Applying NTFS and share permissions  
- Understanding how group-based access control works  

---

## Testing Access from a Normal User (Client-1)

**Screenshots to include:**
- `\\DC-1` file share window on Client-1  
- Attempts to open each folder (success/failure messages)

**What I did:**  
Logged into Client-1 as a normal domain user and accessed `\\DC-1`.  
I tested which folders I could open and which I could create files in.

### Why this matters
Testing access as a normal user confirms whether your permissions are set correctly.  
If an organization misconfigures this, users could accidentally gain access to confidential files.

### Skills demonstrated
- Testing share permissions from a client device  
- Verifying access behavior matches the intended security design  
- Troubleshooting permission errors  

---

## Creating an ACCOUNTANTS Security Group

**Screenshots to include:**
- ACCOUNTANTS security group in ADUC  
- Accounting folder permissions showing ACCOUNTANTS (Read/Write)

**What I did:**  
I created a security group called **ACCOUNTANTS** in ADUC.  
Then I gave this group Read/Write permission to the **accounting** network share.

### Why this matters
Businesses assign permissions to groups—not individual users.  
This keeps environments manageable and scalable.  
Adding a new employee to a department should automatically give them the correct access.

### Skills demonstrated
- Creating AD security groups  
- Applying group-based permissions to network shares  
- Designing role-based access  

---

## Assigning a User to ACCOUNTANTS & Retesting

**Screenshots to include:**
- User properties showing group membership  
- Successful access to the accounting share after membership is applied

**What I did:**  
Attempted access as a non-accountant → access denied.  
Added the user to the ACCOUNTANTS group → access granted.

### Why this matters
This demonstrates how access is instantly changed by group membership—no reconfiguring folders.  
This is exactly how real companies automate access control at scale.

### Skills demonstrated
- Managing user group membership  
- Verifying permission changes through Active Directory  
- Understanding security group propagation and access control  

---

## Summary

In this lab, I configured shared folders, assigned NTFS and share permissions, created AD security groups, and verified access from a client device. These are core skills used daily in help desk, system administration, and security roles.

