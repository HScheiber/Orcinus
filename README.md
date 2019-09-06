NOTES FOR ORCINUS ADMINISTRATION
==============================

Table of Contents
-------------------
-   [General](https://github.com/HScheiber/Orcinus/blob/master/README.md#General)

-   [Basic Nodes and Their Functions](https://github.com/HScheiber/Orcinus/blob/master/README.md#Basic-Nodes-and-Their-Functions)

-   [Administator servers](https://github.com/HScheiber/Orcinus/blob/master/README.md#Administator-servers)

-   [MDS](https://github.com/HScheiber/Orcinus/blob/master/README.md#MDS)

-   [Emergency Shutdown Procedure](https://github.com/HScheiber/Orcinus/blob/master/README.md#Emergency-Shutdown-Procedure)

-   [COOLING SYSTEM](https://github.com/HScheiber/Orcinus/blob/master/README.md#COOLING-SYSTEM)

-   [INTERACTIVE LIGHTS OUT (iLO) SYSTEM](https://github.com/HScheiber/Orcinus/blob/master/README.md#INTERACTIVE-LIGHTS-OUT-iLO-SYSTEM)

-   [HARDWARE](https://github.com/HScheiber/Orcinus/blob/master/README.md#HARDWARE)

-   [FILESYSTEM](https://github.com/HScheiber/Orcinus/blob/master/README.md#FILESYSTEM)

-   [NETWORK](https://github.com/HScheiber/Orcinus/blob/master/README.md#NETWORK)

-   [Queuing System](https://github.com/HScheiber/Orcinus/blob/master/README.md#Queuing-System)

-   [SPECIAL NODES](https://github.com/HScheiber/Orcinus/blob/master/README.md#SPECIAL-NODES)

-   [How to Configure New Nodes](https://github.com/HScheiber/Orcinus/blob/master/README.md#How-to-Configure-New-Nodes)

-   [Nodes Currently Down and Reasons](https://github.com/HScheiber/Orcinus/blob/master/README.md#Nodes-Currently-Down-and-Reasons)


General
==============================

-   All kinds of documentation: elder1.westgrid.ca ---> ssh orca1 ---> cd /orcinus/documentation
-   Roman cell:   604-822-4727
-   Roman office: 604-221-4830

User headnodes for orcinus.westrgid.ca:
-   seawolf1.westgrid.ca
-   seawolf2.westgrid.ca
-   seawolf3.westgrid.ca
-   Connect directly to one of the above if orcinus.westrgid.ca is not responding.


TORQUE (Resource Manager) COMMANDS:
-   `qsub` ---> Shows info about who is queued
-   `qsort -s` ----> Shows who is queuing.
-   `qsort -c` ----> Shows what jobs are running where (what nodes, etc.)
-   `pbsnodes -ln` ----> Shows which nodes are down
-   `pbsnodes -a [nodename]` -----> Shows info about a particular node


Group Priority:
-   Each group has 2% fairshare target using the fairshare algorithm.
-   2% fairshare is approximately 20 cores all the time
-   `ndiag -P` (admin only)
-   Patey group: aqd-930-aa and aqd-93-ae


Basic Nodes and Their Functions
==============================

For these nodes, appending .ibb to their names references the nodes via the
IB fabric, while appending .admin through the administrative network.  So,
ssh orca1.admin logs you into orca1 over the administrative network rather
than the regular user network.  Adding .console accesses the management network
on which sites the ILO cards and other access to controlling elements of
various cluster components.  For security reasons, this latter network is only
accessible from certain nodes, like orca1 and orca2. 

orca1 and orca2 can be reached only from within the network. Use elder[1,2] and ssh tunnel.

orca1
-   provisioning (CMU?), backup manager, httpd, sendmail, dhcp
-   syslog host (all in /var/log and subdirectories thereof)

orca2
-   scheduling resource manager (torque) and file manager, sendmail
-   license manager, httpd


-   orca[1,2] redundantly manage IB fabric (UFM - United Fabric Manager)
-   have a heartbeat that monitors this.
-   are ntp servers for the compute nodes (they synchronize to elder[1,2])

Administator servers:
-------------------------

elder1.westgrid.ca
-   authentication (LDAP) www.portal.westgrid.ca connected to database
-   Replica of westgrid LDAP server at SFU (www.portal.westgrid.ca), updated every 6 hours.
-   denyhosts service, pop3, imap, httpd
-   doesn't have /global/software, /global/system, or any Lustre
-   filesystems mounted (is there a reason for that?)

elder2.westgrid.ca
-   job scheduling (MOAB). Talks with resource manager (TORQUE) on orca2 to queue jobs.
-   denyhosts service, sendmail


-   elder[1,2] are outward facing servers
-   are ntp servers for orca[1,2] and then into the rest of the cluster
-   ntp (synchronized to time.nrc.ca and ntp1.ubc.ca)


MDS:
-------------------------

mds[1,2] - metadata servers for Lustre filesystem.

  mds - virtual IP for NFS mounting of filesystems (also called ahab).
  Be careful here.... interface ib0:1 is the virtual one for ahab and
  BOTH mds1 and mds2 have this configured.  /global/software and
  /global/system are exported from /orcinus which is a directory sitting
  on the same storage pool that holds the metadata.  Thus, both mds1 and
  mds2 can mount /orcinus.  However, you only want ONE of these to
  actually serve the /orcinus filesystem.  Right now, that is mds2.
  If you reboot mds1 and it automatically configures ib0:1, then you'll
  have 2 different machines serving the same virtual IP, and this will
  cause NFS to conflict.  In that case, you have to set ib0:1 to DOWN
  to disable the interface.  Also, it seems that NFS is not configured
  to start automatically, so if mds2 is rebooted, you need to make sure
  /orcinus is mounted, and that ib0:1 is UP, and then you start NFS to
  export everything to the cluster.  THIS STUFF IS IMPORTANT BECAUSE THE
  CLUSTER WILL NOT WORK PROPERLY IF /global/software and /global/system
  ARE NOT AVAILABLE.


oss[1-6] - object storage servers for Lustre filesystem

mobydick[1,2] - main disk controllers (DDN SFA10000)

seawolf[1-2] - head nodes

podX[a,b]Y 

-   compute node in chassis X and blade Y,
    The 'a' or 'b' specifies the A or B node (each blade is composed of two nodes).

-   IP addresses for compute nodes follow a regular pattern
         192.168.abb.ccc with a = 1 for A nodes and 2 for B nodes,
         bb = chassis number [0-29], and ccc = node number [1-16] for IB,
         172.16.abb.ccc and 10.1.abb.ccc for admin and console networks.
         network, 172.16.abb.ccc for admin network.
-   chasses [0-12] are old blades, housing 8-core nodes
-   chasses [13-29] are new blades, housing 12-core nodes



Emergency Shutdown Procedure
==============================

1. Use `init 0` to shutdown all compute nodes and head nodes.  Turn off breakers.
2. If room temperature is OK, leave storage and disks up and running.  If not,
   first shutdown Lustre filesystem (oss and mds servers shutdown) then turn
   off the storage controllers, then shut down the disks.
3. The storage components and switches are under UPS power so should survive
   short power outages.  So, unless the temperature in the room requires it,
   they can be kept up and running.  The compute nodes generate most of the
   heat in the room.
4. Open up the secret vent if added airflow is needed on an emergency basis.
5. Alert Plant Ops if the chiller doesn't seem to be coming back on.
6. Website for temperature of cluster over time:

   https://elder1.westgrid.ca/room_temps

Do reverse process when starting up


COOLING SYSTEM
==============================

Business Continuity Management (BCM) system automatically sends out texts if the temperature of orcinus is rising.
Contact UBC plant ops to be added to this list.

-   If the server room overheats, ALL breakers must be shut down ASAP.

MCS = MODULAR COOLING SYSTEM.
-   MCS are the controllers for the rack cooling systems

MCS accessible from the interactive lights out (iLO) system:
-   `ssh elder1 -X` ---> `ssh orca2 -X` ---> `firefox &` ---> In the firefox browser: `http://mcs5` , `http://mcs6` , ... , `http://mcs10`
-   6 MCS units found on iLO system
-   Username: `Admin`
-   Password: `iloadmin`


-   MCS 6
-   MCS 7
-   MCS 8
-   MCS 9 ----> The rack in the back of the room with previously broken air temperature sensor (constantly detected 4 degrees C)
-   MCS 10 ----> The first rack in the back of the room with fan 5/6 not working.

INTERACTIVE LIGHTS OUT (iLO) SYSTEM
==============================

Can connect directly to (almost?) all hardware in orcinus through the HP interactive lights out system.
To connect to server packs:
    `ssh elder1 -X` ---> `ssh orca2 -X` ---> `firefox &` ---> `https://pack1` , `https://pack2` , ...
    Note: Requires X11 server on client side.
    For windows, download [xming](https://sourceforge.net/projects/xming/).


HARDWARE
==============================
-   First 12 chassis (old style) have 256 cores each.
-   Others have 384 cores each.


FILESYSTEM
==============================
Roman: "Maintaining stability of the filesystem is paramount!"


Lustre filesystem works by separating metadata and data.  Metadata (that is,
creation and modification times, owners, permissions, etc. of files) is stored
on fast storage and served by MDT servers (called mds1 and mds2).  These are
redundant so if one fails the other can take over the other's job.  When
filesystems are mounted, it is from the mds's that the filesystem is served
since this contains all the information that constructs the filesystem itself.
When you type ls -l the information you see comes from the metadata servers.
So a slow ls -l response indicates heavy load on the mds servers.

Once you want the contents of a file (for writing or reading) the mds servers
tell the nodes the locations of the data for a file.  The actual file contents
are stored separately on OST servers (oss1-6).  These servers are directly
connected with the main storage controllers and return the file contents as
requested.  Files may be split over multiple OSTs (called striping) so that
in principle, all 6 servers could be simultaneously returning different parts
of the file.  This makes the filesystem parallel and increases responsiveness,
especially for large files.  If reading or writing a file is slow, it might
be because the oss's are heavily loaded.  In principle, there is redundancy
among the oss's but this is not automated.  So, different OSTs have to be
manually mounted and unmounted.

Commands for monitoring and diagnosing filesystem issues:

1. Check loads on oss and mds servers with top or w.  If high, indicates heavy
   demand from cluster.

2. `lfs check servers [| grep -v active]`

   (gives a listing of all OST and MDT - all entries should say "active".  If
    any are inactive then it indicates a failed oss or mds server)

3. If oss and mds servers look OK, and things are showing as active, then it
   may be a problem with the storage controllers themselves.  To check this
   you need to login to the controllers (mobydick[1,2]) and diagnose further.

4. If oss or mds are not responding, rebooting is probably a good first thing
   to try.

5. When starting the filesystem after a power failure or other catastrophic
   event, first make sure the disks are spinning and everything looks ready
   on the controllers.  Then start the mds and oss servers (in that order?).
   Do we have to manually mount the OSTs on the osses?  What is the name of
   the script for doing that?  Only after everything is ready on the oss and
   mds servers do you then reboot the nodes (which in turn will mount the
   Lustre filesystem on them).

6. Lustre is fairly good at recovering from events and will expel nodes that
   have issues.  So, unless drastic action is needed, it shouldn't be necessary
   to reboot Lustre entirely for most problems.

7. On the controllers (ssh user@mobydick1 from orca2, password user), the
   following commands can help examine things:
-   `show sub fault`
-   `show pd` (physical disks)
-   `show vd` (virtual disks)
-   `show pool (0-59)`

LUSTRE - mounted on orca2 and compute nodes. Connected to 2x SFA10000 controllers. Filesystem split beteween metadata servers (MDS) and data object storage server (OSS) nodes.
4 Separate filesystems:
-   `/global/home`
-   `/global/scratch`
-   `/global/scratchb`
-   `/global/data`

Two MDS for redundancy:
-   `MSD1.westgrid.ca`
-   `MSD2.westgrid.ca`

Object Storage Servers:
-   6 OSS servers which directly access the user data.
-   Object storage server nodes store file data on one or more object storage target (OST) devices.
-   Capacity of the filesystem is simply the sum of capabilities of all OST's.
-   Clients access and use the data on a unified namespace for all of the files and data.
-   OSS1.westgrid.ca
-   OSS2.westgrid.ca
-   OSS3.westgrid.ca
-   OSS4.westgrid.ca
-   OSS5.westgrid.ca
-   OSS6.westgrid.ca

Client Accessing a File:
    1. Filename lookup on MDS
    2. Layout of existing file returned or new file created.
    3. Client then interprets the file layout in a logical object volume layer that maps the logical file offset and size to one or more objects, each on a separate OST.
    4. Client then locks the file range being operated on and executes one or more parallel read or write operations directly on the OSS nodes.
    This system eliminates the bottlenecks for client to OSS communications.

NETWORK
==============================

-   Infiniband (IB) fabric: connects Lustre filesystem, compute nodes, login nodes.
-   Uses two huge switches.
-   Needs to be maintained with fabric manager.
-   United Fabric Manager (UFM) runs in "high availability mode" on both orca1 and orca2.
-   Connected directly to internet (even compute nodes).


196.182.xxx.xxx - IB fabric (available everywhere) [.ibb]
172.16.xxx.xxx	- administration GigE network (available everywhere) [.admin]
10.1.xxx.xxx	- console GigE network (available from orca[1,2]) [.console]
206.12.24.16[1-5,9] - WestGrid external network

mcs[5-10].console	- rack MCS management cards
squidups.console	- UPS Management Port
squid*		- Rack PDU Management Cards
sonar*		- Switch Management Ports
pack?		- Chassis Onboard Administrators

Use UFM to monitor IB fabric.  Usually the gigabit fabrics are problem free.
Lights on the switches and on the network cards can also be checked to see
whether any "bad" lights are showing.

`ndiag -P`


Queuing System
==============================

Job queuing has two components: torque and moab.

Torque monitors all the jobs on the nodes, starts and stop them, and keeps 
track of them while they are running.  This is done by communicating with
pbs_mom processed running on each node.  These daemons are in contact with the
main torque server and report information.  This is now torque knows the loads
on each node, what is running there, etc..  So, if the pbs_mom daemons die,
the nodes will be invisible to torque and any jobs running there will no
longer be actively monitored.  However, such jobs can still be running even
though the pbs_mom has died.  If torque dies, jobs can't be monitored or
started.

Moab is in control of job scheduling.  It looks at all the jobs in the queue
and through algorithms, decides which jobs should run next.  It does this by
scanning the queue, matching job requirements with node availability, and
weighting with fairshare targets.  Moab then tells torque which jobs to run.
If moab isn't running, 

Commands to monitor queuing system

1. `qsort -s` (summary of running jobs)
2. `qsort -c` (status of chasses)
3. `pbsnodes -ln` (info about downed nodes)
4. `pbsnodes -a <nodename>`
5. `showq -r` (running jobs)
6. `showq -i` (idle jobs)
7. `showq -b` (blocked jobs)
8. `showq -b|grep -v Idle` (shows problems with jobs)

`showq` is in /global/system/moab/bin/ as well as other useful commands like
`mstats`, `mshow`, `mdiag`?


SPECIAL NODES
==============================
- `zodiac.westgrid.ca` -----> Data transfer node (DTN). GLOBUS file system transfer node.

How to Configure New Nodes
==============================

Follow these steps when node components have been replaced in order to insure proper uptake into the network. BIOS configuration will require the default password of 

1. Login into orca2 with X and open firefox: `ssh <adminusername>@elder1.westgrid.ca -X` ---> `ssh orca2 -X` ---> `firefox &`

2. In firefox, go the chassis containing the blade in question: `https://pack<#>` and click `add exception`. Login to ILO. 
- Username: `admin`
- Password: `iloadmin`

3. Click on `Device Bays` on the side panel and find the node in question. If it does not have a proper node name (i.e. podX[a|b]Y) then it needs to be reconfigured. Click on the blade name ---> `iLo` ---> `Web Administation` to access the blade.

4. Click on the `Administration` tab. If the blade does not currently have firmware version 2.23 or higher, it must be updated. A version 2.23 firmware image is located in `/tmp/ILO/ilo2_223.bin`. Click `Browse...` and find this file, then `Send firmware image`. This will load new firmware and reset the ILO. After resetting, you will be logged out of the blade. It is easiest to log back in through the chassis ILO as in step 3.

5. Once you are back into the blade ILO and have confirmed the firmware is version 2.23 or higher, go back to the `Administration` tab and click `User Administration` on the side panel. If user `root` does not exist, add it by clicking `New`. The User Name and Login Name should both be `root` and the password should be the root password if you know it. Otherwise set any old password and tell the head administator to change it later.

6. Go to `Access` under `Settings` in the side panel. Click the `Options` tab. Beside `Server Name:` make sure the node is named `podX[a|b]Y`. `X` = the chassis number, choose `a` if this is an A-blade in a pair or `b` if it is a B-blade. Y = blade number. Click `Apply` after changing the name.

7. Go to the `Services` tab and change `Secure Shell (SSH) Port:` to `30`. Click `Apply`. This will reboot the ILO again. After resetting, log back in as before.

8. Return to the `Administation` tab and click on `Security` under `Settings`. Add the SSH key file from `/tmp/ILO/cluster_id.pub.root` and click `Authorize Key`.

9. Now click on `Network` under `Settings`. Change the `iLO 2 Subsystem Name` to `podX[a|b]Y-ilo` using the same convention as before. Click `Apply`. The ILO will reset, but that is the end of the ILO part of the configuration. You can close the browser tab.

Next the BIOS settings must be configured.

10. You may use the default administrator password which is shipped with the blade here. From orca2, `ssh Administrator@podX[a|b]Y.console -p 30` and input this password. Otherwise, since you just added another account to the ILO (user   `root`), you can log in with that account. You can also replace `ssh` with `cluster_c` to use for internal access through the administrator network.

11. Once you are into the blade. Type in `power reset` or `power warm` followed quickly by `vsp`. This will reboot the blade and bring you into the virtual serial port. You should see the following:

```
Starting virtual serial port.
Press 'ESC (' to return to the CLI Session.

</>hpiLO-> Virtual Serial Port active: IO=0x03F8 INT=4
                            24 GB Installed

ProLiant System BIOS - I26 (01/30/2011)
Copyright 1982, 2011 Hewlett-Packard Development Company, L.P.


2 Processor(s) detected, 12 total cores enabled, Hyperthreading is enabled
Proc 1: Intel(R) Xeon(R) CPU X5650 @ 2.67GHz
Proc 2: Intel(R) Xeon(R) CPU X5650 @ 2.67GHz
QPI Speed: 6.4 GT/s
HP Power Profile Mode: Balanced Power and Performance
Power Regulator Mode: Dynamic Power Savings

Advanced Memory Protection Mode: Advanced ECC Support
Redundant ROM Detected - This system contains a valid backup system ROM.
Inlet Ambient Temperature: 17C/62F


                       Press any key to view Option ROM messages

Initializing Intel(R) Boot Agent GE v1.3.32
PXE 2.1 Build 086 (WfM 2.0)

SATA Option ROM ver 2.00.B12
Copyright 1982, 2008. Hewlett-Packard Development Company, L.P.
  Port1: (Hard Disk) GJ0250EAGSQ
Drive Write Cache Disabled
Integrated Lights-Out 2 Standard Blade Edition
iLO 2 v2.23 Nov 05 2013 10.1.227.3


Mellanox ConnectX FlexBoot v3.3.500
iPXE (http://ipxe.org) 03:00.0 6000 PCI3.00 PnP PMM+00A0E800+00A29C00
 Press "F9" key for ROM-Based Setup Utility
 Press "F10" key for System Maintenance Menu
 Press "F11" key for Default Boot Override Options
 Press "F12" key for Network Boot
 For access via BIOS Serial Console
 Press "ESC+9" for ROM-Based Setup Utility
 Press "ESC+0" for System Maintenance Menu
 Press "ESC+!" for Default Boot Override Options
 Press "ESC+@" for Network Boot
ROM-Based Setup Utility, Version 3.00
Copyright 1982, 2011 Hewlett-Packard Development Company, L.P.
```

At this point, since you cannot directly press `F9` in the virtual serial port, press `Esc` then `9`. If you pressed this at the correct time, you should have entered the ROM-Based Setup Utility (RBSU) and you should see the following:

```
Type HELP to display a list of valid commands.
HELP [<command>|<TREE>] displays detailed information about a given command
or lists a given TREE of commands.

rbsu>
```

From here you can configure the BIOS.

12. Set the Virtual Serial Port by copy-pasting `SET CONFIG VIRTUAL SERIAL PORT 2`. Output:
```
Virtual Serial Port
1|COM 1; IRQ4; IO: 3F8h-3FFh
2|COM 2; IRQ3; IO: 2F8h-2FFh <=
3|COM 3; IRQ5; IO: 3E8h-3EFh
4|Disabled
```

13. Set the thermal shutdown to on: `SET CONFIG THERMAL SHUTDOWN 1`. Output:
```
Thermal Shutdown
1|Enabled <=
2|Disabled
```

14. Set BIOS Serial Console Port: `SET CONFIG BIOS SERIAL CONSOLE PORT 4`. Output:
```
BIOS Serial Console Port
1|Auto
2|Disabled
3|COM 1; IRQ4; IO: 3F8h-3FFh
4|COM 2; IRQ3; IO: 2F8h-2FFh <=
```

15. Set BIOS Serial Console Baud Rate: `SET CONFIG BIOS SERIAL CONSOLE BAUD RATE 1`. Output:
```
BIOS Serial Console Baud Rate
1|9600 <=
2|19200
3|57600
4|115200
```

16. If you are replacing one of the older blades, this step can be ignored. Set Intel(R) Hyperthreading Options: `SET CONFIG INTEL(R) HYPERTHREADING OPTIONS 2`. Output:
```
Intel(R) Hyperthreading Options
1|Enabled
2|Disabled <=
```

17. If you are replacing one of the older blades, this step can be ignored. Set Power-On Logo: `SET CONFIG POWER-ON LOGO 2`. Output:
```
Power-On Logo
1|Enabled
2|Disabled <=
```

18. Set Drive Write Cache: `SET CONFIG DRIVE WRITE CACHE 1`. Output:
```
Drive Write Cache
1|Enabled <=
2|Disabled
```

19. Set the boot order. Make sure that the output here is the same as shown below. This may take several commands. `SET IPL PXE 4`
Output:
```
1| CD-ROM
2| Floppy Drive (A:)
3| USB DriveKey (C:)
4| PCI Embedded HP NC362i Dual Port BL-c Adapter Port 1
5| Hard Drive C: (See Boot Controller Order)
6| PCI Slot 1 Other Network Controller
```

20. Set Date and Time: `SET DATE mm/dd/yy`. Output: `mm/dd/yy`.
`SET TIME hh:mm`. Output: `hh:mm`.

21. Type the following to save and exit: `EXIT`. If you do not wish to save, press `QUIT`. This will take you out of the RSBU and cause an automatic reboot (as long as you changed some settings).

To see an example of the output from a normal (new-style) node booting up, [click here](Node_Startup.txt "Node Startup"). 

Nodes Currently Down and Reasons
==============================

Blade | Status | Notes
--- | --- | ---
pod1a2 | down | Unknown
pod1a6 | down | Unknown
pod1b8 | down,offline | ILO
pod2a8 | down,offline | HDA
pod2b8 | down,offline | HDA
pod3b11 | down,offline | Investigate
pod4a2 | offline | Down due to partner node problem
pod4a3 | offline | MB
pod4a4 | offline | Down due to partner node problem
pod4a5 | offline | Power
pod4a6 | offline | Down due to partner node problem
pod4a7 | offline | Down due to partner node problem
pod4a11 | offline | Down due to partner node problem
pod4a13 | offline | Power
pod4b2 | offline | Power
pod4b3 | down,offline | Power
pod4b4 | offline | Power
pod4b5 | offline | Power
pod4b6 | down,offline | Power
pod4b7 | offline | Power
pod4b11 | offline | Power
pod4b12 | offline | ILO
pod4b13 | down,offline | Power
pod5a2 | down | Unknown
pod5a15 | offline | Down due to partner node problem
pod5b3 | offline | ILO
pod5b7 | down,offline | ILO
pod5b15 | down,offline | REPLACE MB
pod6a9 | offline | Down due to partner node problem
pod6a15 | offline | Down due to partner node problem
pod6b9 | down,offline | REPLACE MB
pod6b11 | down | Unknown
pod6b14 | down | Unknown
pod6b15 | down,offline | HDA
pod6b16 | down | seems_ok
pod7a6 | down | Unknown
pod7a12 | down | Unknown
pod7b6 | down | Unknown
pod8a7 | offline | Down due to partner node problem
pod8a9 | offline | Down due to partner node problem
pod8a13 | offline | Down due to partner node problem
pod8b7 | down,offline | REPLACE MB
pod8b9 | down,offline | REPLACE MB
pod8b13 | offline | MBA_power
pod9a1 | down,offline | HDA
pod9b1 | offline | Down due to partner node problem
pod9b11 | down,offline | ILO
pod10a7 | offline | IB-hda-rebuild
pod10a8 | offline | Down due to partner node problem
pod10a9 | offline | Down due to partner node problem
pod10a11 | offline | Down due to partner node problem
pod10a13 | offline | Down due to partner node problem
pod10b8 | down,offline | REPLACE MB
pod10b9 | offline | power_RB_REPLACE MB
pod10b11 | down,offline | HDA_tmp
pod10b13 | down,offline | HDA
pod11a6 | down | Unknown
pod11a11 | offline | Down due to partner node problem
pod11b1 | down | Unknown
pod11b11 | down,offline | Power_issue_MB
pod11b15 | offline | ILO_?
pod12a3 | down,offline | ILO_?
pod12a10 | down,offline | ILO_?
pod12a12 | down | Unknown
pod12b6 | down,offline | MB_RB
pod12b9 | down | Unknown
pod12b13 | down | Unknown
pod13b1 | down | Unknown
pod13b6 | down | Unknown
pod13b7 | down | Unknown
pod13b10 | down | Unknown
pod14a9 | down,offline | REPLACE MB
pod14b9 | offline | Down due to partner node problem
pod16a2 | down | Unknown
pod16a3 | offline | Down due to partner node problem
pod16a5 | offline | Down due to partner node problem
pod16a6 | offline | Down due to partner node problem
pod16a9 | offline | Down due to partner node problem
pod16a13 | offline | Down due to partner node problem
pod16b1 | down,offline | RETIRED_no_CPU_no_MLX
pod16b2 | down,offline | RETIRED
pod16b3 | down,offline | RB_REPLACE MB
pod16b5 | down,offline | Power_issue_MB
pod16b6 | down,offline | Investigate
pod16b9 | down,offline | REPLACE MB
pod16b13 | down,offline | REPLACE CPU2
pod17a8 | offline | Down due to partner node problem
pod17a12 | down | Unknown
pod17a16 | down | Unknown
pod17b1 | down | Unknown
pod17b2 | down | Unknown
pod17b5 | down | Unknown
pod17b8 | down,offline | RB_ILO_MB_Power_July1018. Likely a motherboard issue. Will not power on at all.
pod17b15 | down | Unknown
pod18a11 | down | Unknown
pod18a14 | offline | Down due to partner node problem
pod18b3 | down | Unknown
pod18b8 | down | Unknown
pod18b11 | down | Unknown
pod18b14 | down,offline | power_RB_REPLACE MB
pod18b15 | down | Unknown
pod20b2 | down,offline | ILO_settings
pod21a2 | down,offline | RB_REPLACE MB ILO-Error
pod21a8 | down,offline | Down due to partner node problem
pod21a10 | down,offline | Power_MT
pod21a13 | down,offline | Down due to partner node problem
pod21b2 | down,offline | reseat-ILO-Error
pod21b8 | down,offline | RB_REPLACE MB
pod21b10 | down,offline | Power_MT
pod21b13 | down,offline | MB_RB
pod22a1 | offline | Down due to partner node problem
pod22a10 | down,offline | Power_MT
pod22b1 | down,offline | Power_MT
pod22b10 | offline,job-exclusive | Down due to partner node problem
pod23a5 | down,offline | Down due to partner node problem
pod23a11 | down,offline | won't power on
pod23a16 | down,offline | Down due to partner node problem
pod23b5 | down,offline | Power_issue_MB
pod23b11 | down,offline | Down due to partner node problem
pod23b16 | down,offline | Power_Oct_2018
pod24a9 | down,offline | Down due to partner node problem
pod24a12 | down,offline | Down due to partner node problem
pod24b9 | down,offline | RB_REPLACE MB check
pod24b12 | down,offline | REPLACE MB MLX
pod25a3 | down,offline | HDA_MT
pod25b3 | down,offline | Down due to partner node problem
pod26a7 | down,offline | Down due to partner node problem
pod26b7 | down,offline | Looks like a memory or motherboard issue. Upon boot, the node complains about Invalid memory config.


<a href="#top">Back to top</a>
