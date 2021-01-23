# CTO E-mail

Hello,

In accordance with the requirements requested by you, Network Operations, Systems Administrator

We have interviewed all the business stakeholders and determined their processing needs

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
