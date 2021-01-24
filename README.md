# Private-Cloud-Application-infraestracture
Private Cloud-Application infrastructure Udacity Nutanix

# Summary:

It's a company called The E-Commerce Company after a failure in our datacenter, the CEO has demanded our team come up with a better solution to prepare and handle such failure events moving forward and mitigate the downtime it caused our customers. We are given the job to design a private cloud solution for your company’s key revenue generator, an e-commerce web application.
According to our CEO, all of the VMs must be protected against failure.

# Our Tasks

Deploy and protect the three Virtual Machines composing the infrastructure for a web application: a web server VM, application VM and database server VM on the private cloud:

# Task List

• Study the provided e-mails with your E-Commerce Company IT Leaders to determine whether your organization is Cloud Ready.
• Determine the High Level Requirements from the e-mails.
• Configure an on-prem HCI environment to support VMs and implement a data protection/disaster recovery strategy to protect them.
• Your solution must also show that you are able to recover if one of your protected VMs is deleted.


# Business Requeriments.


## CTO Requeriments mail. He would like to see a 3-tier application stack with:
### Production 

Data protection using backup/restore with snapshots and no more than 1 hour of data loss after a failure.

Additional tests for VM workload expansion (cloning)
The ability to dynamically add CPU/Memory resources to online virtual machines (add 1 vCPU and 2GB memory to the database server) is required. 
Final verification is the removal of a key VM and performing a full restoration.

1) Database server VM.
2) Application server VM 
3) Web server VM 


### Development 

Additional tests for VM workload expansion (cloning)
The ability to dynamically add CPU/Memory resources to online virtual machines (add 1 vCPU and 2GB memory to the database server) is required. 

1) Database server VM.
2) Application server VM 
3) Web server VM 


## Network Operations E-mail Requirements 

### Production 

Network using IPAM/DHCP from an IP Pool provided by the Network Operations group. 
Network will be on vlan 0, using the 172.31.0.0/24 network. 
The IP Pool will use a Start address of 172.31.0.210 and an End address of 172.31.0.230.

### Development

The development network will be unmanaged on VLAN 101 using the 172.31.101.0/24 network.


## Systems Administrator E-mail Requirements 

The basic testing resource requirements for each virtual machine in the 3-tier application stack will be the same.

1) VM Microsoft SQL for the database on Windows 
 1 vCPU and 4 GB of RAM. 
2) The application server  on linux 
 1 vCPU and 4 GB of RAM.
3) Web server on Linux .
 1 vCPU and 4 GB of RAM. 

 
Configure the Network Time Protocol (NTP) using the public service, pool.ntp.org, and 8.8.8.8 for the Domain Naming Service (DNS).
You will also need to create a new storage container called Images to hold the Windows and CentOS virtual disk images (C:\Images) to be uploaded to the Image Service.
The virtual machine naming convention will be based on a 2-3 letter representation, followed by the environment. Example: Database server for Production, use db-prod. Application for development, use app-dev

The production virtual machines, when created based on the previous criteria, should be duplicated to create an identical development environment.


## Directions

Refer to the e-mails provided in the project to set the correct configurations for the following:

1.	The NTP server to the HCI Cloud Platform.
2.	The Name Server to the HCI Cloud Platform.
3.	A managed virtual network using IPAM/DHCP in the HCI Cloud Platform.
4.	An unmanaged virtual network in the HCI Cloud Platform.
5.	A storage container to the HCI Cloud Platform and upload Windows and Linux (CentOS) virtual disk images to the new container.
6.	Deploying Windows and Linux virtual machines in the HCI Cloud Platform.
7.	Creating virtual machine clones and change configurations in the HCI Cloud Platform.
8.	Creating data protection configurations to automate virtual machine snapshots.
9.	Performing virtual machine restorations using the data protection snapshots.
Make sure you review the rubric as you set the configurations for the items above.


## Solution Summary:

2 production VMs
3 development VMs
1 restored VM (clone of the deleted production VM)

Image Locations: Images
NTP = pool.ntp.org
DNS = 8.8.8.8

### Production:

Network =172.31.0.0/24
Vlan     = 0
Ip Lease = PAM/DHCP
Ip Network Start = 172.31.0.210
Ip Network End = 172.31.0.230

db-prod:

    vCPU = 1
    Ram =4 
    OS = "Microsoft SQL on Windows"
    IP= PAM/DHCP

app-prod:

    vCPU = 1
    Ram  = 4
    OS   = "Linux CentOS"
    IP   = PAM/DHCP

web-prod:
    vCPU =  1
    Ram  =  4
    OS   = "Linux CentOS"
    IP   =  PAM/DHCP

### Development :

Network  = 172.31.101.0/24
Vlan     = 101
Ip Lease = Unmanaged

A clone for each server was created for the development team

db-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Microsoft SQL on Windows"
    IP   = 172.31.101.102

app-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Linux CentOS"
    IP   = 172.31.101.100

web-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Linux CentOS"
    IP   = 172.31.101.101


