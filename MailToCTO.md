# CTO E-mail

Hello,

In accordance with the requirements requested by you, Network Operations, Systems Administrator

We have interviewed all the business stakeholders and determined their processing needs

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


We decided to implement this configuration :

  
## Solution Summary:

Production VMs

The production environment requires built-in data protection using backup/restore with snapshots and no more than 1 hour of data loss after a failure. Additional tests for VM workload expansion (cloning), the ability to dynamically add CPU/Memory resources to online virtual machines (add 1 vCPU and 2GB memory to the database server) is required. Final verification is the removal of a key VM and performing a full restoration.

   3-tier application stack with a database server VM.
   Aplication server VM 
   Web server VM

3 development VMs
1 restored VM (clone of the deleted production VM)

Image Locations: Images
NTP = pool.ntp.org
DNS = 8.8.8.8

### Production Network:

Network =172.31.0.0/24
Vlan Tag = 0
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
Network  = 172.31.101.0/24
Vlan Tag = 101
Ip Lease = Unmanaged

A clone for each server was created for the development team

db-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Microsoft SQL on Windows"
    IP   = 172.31.101.102

App-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Linux CentOS"
    IP   = 172.31.101.100

Web-dev:

    vCPU = 1
    Ram  = 4
    OS   = "Linux CentOS"
    IP   = 172.31.101.101
