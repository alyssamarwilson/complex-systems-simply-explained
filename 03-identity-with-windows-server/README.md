<img width="1916" height="821" alt="image" src="https://github.com/user-attachments/assets/5f0673cd-d21a-428b-97f6-25922426238e" />



##  “Identity,” “Authentication,” or “Active Directory"
When people hear these terms,” it can sound like a locked vault full of confusing rules. But identity is really about answering two big questions:
- Who are you?
- What are you allowed to access?

Think of identity like the **security system of a digital city**. Users need badges, computers need to be recognized, doors need access rules, and administrators need a way to manage it all safely.

---

## What this section covers

- Installing and configuring domain controllers
- Managing objects in Active Directory Domain Services, or AD DS
- Using graphical tools and PowerShell to manage users, groups, and computers
- Deploying and managing AD FS, AD CS, and AD RMS
- Configuring and managing Group Policy Objects, or GPOs
- Securing AD DS and user accounts
- Synchronizing identities with Azure AD
- Monitoring, troubleshooting, and recovering AD DS environments

---

## Why it matters

Before users can access files, applications, printers, email, or cloud resources, the organization needs a trusted way to verify identity.

This topic helps explain:

- how users sign in
- how permissions are assigned
- how computers join a domain
- how policies are applied
- how identity connects on-premises systems to the cloud
- how administrators protect accounts from misuse
- how Active Directory can be monitored, repaired, and recovered

Identity is one of the most important parts of IT because it controls access to almost everything.

---

## Core concepts made simple

### Active Directory = the company’s master contact book and security office

Active Directory stores information about users, computers, groups, and resources in a Windows domain.

Think of it like a company’s master directory combined with a security office. It knows who works there, what devices belong to the organization, and what each person is allowed to access.

**Simple idea:**  
Active Directory helps organize identities and control access in a Windows environment.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/fadc78ac-c8b5-4bc4-baad-11853b4d6cb1" />


---

### Domain = the digital kingdom

A domain is a group of users, computers, and resources managed together.

Instead of every computer having its own separate rules, a domain lets administrators manage identity and access from one central place.

**Simple idea:**  
A domain is a managed group of systems that trust the same identity system.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/3f16fd39-d5ce-4f8f-a5b1-118b2bb61fba" />

---

### Domain controller = the security checkpoint

A domain controller is a server that handles sign-ins and verifies identity.

When a user tries to log in, the domain controller checks their username and password. If the information is correct, it allows access based on the permissions assigned to that user.

**Simple idea:**  
A domain controller checks who you are before letting you into the network.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/f3b60ce1-041e-48c2-8574-376f03754346" />


---

### Authentication = proving who you are

Authentication is the process of proving your identity.

It is like showing your ID badge at the front desk. The system checks whether your username, password, smart card, or other sign-in method is valid.

**Simple idea:**  
Authentication answers: “Are you really who you say you are?”

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/4f139638-cb4d-4568-b247-71f94757ea31" />


---

### Authorization = deciding what you can access

Authorization happens after authentication.

Once the system knows who you are, it checks what you are allowed to do. One user may be allowed to open a shared folder, while another user may be blocked.

**Simple idea:**  
Authorization answers: “What are you allowed to access?”

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/5db9fb99-b3af-450a-9800-c80809531909" />


---

### AD DS objects = people, devices, and groups in the directory

Active Directory stores items as objects.

Common AD DS objects include:

- users
- computers
- groups
- organizational units
- printers
- shared resources

Think of each object like a labeled card inside a giant company directory.

**Simple idea:**  
AD DS objects represent the people, devices, and resources in a domain.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/5bd0644d-f3c5-4ed7-9cb6-4bf1adea864d" />


---

### Organizational Units, or OUs = folders for organizing the company

OUs help organize Active Directory objects.

They are like folders inside the directory. An organization might have OUs for departments, locations, or device types.

For example:

- HR Users
- IT Users
- Finance Computers
- San Antonio Office
- Student Lab Devices

**Simple idea:**  
OUs help administrators organize and manage Active Directory objects.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/08c39d45-32bb-4990-856e-1b84b470e68a" /> 


---

### Groups = team access passes

Groups make permissions easier to manage.

Instead of giving access to each person one at a time, administrators can place users into a group and assign permissions to the group.

For example, members of the “HR Team” group might get access to the HR shared folder.

**Simple idea:**  
Groups let administrators manage access for many users at once.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/91c21519-8ecb-4880-9327-eea715ef4ef8" />


---

### Managing AD DS with graphical tools = using the control panel

Graphical tools give administrators a visual way to manage Active Directory.

Tools like Active Directory Users and Computers let admins create users, reset passwords, move objects, create groups, and manage basic settings without typing commands.

**Simple idea:**  
Graphical tools make Active Directory easier to view and manage.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/14fb09cd-0188-4161-a2b8-c08547dff043" />


---

### Managing AD DS with PowerShell = using command shortcuts

PowerShell lets administrators manage Active Directory faster and more consistently.

Instead of clicking through menus, admins can use commands to create users, update accounts, search for objects, or automate repeated tasks.

**Simple idea:**  
PowerShell helps admins manage Active Directory with commands and automation.

<img width="1448" height="1086" alt="image" src="https://github.com/user-attachments/assets/c743683a-1437-4168-ae92-62c7b16d6592" />


---

### Group Policy = company rules sent to computers and users

Group Policy lets administrators apply rules across the domain.

A Group Policy Object, or GPO, can control settings like password rules, desktop restrictions, mapped drives, security settings, and software behavior.

Think of it like sending out a company rulebook that computers and users must follow.

**Simple idea:**  
Group Policy applies rules and settings across users and computers.

**Visual idea:**  
A steampunk messenger delivering rulebooks to different buildings in the company city.

---

### LSDOU = the order Group Policy applies

Group Policy applies in a specific order:

- Local
- Site
- Domain
- Organizational Unit

This is often remembered as **LSDOU**.

Think of it like rules being layered from broad to specific. Local rules apply first, and more specific OU rules can apply later.

**Simple idea:**  
LSDOU explains the order Group Policy settings are processed.

**Visual idea:**  
A layered stack of rulebooks labeled Local, Site, Domain, and OU.

---

### AD FS = a trusted passport office

AD FS stands for Active Directory Federation Services.

It allows users to use their organization identity to access applications outside the local domain, often through a trust relationship.

Think of AD FS like a passport office. It confirms who you are so another trusted service can let you in.

**Simple idea:**  
AD FS helps users access external applications using their organization identity.

**Visual idea:**  
A steampunk passport office issuing trusted identity passes to users traveling to cloud apps.

---

### AD CS = the certificate authority that issues digital IDs

AD CS stands for Active Directory Certificate Services.

It creates and manages digital certificates. Certificates help prove identity, secure communication, and support encryption.

Think of AD CS like an official badge-printing office. It issues trusted digital IDs that systems can use to prove they are legitimate.

**Simple idea:**  
AD CS provides digital certificates for trust and security.

**Visual idea:**  
A steampunk badge-making machine printing glowing certificates and digital ID cards.

---

### AD RMS = protecting sensitive documents

AD RMS stands for Active Directory Rights Management Services.

It helps protect documents and information by controlling what users can do with them. For example, it can limit who can open, print, copy, or forward sensitive files.

Think of AD RMS like sealing a document in a magical locked envelope that only approved people can open.

**Simple idea:**  
AD RMS helps protect sensitive information even after it leaves a shared folder.

**Visual idea:**  
A locked scroll or document vault with permissions stamped on it: Read, Print, Copy, Forward.

---

### Securing user accounts = protecting the keys to the kingdom

User accounts are powerful because they provide access to systems and data.

Securing accounts means using strong passwords, least privilege, account lockout policies, multifactor authentication, and careful admin access.

**Simple idea:**  
Protecting user accounts helps protect the entire environment.

**Visual idea:**  
A keyring labeled User Access, Admin Access, Password Policy, and MFA guarded inside a vault.

---

### Least privilege = only giving the keys someone actually needs

Least privilege means users should only have the access required to do their job.

A regular user should not have administrator access unless they truly need it. This helps reduce risk if an account is misused or compromised.

**Simple idea:**  
Least privilege means giving people only the access they need, not extra keys.

**Visual idea:**  
A security desk handing out one specific key instead of the entire master keyring.

---

### Azure AD synchronization = connecting the local directory to the cloud

Azure AD synchronization connects on-premises identities to cloud services.

This allows users to sign in to cloud resources, such as Microsoft 365 or Azure-connected services, using identities that are connected to the organization’s directory.

Think of it like building a secure bridge between the company’s local identity office and the cloud identity office.

**Simple idea:**  
Azure AD synchronization helps connect on-premises identities with cloud-based access.

**Visual idea:**  
A glowing bridge connecting an on-premises Active Directory city to a cloud city labeled Azure AD.

---

### Monitoring AD DS = watching the security dashboard

Monitoring AD DS means checking the health, performance, replication, sign-in activity, and errors in the environment.

Admins need to know if domain controllers are working, if replication is healthy, and if unusual account activity is happening.

**Simple idea:**  
Monitoring helps administrators catch problems before they become bigger issues.

**Visual idea:**  
A steampunk dashboard with gauges for Replication, Login Activity, Domain Controller Health, and Alerts.

---

### Troubleshooting AD DS = finding where the identity system broke

When users cannot sign in or access resources, administrators need to investigate.

Troubleshooting might involve checking DNS, domain controller availability, replication, account status, password issues, or Group Policy problems.

**Simple idea:**  
Troubleshooting AD DS means finding why identity or access is not working correctly.

**Visual idea:**  
A steampunk detective following clues between a user badge, DNS map, domain controller, and access door.

---

### Recovering AD DS = restoring the security office after a problem

Recovery means bringing Active Directory back after something goes wrong.

This could include restoring deleted objects, recovering a domain controller, using backups, or fixing replication problems.

**Simple idea:**  
AD DS recovery helps restore identity services when something breaks.

**Visual idea:**  
A repair crew rebuilding the security office and restoring labeled identity files from a backup vault.

---

## Suggested learning path

1. Start with the purpose of identity and access
2. Learn what Active Directory stores
3. Understand domains and domain controllers
4. Practice creating users, groups, computers, and OUs
5. Learn the difference between authentication and authorization
6. Study Group Policy and the LSDOU processing order
7. Explore AD FS, AD CS, and AD RMS as advanced identity services
8. Learn how user accounts are secured
9. Understand how identities sync with Azure AD
10. Finish with monitoring, troubleshooting, and recovery

---

## PowerShell examples

These are beginner-friendly commands that connect to this section:

```powershell
Get-ADUser -Filter *
