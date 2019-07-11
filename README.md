---------------------------------
NOTES FOR ORCINUS ADMINISTRATION
---------------------------------

DOCUMENTATION: elder1.westgrid.ca ---> ssh orca1 ---> cd /orcinus/documentation

Roman cell:   604-822-4727
Roman office: 604-221-4830

Connect to: 
elder1.westgrid.ca -----> LDAP (Authentication server). Replica of westgrid LDAP server at SFU (www.portal.westgrid.ca), updated every 6 hours.

OR
elder2.westgrid.ca -----> MOAB (Job scheduler). Talks with resource manager (TORQUE) on orca2 to queue jobs.


From elder headnodes only, can connect on infiniband network to:
orca1 -----> Provisioning (images nodes). Backup file manager.
orca2 -----> Runs TORQUE (Resource manager - queries alle nodes, gets info about available resources). Runs main file manager.


User headnodes for orcinus.westrgid.ca:
    seawolf1.westgrid.ca
    seawolf2.westgrid.ca
    seawolf3.westgrid.ca
    Connect directly to one of the above if orcinus.westrgid.ca is not responding.


TORQUE (Resource Manager) COMMANDS:
qsub ---> Shows info about who is queued
qsort -s ----> Shows who is queuing.
qsort -c ----> Shows what jobs are running where (what nodes, etc.)
pbsnodes -ln ----> Shows which nodes are down
pbsnodes -a [nodename] -----> Shows info about a particular node


MOAB (Scheduler) COMMANDS:
showq -r ----> Currently running jobs
showq -i ----> Currently idle jobs
showq -b ----> Currently blocked jobs
showq -b | grep -v Idle -----> Shows if there are problems with any jobs.


Lustre (Filesystem) COMMANDS:
lfs check servers | grep -v active ----> Check filesystem nodes are responding.


Group Priority:
    Each group has 2% fairshare target using the fairshare algorithm.
    2% fairshare is approximately 20 cores all the time
    ndiag -P (admin only)
    Patey group: aqd-930-aa and aqd-93-ae


---------------------------------
Clean shutdown and Startup
---------------------------------
init O = shut down

1. Shut down all filesystem servers: MDS1, MDS2, OSS1, ... , OSS6

2. Shut down data storage controller 2nd: SHUTDOWN

3. Shut down discs

Do reverse process when starting up

---------------------------------
Controller
---------------------------------
To access:
    1. ssh elder1.westgrid.ca
    2. ssh orca2
    3. ssh user@mobydick1
        password is user

Commands:
    show sub fault ----> Shows any faulty discs
    show pd ----> Shows physical disks
    show vd ----> Shows virtual disksshow 
    show pool (0 - 59)


---------------------------------
COOLING SYSTEM
---------------------------------

Business Continuity Management (BCM) system automatically sends out texts if the temperature of orcinus is rising.
Contact UBC plant ops to be added to this list.

If the server room overheats, ALL breakers must be shut down ASAP.

MCS = MODULAR COOLING SYSTEM.
MCS are the controllers for the rack cooling systems
Accessible from the interactive lights out (iLO) system from:
    ssh elder1 -X ---> ssh orca2 -X ---> firefox & ---> http://mcs5 , http://mcs6 , ... , http://mcs10
    6 MCS units found on iLO system
    Username: Admin
    Password: iloadmin

MCS 6
MCS 7
MCS 8
MCS 9 ----> The rack in the back of the room with previously broken air temperature sensor (constantly detected 4 degrees C)
MCS 10 ----> The first rack in the back of the room with fan 5/6 not working.

---------------------------------
INTERACTIVE LIGHTS OUT (iLO) SYSTEM
---------------------------------

Can connect directly to (almost?) all hardware in orcinus through the HP interactive lights out system.
To connect to server packs:
    ssh elder1 -X ---> ssh orca2 -X ---> firefox & ---> https://pack1 , https://pack2 , ...
    Note: Requires X11 server on client side.


---------------------------------
HARDWARE
---------------------------------
First 12 chassis have 256 cores each.
Others have 384 cores each.


---------------------------------
FILESYSTEM
---------------------------------
Roman: "Maintaining stability of the filesystem is paramount!"


LUSTRE - mounted on orca2 and compute nodes. Connected to SFA1000 (??). Filesystem split beteween metadata (MDT) and data object storage server (OSS) nodes.
4 Separate filesystems:
    /global/home
    /global/scratch
    /global/scratchb
    ?? (Insert 4th here) ??

MDT Server:
    MDT server provides a description of the filesystem. Stores filenames, directories, permissions, and file layout.
    MDT data stored in a local disk filesystem.
    MDT server is only involved in pathname and permission checks, not involved in any file input/output operations.
    2 MDT servers for redundancy:
    MSD1.westgrid.ca
    MSD2.westgrid.ca

Object Storage Servers:
    6 OSS servers which directly access the user data.
    Object storage server nodes store file data on one or more object storage target (OST) devices.
    Capacity of the filesystem is simply the sum of capabilities of all OST's.
    Clients access and use the data on a unified namespace for all of the files and data.
    OSS1.westgrid.ca
    OSS2.westgrid.ca
    OSS3.westgrid.ca
    OSS4.westgrid.ca
    OSS5.westgrid.ca
    OSS6.westgrid.ca (Dead?)

Client Accessing a File:
    1. Filename lookup on MDS
    2. Layout of existing file returned or new file created.
    3. Client then interprets the file layout in a logical object volume layer that maps the logical file offset and size to one or more objects, each on a separate OST.
    4. Client then locks the file range being operated on and executes one or more parallel read or write operations directly on the OSS nodes.
    This system eliminates the bottlenecks for client to OSS communications.

---------------------------------
NETWORKS
---------------------------------
Infiniband (IB) fabric: connects Lustre filesystem, compute nodes, login nodes.
Uses two huge switches.
Needs to be maintained with fabric manager.
United Fabric Manager (UFM) runs in "high availability mode" on both orca1 and orca2.
Connected directly to internet (even compute nodes).

---------------------------------
SPECIAL NODES
---------------------------------
zodiac.westgrid.ca -----> Data transfer node (DTN). GLOBUS file system transfer node.
