# The following is an example of a proper boot sequence. Copied from pod27b3 after a fresh install and reconfiguration.
```
</>hpiLO-> Virtual Serial Port active: IO=0x02F8 INT=3
                            24 GB Installed

ProLiant System BIOS - I26 (01/30/2011)
Copyright 1982, 2011 Hewlett-Packard Development Company, L.P.


2 Processor(s) detected, 12 total cores enabled, Hyperthreading is disabled
Proc 1: Intel(R) Xeon(R) CPU X5650 @ 2.67GHz
Proc 2: Intel(R) Xeon(R) CPU X5650 @ 2.67GHz
QPI Speed: 6.4 GT/s
HP Power Profile Mode: Balanced Power and Performance
Power Regulator Mode: Dynamic Power Savings

Advanced Memory Protection Mode: Advanced ECC Support
Redundant ROM Detected - This system contains a valid backup system ROM.
Inlet Ambient Temperature: 16C/60F



Initializing Intel(R) Boot Agent GE v1.3.32
PXE 2.1 Build 086 (WfM 2.0)

SATA Option ROM ver 2.00.B12
Copyright 1982, 2008. Hewlett-Packard Development Company, L.P.
  Port1: (Hard Disk) GJ0250EAGSQ                                  <F9 = Setup>
Drive Write Cache Enabled
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
Probing EDD (edd=off to disable)... ok                                                                                                                                                                         Initializing cgroup subsys cpuset                                                                                                                                                                              Initializing cgroup subsys cpu                                                                                                                                                                                 Linux version 2.6.32-358.18.1.el6.x86_64 (mockbuild@c6b10.bsys.dev.centos.org) (g                                                                                                                              cc version 4.4.7 20120313 (Red Hat 4.4.7-3) (GCC) ) #1 SMP Wed Aug 28 17:19:38 UT                                                                                                                              C 2013                                                                                                                                                                                                         Command line: ro root=/dev/sda1 rd_NO_LUKS rd_NO_LVM LANG=en_US.UTF-8 rd_NO_MD SY                                                                                                                              SFONT=latarcyrheb-sun16 console=ttyS1 crashkernel=auto  KEYBOARDTYPE=pc KEYTABLE=                                                                                                                              us transparent_hugepage=never rd_NO_DM                                                                                                                                                                         KERNEL supported cpus:                                                                                                                                                                                           Intel GenuineIntel                                                                                                                                                                                             AMD AuthenticAMD                                                                                                                                                                                               Centaur CentaurHauls                                                                                                                                                                                         BIOS-provided physical RAM map:                                                                                                                                                                                 BIOS-e820: 0000000000000000 - 0000000000097c00 (usable)                                                                                                                                                        BIOS-e820: 0000000000097c00 - 00000000000a0000 (reserved)                                                                                                                                                      BIOS-e820: 00000000000f0000 - 0000000000100000 (reserved)                                                                                                                                                      BIOS-e820: 0000000000100000 - 00000000e762f000 (usable)                                                                                                                                                        BIOS-e820: 00000000e762f000 - 00000000e763c000 (ACPI data)                                                                                                                                                     BIOS-e820: 00000000e763c000 - 00000000e763d000 (usable)                                                                                                                                                        BIOS-e820: 00000000e763d000 - 00000000ec000000 (reserved)                                                                                                                                                      BIOS-e820: 00000000fec00000 - 00000000fee10000 (reserved)                                                                                                                                                      BIOS-e820: 00000000ff800000 - 0000000100000000 (reserved)                                                                                                                                                      BIOS-e820: 0000000100000000 - 0000000617fff000 (usable)                                                                                                                                                       DMI 2.7 present.
SMBIOS version 2.7 @ 0xF4F40
last_pfn = 0x617fff max_arch_pfn = 0x400000000
x86 PAT enabled: cpu 0, old 0x7040600070406, new 0x7010600070106
last_pfn = 0xe763d max_arch_pfn = 0x400000000
Using GB pages for direct mapping
init_memory_mapping: 0000000000000000-00000000e763d000
init_memory_mapping: 0000000100000000-0000000617fff000
RAMDISK: 36dd5000 - 37fef842
ACPI: RSDP 00000000000f4f00 00024 (v02 HP    )
ACPI: XSDT 00000000e7630080 000AC (v01 HP     ProLiant 00000002   ▒? 0000162E)
ACPI: FACP 00000000e7630180 000F4 (v03 HP     ProLiant 00000002   ▒? 0000162E)
ACPI Warning: Invalid length for Pm1aControlBlock: 32, using default 16 (20090903                                                                                                                              /tbfadt-607)
ACPI Warning: Invalid length for Pm2ControlBlock: 32, using default 8 (20090903/t                                                                                                                              bfadt-607)
ACPI: DSDT 00000000e7630280 0216E (v01 HP         DSDT 00000001 INTL 20030228)
ACPI: FACS 00000000e762f100 00040
ACPI: SPCR 00000000e762f140 00050 (v01 HP     SPCRRBSU 00000001   ▒? 0000162E)
ACPI: MCFG 00000000e762f1c0 0003C (v01 HP     ProLiant 00000001      00000000)
ACPI: HPET 00000000e762f200 00038 (v01 HP     ProLiant 00000002   ▒? 0000162E)
ACPI: FFFF 00000000e762f240 00064 (v02 HP     ProLiant 00000002   ▒? 0000162E)
ACPI: SPMI 00000000e762f2c0 00040 (v05 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: ERST 00000000e762f300 001D0 (v01 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: APIC 00000000e762f500 0015E (v01 HP     ProLiant 00000002      00000000)
ACPI: SRAT 00000000e762f680 00570 (v01 HP     Proliant 00000001   ▒? 0000162E)
ACPI: FFFF 00000000e762fc00 00176 (v01 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: BERT 00000000e762fd80 00030 (v01 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: HEST 00000000e762fdc0 000BC (v01 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: DMAR 00000000e762fe80 00106 (v01 HP     ProLiant 00000001   ▒? 0000162E)
ACPI: SSDT 00000000e7632400 00125 (v03     HP  CRSPCI0 00000002   HP 00000001)
ACPI: SSDT 00000000e7632540 003BB (v01     HP      pcc 00000001 INTL 20090625)
ACPI: SSDT 00000000e7632900 00377 (v01     HP     pmab 00000001 INTL 20090625)
ACPI: SSDT 00000000e7632c80 02094 (v01  INTEL PPM RCM  00000001 INTL 20061109)
Setting APIC routing to flat.
SRAT: PXM 0 -> APIC 0 -> Node 0
SRAT: PXM 0 -> APIC 2 -> Node 0
SRAT: PXM 0 -> APIC 4 -> Node 0
SRAT: PXM 0 -> APIC 16 -> Node 0
SRAT: PXM 0 -> APIC 18 -> Node 0
SRAT: PXM 0 -> APIC 20 -> Node 0
SRAT: PXM 1 -> APIC 32 -> Node 1
SRAT: PXM 1 -> APIC 34 -> Node 1
SRAT: PXM 1 -> APIC 36 -> Node 1
SRAT: PXM 1 -> APIC 48 -> Node 1
SRAT: PXM 1 -> APIC 50 -> Node 1
SRAT: PXM 1 -> APIC 52 -> Node 1
SRAT: Node 0 PXM 0 0-e8000000
SRAT: Node 0 PXM 0 100000000-318000000
SRAT: Node 1 PXM 1 318000000-618000000
Bootmem setup node 0 0000000000000000-0000000318000000
  NODE_DATA [000000000000c1c0 - 00000000000401bf]
  bootmap [0000000000100000 -  0000000000162fff] pages 63
(9 early reservations) ==> bootmem [0000000000 - 0318000000]
  #0 [0000000000 - 0000001000]   BIOS data page ==> [0000000000 - 0000001000]
  #1 [0000006000 - 0000008000]       TRAMPOLINE ==> [0000006000 - 0000008000]
  #2 [0001000000 - 000201b0a4]    TEXT DATA BSS ==> [0001000000 - 000201b0a4]
  #3 [0036dd5000 - 0037fef842]          RAMDISK ==> [0036dd5000 - 0037fef842]
  #4 [0000097c00 - 0000100000]    BIOS reserved ==> [0000097c00 - 0000100000]
  #5 [000201c000 - 000201c14c]              BRK ==> [000201c000 - 000201c14c]
  #6 [0000008000 - 000000a000]          PGTABLE ==> [0000008000 - 000000a000]
  #7 [000000a000 - 000000c000]          PGTABLE ==> [000000a000 - 000000c000]
  #8 [000000c000 - 000000c1c0]       MEMNODEMAP ==> [000000c000 - 000000c1c0]
Bootmem setup node 1 0000000318000000-0000000617fff000
  NODE_DATA [0000000318000040 - 000000031803403f]
  bootmap [0000000318035000 -  0000000318094fff] pages 60
(9 early reservations) ==> bootmem [0318000000 - 0617fff000]
  #0 [0000000000 - 0000001000]   BIOS data page
  #1 [0000006000 - 0000008000]       TRAMPOLINE
  #2 [0001000000 - 000201b0a4]    TEXT DATA BSS
  #3 [0036dd5000 - 0037fef842]          RAMDISK
  #4 [0000097c00 - 0000100000]    BIOS reserved
  #5 [000201c000 - 000201c14c]              BRK
  #6 [0000008000 - 000000a000]          PGTABLE
  #7 [000000a000 - 000000c000]          PGTABLE
  #8 [000000c000 - 000000c1c0]       MEMNODEMAP
found SMP MP-table at [ffff8800000f4f80] f4f80
Reserving 130MB of memory at 48MB for crashkernel (System RAM: 24959MB)
[ffffea000ad40000-ffffea000adfffff] potential offnode page_structs
Zone PFN ranges:
  DMA      0x00000001 -> 0x00001000
  DMA32    0x00001000 -> 0x00100000
  Normal   0x00100000 -> 0x00617fff
Movable zone start PFN for each node
early_node_map[5] active PFN ranges
    0: 0x00000001 -> 0x00000097
    0: 0x00000100 -> 0x000e762f
    0: 0x000e763c -> 0x000e763d
    0: 0x00100000 -> 0x00318000
    1: 0x00318000 -> 0x00617fff
ACPI: PM-Timer IO Port: 0x908
Setting APIC routing to flat.
ACPI: LAPIC (acpi_id[0x10] lapic_id[0x20] enabled)
ACPI: LAPIC (acpi_id[0x00] lapic_id[0x10] enabled)
ACPI: LAPIC (acpi_id[0x18] lapic_id[0x30] enabled)
ACPI: LAPIC (acpi_id[0x08] lapic_id[0x00] enabled)
ACPI: LAPIC (acpi_id[0x14] lapic_id[0x24] enabled)
ACPI: LAPIC (acpi_id[0x04] lapic_id[0x14] enabled)
ACPI: LAPIC (acpi_id[0x1c] lapic_id[0x34] enabled)
ACPI: LAPIC (acpi_id[0x0c] lapic_id[0x04] enabled)
ACPI: LAPIC (acpi_id[0x12] lapic_id[0x22] enabled)
ACPI: LAPIC (acpi_id[0x02] lapic_id[0x12] enabled)
ACPI: LAPIC (acpi_id[0x1a] lapic_id[0x32] enabled)
ACPI: LAPIC (acpi_id[0x0a] lapic_id[0x02] enabled)
ACPI: LAPIC (acpi_id[0x16] lapic_id[0x26] disabled)
ACPI: LAPIC (acpi_id[0x06] lapic_id[0x16] disabled)
ACPI: LAPIC (acpi_id[0x1e] lapic_id[0x36] disabled)
ACPI: LAPIC (acpi_id[0x0e] lapic_id[0x06] disabled)
ACPI: LAPIC (acpi_id[0x11] lapic_id[0x21] disabled)
ACPI: LAPIC (acpi_id[0x01] lapic_id[0x11] disabled)
ACPI: LAPIC (acpi_id[0x19] lapic_id[0x31] disabled)
ACPI: LAPIC (acpi_id[0x09] lapic_id[0x01] disabled)
ACPI: LAPIC (acpi_id[0x15] lapic_id[0x25] disabled)
ACPI: LAPIC (acpi_id[0x05] lapic_id[0x15] disabled)
ACPI: LAPIC (acpi_id[0x1d] lapic_id[0x35] disabled)
ACPI: LAPIC (acpi_id[0x0d] lapic_id[0x05] disabled)
ACPI: LAPIC (acpi_id[0x13] lapic_id[0x23] disabled)
ACPI: LAPIC (acpi_id[0x03] lapic_id[0x13] disabled)
ACPI: LAPIC (acpi_id[0x1b] lapic_id[0x33] disabled)
ACPI: LAPIC (acpi_id[0x0b] lapic_id[0x03] disabled)
ACPI: LAPIC (acpi_id[0x17] lapic_id[0x27] disabled)
ACPI: LAPIC (acpi_id[0x07] lapic_id[0x17] disabled)
ACPI: LAPIC (acpi_id[0x1f] lapic_id[0x37] disabled)
ACPI: LAPIC (acpi_id[0x0f] lapic_id[0x07] disabled)
ACPI: LAPIC_NMI (acpi_id[0xff] dfl dfl lint[0x1])
ACPI: IOAPIC (id[0x08] address[0xfec00000] gsi_base[0])
IOAPIC[0]: apic_id 8, version 32, address 0xfec00000, GSI 0-23
ACPI: IOAPIC (id[0x00] address[0xfec80000] gsi_base[24])
IOAPIC[1]: apic_id 0, version 32, address 0xfec80000, GSI 24-47
ACPI: INT_SRC_OVR (bus 0 bus_irq 0 global_irq 2 high edge)
ACPI: INT_SRC_OVR (bus 0 bus_irq 9 global_irq 9 high level)
Using ACPI (MADT) for SMP configuration information
ACPI: HPET id: 0x8086a201 base: 0xfed00000
SMP: Allowing 32 CPUs, 20 hotplug CPUs
PM: Registered nosave memory: 0000000000097000 - 0000000000098000
PM: Registered nosave memory: 0000000000098000 - 00000000000a0000
PM: Registered nosave memory: 00000000000a0000 - 00000000000f0000
PM: Registered nosave memory: 00000000000f0000 - 0000000000100000
PM: Registered nosave memory: 00000000e762f000 - 00000000e763c000
PM: Registered nosave memory: 00000000e763d000 - 00000000ec000000
PM: Registered nosave memory: 00000000ec000000 - 00000000fec00000
PM: Registered nosave memory: 00000000fec00000 - 00000000fee10000
PM: Registered nosave memory: 00000000fee10000 - 00000000ff800000
PM: Registered nosave memory: 00000000ff800000 - 0000000100000000
Allocating PCI resources starting at ec000000 (gap: ec000000:12c00000)
Booting paravirtualized kernel on bare hardware
NR_CPUS:4096 nr_cpumask_bits:32 nr_cpu_ids:32 nr_node_ids:2
PERCPU: Embedded 31 pages/cpu @ffff880028200000 s94552 r8192 d24232 u131072
pcpu-alloc: s94552 r8192 d24232 u131072 alloc=1*2097152
pcpu-alloc: [0] 00 02 04 06 08 10 13 15 17 19 21 23 25 27 29 31
pcpu-alloc: [1] 01 03 05 07 09 11 12 14 16 18 20 22 24 26 28 30
Built 2 zonelists in Zone order, mobility grouping on.  Total pages: 6201366
Policy zone: Normal
Kernel command line: ro root=/dev/sda1 rd_NO_LUKS rd_NO_LVM LANG=en_US.UTF-8 rd_N                                                                                                                              O_MD SYSFONT=latarcyrheb-sun16 console=ttyS1 crashkernel=130M@0M  KEYBOARDTYPE=pc                                                                                                                               KEYTABLE=us transparent_hugepage=never rd_NO_DM
PID hash table entries: 4096 (order: 3, 32768 bytes)
Checking aperture...
No AGP bridge found
PCI-DMA: Using software bounce buffering for IO (SWIOTLB)
Placing 64MB software IO TLB between ffff880020000000 - ffff880024000000
software IO TLB at phys 0x20000000 - 0x24000000
Memory: 24570196k/25559036k available (5222k kernel code, 403688k absent, 585152k                                                                                                                               reserved, 7119k data, 1264k init)
Hierarchical RCU implementation.
NR_IRQS:33024 nr_irqs:1072
Extended CMOS year: 2000
Console: colour VGA+ 80x25
console [ttyS1] enabled
allocated 100663296 bytes of page_cgroup
please try 'cgroup_disable=memory' option if you don't want memory cgroups
Fast TSC calibration using PIT
Detected 2665.906 MHz processor.
Calibrating delay loop (skipped), value calculated using timer frequency.. 5331.8                                                                                                                              1 BogoMIPS (lpj=2665906)
pid_max: default: 32768 minimum: 301
Security Framework initialized
SELinux:  Initializing.
Dentry cache hash table entries: 4194304 (order: 13, 33554432 bytes)
Inode-cache hash table entries: 2097152 (order: 12, 16777216 bytes)
Mount-cache hash table entries: 256
Initializing cgroup subsys ns
Initializing cgroup subsys cpuacct
Initializing cgroup subsys memory
Initializing cgroup subsys devices
Initializing cgroup subsys freezer
Initializing cgroup subsys net_cls
Initializing cgroup subsys blkio
Initializing cgroup subsys perf_event
Initializing cgroup subsys net_prio
CPU: Physical Processor ID: 1
CPU: Processor Core ID: 0
mce: CPU supports 9 MCE banks
CPU0: Thermal monitoring enabled (TM1)
using mwait in idle threads.
ACPI: Core revision 20090903
ftrace: converting mcount calls to 0f 1f 44 00 00
ftrace: allocating 21439 entries in 85 pages
dmar: Host address width 39
dmar: DRHD base: 0x000000efffe000 flags: 0x1
dmar: IOMMU 0: reg_base_addr efffe000 ver 1:0 cap c90780106f0462 ecap f0207e
dmar: RMRR base: 0x000000e77fc000 end: 0x000000e77fdfff
dmar: RMRR base: 0x000000e77f5000 end: 0x000000e77fafff
dmar: ATSR flags: 0x0
IOAPIC id 8 under DRHD base 0xefffe000
IOAPIC id 0 under DRHD base 0xefffe000
Enabled IRQ remapping in xapic mode
APIC routing finalized to physical flat.
..TIMER: vector=0x30 apic1=0 pin1=2 apic2=-1 pin2=-1
CPU0: Intel(R) Xeon(R) CPU           X5650  @ 2.67GHz stepping 02
Performance Events: PEBS fmt1+, Westmere events, Broken BIOS detected, complain t                                                                                                                              o your hardware vendor.
[Firmware Bug]: the BIOS has corrupted hw-PMU resources (MSR 38d is 330)
Intel PMU driver.
CPUID marked event: 'bus cycles' unavailable
... version:                3
... bit width:              48
... generic registers:      4
... value mask:             0000ffffffffffff
... max period:             000000007fffffff
... fixed-purpose events:   3
... event mask:             000000070000000f
NMI watchdog enabled, takes one hw-pmu counter.
Booting Node   0, Processors  #1 Ok.
Booting Node   1, Processors  #2 Ok.
Booting Node   0, Processors  #3 Ok.
Booting Node   1, Processors  #4 Ok.
Booting Node   0, Processors  #5 Ok.
Booting Node   1, Processors  #6 Ok.
Booting Node   0, Processors  #7 Ok.
Booting Node   1, Processors  #8 Ok.
Booting Node   0, Processors  #9 Ok.
Booting Node   1, Processors  #10 Ok.
Booting Node   0, Processors  #11
Brought up 12 CPUs
Total of 12 processors activated (63978.87 BogoMIPS).
devtmpfs: initialized
regulator: core version 0.5
NET: Registered protocol family 16
ACPI FADT declares the system doesn't support PCIe ASPM, so disable it
ACPI: bus type pci registered
PCI: MCFG configuration 0: base e8000000 segment 0 buses 0 - 63
PCI: MCFG area at e8000000 reserved in E820
PCI: Using MMCONFIG at e8000000 - ebffffff
PCI: Using configuration type 1 for base access
bio: create slab <bio-0> at 0
ACPI: Interpreter enabled
ACPI: (supports S0 S4 S5)
ACPI: Using IOAPIC for interrupt routing
ACPI: No dock devices found.
HEST: Table parsing has been initialized.
PCI: Using host bridge windows from ACPI; if necessary, use "pci=nocrs" and repor                                                                                                                              t a bug
ACPI: PCI Root Bridge [PCI0] (domain 0000 [bus 00-0a])
pci_root PNP0A03:00: host bridge window [mem 0xef000000-0xfbffffff]
pci_root PNP0A03:00: host bridge window [io  0x1000-0x4fff]
pci_root PNP0A03:00: host bridge window [io  0x0000-0x03af]
pci_root PNP0A03:00: host bridge window [io  0x03e0-0x0cf7]
pci_root PNP0A03:00: host bridge window [io  0x0d00-0x0fff]
pci_root PNP0A03:00: host bridge window [mem 0xfed00000-0xfed03fff]
pci_root PNP0A03:00: host bridge window [mem 0xfed00000-0xfed44fff]
pci_root PNP0A03:00: host bridge window [io  0x03b0-0x03bb]
pci_root PNP0A03:00: host bridge window [io  0x03c0-0x03df]
pci_root PNP0A03:00: host bridge window [mem 0x000a0000-0x000bffff]
pci_root PNP0A03:00: host bridge window expanded to [mem 0xfed00000-0xfed44fff];                                                                                                                               [mem 0xfed00000-0xfed44fff] ignored
[Hardware Error]: This system BIOS has enabled interrupt remapping
on a chipset that contains an errata making that
feature unstable.  Please reboot with nointremap
added to the kernel command line and contact
your BIOS vendor for an update
pci 0000:00:00.0: PME# supported from D0 D3hot D3cold
pci 0000:00:00.0: PME# disabled
pci 0000:00:01.0: PME# supported from D0 D3hot D3cold
pci 0000:00:01.0: PME# disabled
pci 0000:00:02.0: PME# supported from D0 D3hot D3cold
pci 0000:00:02.0: PME# disabled
pci 0000:00:03.0: PME# supported from D0 D3hot D3cold
pci 0000:00:03.0: PME# disabled
pci 0000:00:07.0: PME# supported from D0 D3hot D3cold
pci 0000:00:07.0: PME# disabled
pci 0000:00:08.0: PME# supported from D0 D3hot D3cold
pci 0000:00:08.0: PME# disabled
pci 0000:00:09.0: PME# supported from D0 D3hot D3cold
pci 0000:00:09.0: PME# disabled
pci 0000:00:0a.0: PME# supported from D0 D3hot D3cold
pci 0000:00:0a.0: PME# disabled
pci 0000:00:1d.7: PME# supported from D0 D3hot D3cold
pci 0000:00:1d.7: PME# disabled
pci 0000:00:01.0: PCI bridge to [bus 06-06]
pci 0000:00:02.0: PCI bridge to [bus 07-07]
pci 0000:02:00.0: PME# supported from D0 D3hot D3cold
pci 0000:02:00.0: PME# disabled
pci 0000:02:00.1: PME# supported from D0 D3hot D3cold
pci 0000:02:00.1: PME# disabled
pci 0000:00:03.0: PCI bridge to [bus 02-02]
pci 0000:00:07.0: PCI bridge to [bus 03-05]
pci 0000:00:08.0: PCI bridge to [bus 08-08]
pci 0000:00:09.0: PCI bridge to [bus 09-09]
pci 0000:00:0a.0: PCI bridge to [bus 0a-0a]
pci 0000:01:04.0: PME# supported from D0 D3hot D3cold
pci 0000:01:04.0: PME# disabled
pci 0000:01:04.2: PME# supported from D0 D3hot D3cold
pci 0000:01:04.2: PME# disabled
pci 0000:01:04.4: PME# supported from D0 D3hot D3cold
pci 0000:01:04.4: PME# disabled
pci 0000:01:04.6: PME# supported from D0 D3hot D3cold
pci 0000:01:04.6: PME# disabled
pci 0000:00:1e.0: PCI bridge to [bus 01-01] (subtractive decode)
 pci0000:00: Requesting ACPI _OSC control (0x1d)
Unable to assume _OSC PCIe control. Disabling ASPM
ACPI: PCI Interrupt Link [LNKA] (IRQs 5 7 *10 11)
ACPI: PCI Interrupt Link [LNKB] (IRQs 5 7 *10 11)
ACPI: PCI Interrupt Link [LNKC] (IRQs 5 7 10 11) *0, disabled.
ACPI: PCI Interrupt Link [LNKD] (IRQs 5 7 10 11) *0, disabled.
ACPI: PCI Interrupt Link [LNKE] (IRQs 5 7 10 *11)
ACPI: PCI Interrupt Link [LNKF] (IRQs 5 *7 10 11)
ACPI: PCI Interrupt Link [LNKG] (IRQs *5 7 10 11)
ACPI: PCI Interrupt Link [LNKH] (IRQs 5 7 10 11) *4
vgaarb: device added: PCI:0000:01:03.0,decodes=io+mem,owns=io+mem,locks=none
vgaarb: loaded
vgaarb: bridge control possible 0000:01:03.0
SCSI subsystem initialized
usbcore: registered new interface driver usbfs
usbcore: registered new interface driver hub
usbcore: registered new device driver usb
PCI: Using ACPI for IRQ routing
NetLabel: Initializing
NetLabel:  domain hash size = 128
NetLabel:  protocols = UNLABELED CIPSOv4
NetLabel:  unlabeled traffic allowed by default
HPET: 4 timers in total, 0 timers will be used for per-cpu timer
hpet0: at MMIO 0xfed00000, IRQs 2, 8, 0, 0
hpet0: 4 comparators, 64-bit 14.318180 MHz counter
Switching to clocksource hpet
pnp: PnP ACPI init
ACPI: bus type pnp registered
pnp: PnP ACPI: found 10 devices
ACPI: ACPI bus type pnp unregistered
system 00:01: [io  0x0408-0x040f] has been reserved
system 00:01: [io  0x04d0-0x04d1] has been reserved
system 00:01: [io  0x0700-0x071f] has been reserved
system 00:01: [io  0x0880-0x08ff] has been reserved
system 00:01: [io  0x0900-0x097f] has been reserved
system 00:01: [io  0x0c80-0x0c83] has been reserved
system 00:01: [io  0x0cd4-0x0cd7] has been reserved
system 00:01: [io  0x0f50-0x0f58] has been reserved
system 00:01: [io  0x0ca0-0x0ca1] has been reserved
system 00:01: [io  0x0ca4-0x0ca5] has been reserved
system 00:01: [io  0x02f8-0x02ff] has been reserved
system 00:01: [mem 0xe8000000-0xebffffff] has been reserved
system 00:01: [mem 0xfe000000-0xfebfffff] has been reserved
system 00:01: [mem 0xefffe000-0xefffffff] could not be reserved
pci 0000:00:03.0: BAR 15: assigned [mem 0xef000000-0xef0fffff pref]
pci 0000:00:01.0: PCI bridge to [bus 06-06]
pci 0000:00:01.0: PCI bridge to [bus 06-06]
pci 0000:00:01.0:   bridge window [io  disabled]
pci 0000:00:01.0:   bridge window [mem disabled]
pci 0000:00:01.0:   bridge window [mem pref disabled]
pci 0000:00:02.0: PCI bridge to [bus 07-07]
pci 0000:00:02.0: PCI bridge to [bus 07-07]
pci 0000:00:02.0:   bridge window [io  disabled]
pci 0000:00:02.0:   bridge window [mem disabled]
pci 0000:00:02.0:   bridge window [mem pref disabled]
pci 0000:02:00.0: BAR 6: assigned [mem 0xef000000-0xef01ffff pref]
pci 0000:02:00.1: BAR 6: assigned [mem 0xef020000-0xef03ffff pref]
pci 0000:02:00.0: BAR 7: assigned [mem 0xfbe00000-0xfbe1ffff 64bit]
pci 0000:02:00.0: BAR 7: set to [mem 0xfbe00000-0xfbe1ffff 64bit] (PCI address [0                                                                                                                              xfbe00000-0xfbe1ffff]
pci 0000:02:00.0: BAR 10: assigned [mem 0xfbe20000-0xfbe3ffff 64bit]
pci 0000:02:00.0: BAR 10: set to [mem 0xfbe20000-0xfbe3ffff 64bit] (PCI address [                                                                                                                              0xfbe20000-0xfbe3ffff]
pci 0000:02:00.1: BAR 7: can't assign mem (size 0x20000)
pci 0000:02:00.1: BAR 10: can't assign mem (size 0x20000)
pci 0000:00:03.0: PCI bridge to [bus 02-02]
pci 0000:00:03.0: PCI bridge to [bus 02-02]
pci 0000:00:03.0:   bridge window [io  0x4000-0x4fff]
pci 0000:00:03.0:   bridge window [mem 0xfbe00000-0xfbefffff]
pci 0000:00:03.0:   bridge window [mem 0xef000000-0xef0fffff pref]
pci 0000:03:00.0: BAR 6: can't assign mem pref (size 0x100000)
pci 0000:00:07.0: PCI bridge to [bus 03-05]
pci 0000:00:07.0: PCI bridge to [bus 03-05]
pci 0000:00:07.0:   bridge window [io  disabled]
pci 0000:00:07.0:   bridge window [mem 0xfbf00000-0xfbffffff]
pci 0000:00:07.0:   bridge window [mem 0xf8000000-0xf9ffffff 64bit pref]
pci 0000:00:08.0: PCI bridge to [bus 08-08]
pci 0000:00:08.0: PCI bridge to [bus 08-08]
pci 0000:00:08.0:   bridge window [io  disabled]
pci 0000:00:08.0:   bridge window [mem disabled]
pci 0000:00:08.0:   bridge window [mem pref disabled]
pci 0000:00:09.0: PCI bridge to [bus 09-09]
pci 0000:00:09.0: PCI bridge to [bus 09-09]
pci 0000:00:09.0:   bridge window [io  disabled]
pci 0000:00:09.0:   bridge window [mem disabled]
pci 0000:00:09.0:   bridge window [mem pref disabled]
pci 0000:00:0a.0: PCI bridge to [bus 0a-0a]
pci 0000:00:0a.0: PCI bridge to [bus 0a-0a]
pci 0000:00:0a.0:   bridge window [io  disabled]
pci 0000:00:0a.0:   bridge window [mem disabled]
pci 0000:00:0a.0:   bridge window [mem pref disabled]
pci 0000:01:03.0: BAR 6: assigned [mem 0xfbc00000-0xfbc1ffff pref]
pci 0000:01:04.2: BAR 6: assigned [mem 0xfbc20000-0xfbc2ffff pref]
pci 0000:00:1e.0: PCI bridge to [bus 01-01]
pci 0000:00:1e.0: PCI bridge to [bus 01-01]
pci 0000:00:1e.0:   bridge window [io  0x2000-0x3fff]
pci 0000:00:1e.0:   bridge window [mem 0xfbc00000-0xfbdfffff]
pci 0000:00:1e.0:   bridge window [mem 0xf0000000-0xf7ffffff 64bit pref]
NET: Registered protocol family 2
IP route cache hash table entries: 524288 (order: 10, 4194304 bytes)
TCP established hash table entries: 524288 (order: 11, 8388608 bytes)
TCP bind hash table entries: 65536 (order: 8, 1048576 bytes)
TCP: Hash tables configured (established 524288 bind 65536)
TCP reno registered
NET: Registered protocol family 1
pci 0000:00:1d.0: PCI INT A -> GSI 20 (level, low) -> IRQ 20
pci 0000:00:1d.0: PCI INT A disabled
pci 0000:00:1d.1: PCI INT B -> GSI 23 (level, low) -> IRQ 23
pci 0000:00:1d.1: PCI INT B disabled
pci 0000:00:1d.2: PCI INT C -> GSI 22 (level, low) -> IRQ 22
pci 0000:00:1d.2: PCI INT C disabled
pci 0000:00:1d.3: PCI INT D -> GSI 23 (level, low) -> IRQ 23
pci 0000:00:1d.3: PCI INT D disabled
pci 0000:00:1d.7: PCI INT A -> GSI 20 (level, low) -> IRQ 20
pci 0000:00:1d.7: PCI INT A disabled
pci 0000:01:04.4: PCI INT B -> GSI 22 (level, low) -> IRQ 22
pci 0000:01:04.4: PCI INT B disabled
Trying to unpack rootfs image as initramfs...
Freeing initrd memory: 18538k freed
audit: initializing netlink socket (disabled)
type=2000 audit(1566239918.700:1): initialized
HugeTLB registered 2 MB page size, pre-allocated 0 pages
VFS: Disk quotas dquot_6.5.2
Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
msgmni has been set to 32768
alg: No test for stdrng (krng)
ksign: Installing public key data
Loading keyring
- Added public key 2B202C2FC9DD26CD
- User ID: CentOS (Kernel Module GPG key)
Block layer SCSI generic (bsg) driver version 0.4 loaded (major 251)
io scheduler noop registered
io scheduler anticipatory registered
io scheduler deadline registered
io scheduler cfq registered (default)
pci_hotplug: PCI Hot Plug PCI Core version: 0.5
pciehp: PCI Express Hot Plug Controller Driver version: 0.4
acpiphp: ACPI Hot Plug PCI Controller Driver version: 0.5
ipmi message handler version 39.2
IPMI System Interface driver.
ipmi_si: Adding ACPI-specified kcs state machine
ipmi_si: Adding SMBIOS-specified kcs state machine: duplicate interface
ipmi_si 0000:01:04.6: PCI INT A -> GSI 21 (level, low) -> IRQ 21
ipmi_si: Adding PCI-specified kcs state machine
ipmi_si: Adding ACPI-specified kcs state machine: duplicate interface
ipmi_si: Trying PCI-specified kcs state machine at mem address 0xfbcf0000, slave                                                                                                                               address 0x0, irq 21
IRQ 21/ipmi_si: IRQF_DISABLED is not guaranteed on shared IRQs
  Using irq 21
ipmi: Found new BMC (man_id: 0x00000b,  prod_id: 0x2020, dev_id: 0x11)
IPMI kcs interface initialized
input: Power Button as /devices/LNXSYSTM:00/LNXPWRBN:00/input/input0
ACPI: Power Button [PWRF]
thermal LNXTHERM:01: registered as thermal_zone0
ACPI: Thermal Zone [THM0] (8 C)
[Firmware Bug]: APEI: Invalid bit width + offset in GAR [0xe8028/64/0/2/0]
GHES: APEI firmware first mode is enabled by APEI bit and WHEA _OSC.
Non-volatile memory driver v1.3
Linux agpgart interface v0.103
crash memory driver: version 1.1
Serial: 8250/16550 driver, 4 ports, IRQ sharing enabled
▒▒serial8250: ttyS1 at I/O 0x2f8 (irq = 3) is a 16550A
brd: module loaded
loop: module loaded
input: Macintosh mouse button emulation as /devices/virtual/input/input1
Fixed MDIO Bus: probed
ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
ehci_hcd 0000:00:1d.7: PCI INT A -> GSI 20 (level, low) -> IRQ 20
ehci_hcd 0000:00:1d.7: EHCI Host Controller
ehci_hcd 0000:00:1d.7: new USB bus registered, assigned bus number 1
ehci_hcd 0000:00:1d.7: debug port 1
ehci_hcd 0000:00:1d.7: irq 20, io mem 0xfbbf0000
ehci_hcd 0000:00:1d.7: USB 2.0 started, EHCI 1.00
usb usb1: New USB device found, idVendor=1d6b, idProduct=0002
usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb1: Product: EHCI Host Controller
usb usb1: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 ehci_hcd
usb usb1: SerialNumber: 0000:00:1d.7
usb usb1: configuration #1 chosen from 1 choice
hub 1-0:1.0: USB hub found
hub 1-0:1.0: 8 ports detected
ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
uhci_hcd: USB Universal Host Controller Interface driver
uhci_hcd 0000:00:1d.0: PCI INT A -> GSI 20 (level, low) -> IRQ 20
uhci_hcd 0000:00:1d.0: UHCI Host Controller
uhci_hcd 0000:00:1d.0: new USB bus registered, assigned bus number 2
uhci_hcd 0000:00:1d.0: irq 20, io base 0x00001000
usb usb2: New USB device found, idVendor=1d6b, idProduct=0001
usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb2: Product: UHCI Host Controller
usb usb2: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 uhci_hcd
usb usb2: SerialNumber: 0000:00:1d.0
usb usb2: configuration #1 chosen from 1 choice
hub 2-0:1.0: USB hub found
hub 2-0:1.0: 2 ports detected
uhci_hcd 0000:00:1d.1: PCI INT B -> GSI 23 (level, low) -> IRQ 23
uhci_hcd 0000:00:1d.1: UHCI Host Controller
uhci_hcd 0000:00:1d.1: new USB bus registered, assigned bus number 3
uhci_hcd 0000:00:1d.1: irq 23, io base 0x00001020
usb usb3: New USB device found, idVendor=1d6b, idProduct=0001
usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb3: Product: UHCI Host Controller
usb usb3: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 uhci_hcd
usb usb3: SerialNumber: 0000:00:1d.1
usb usb3: configuration #1 chosen from 1 choice
hub 3-0:1.0: USB hub found
hub 3-0:1.0: 2 ports detected
uhci_hcd 0000:00:1d.2: PCI INT C -> GSI 22 (level, low) -> IRQ 22
uhci_hcd 0000:00:1d.2: UHCI Host Controller
uhci_hcd 0000:00:1d.2: new USB bus registered, assigned bus number 4
uhci_hcd 0000:00:1d.2: irq 22, io base 0x00001040
usb usb4: New USB device found, idVendor=1d6b, idProduct=0001
usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb4: Product: UHCI Host Controller
usb usb4: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 uhci_hcd
usb usb4: SerialNumber: 0000:00:1d.2
usb usb4: configuration #1 chosen from 1 choice
hub 4-0:1.0: USB hub found
hub 4-0:1.0: 2 ports detected
uhci_hcd 0000:00:1d.3: PCI INT D -> GSI 23 (level, low) -> IRQ 23
uhci_hcd 0000:00:1d.3: UHCI Host Controller
uhci_hcd 0000:00:1d.3: new USB bus registered, assigned bus number 5
uhci_hcd 0000:00:1d.3: irq 23, io base 0x00001060
usb usb5: New USB device found, idVendor=1d6b, idProduct=0001
usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb5: Product: UHCI Host Controller
usb usb5: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 uhci_hcd
usb usb5: SerialNumber: 0000:00:1d.3
usb usb5: configuration #1 chosen from 1 choice
hub 5-0:1.0: USB hub found
hub 5-0:1.0: 2 ports detected
uhci_hcd 0000:01:04.4: PCI INT B -> GSI 22 (level, low) -> IRQ 22
uhci_hcd 0000:01:04.4: UHCI Host Controller
uhci_hcd 0000:01:04.4: new USB bus registered, assigned bus number 6
uhci_hcd 0000:01:04.4: port count misdetected? forcing to 2 ports
uhci_hcd 0000:01:04.4: irq 22, io base 0x00003800
usb usb6: New USB device found, idVendor=1d6b, idProduct=0001
usb usb6: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb6: Product: UHCI Host Controller
usb usb6: Manufacturer: Linux 2.6.32-358.18.1.el6.x86_64 uhci_hcd
usb usb6: SerialNumber: 0000:01:04.4
usb usb6: configuration #1 chosen from 1 choice
hub 6-0:1.0: USB hub found
hub 6-0:1.0: 2 ports detected
PNP: PS/2 Controller [PNP0303:KBD,PNP0f0e:PS2M] at 0x60,0x64 irq 1,12
serio: i8042 KBD port at 0x60,0x64 irq 1
serio: i8042 AUX port at 0x60,0x64 irq 12
mice: PS/2 mouse device common for all mice
rtc_cmos 00:09: RTC can wake from S4
rtc_cmos 00:09: rtc core: registered rtc_cmos as rtc0
rtc0: alarms up to one year, y3k, 114 bytes nvram, hpet irqs
cpuidle: using governor ladder
cpuidle: using governor menu
EFI Variables Facility v0.08 2004-May-17
usbcore: registered new interface driver hiddev
usbcore: registered new interface driver usbhid
usbhid: v2.6:USB HID core driver
TCP cubic registered
Initializing XFRM netlink socket
NET: Registered protocol family 17
registered taskstats version 1
rtc_cmos 00:09: setting system clock to 2019-08-19 18:38:40 UTC (1566239920)
Initalizing network drop monitor service
Freeing unused kernel memory: 1264k freed
Write protecting the kernel read-only data: 10240k
Freeing unused kernel memory: 900k freed
Freeing unused kernel memory: 1672k freed
dracut: dracut-004-303.el6
dracut: rd_NO_LUKS: removing cryptoluks activation
dracut: rd_NO_LVM: removing LVM activation
device-mapper: uevent: version 1.0.3
device-mapper: ioctl: 4.23.6-ioctl (2012-07-25) initialised: dm-devel@redhat.com
udev: starting version 147
[drm] Initialized drm 1.1.0 20060810
[drm] radeon defaulting to kernel modesetting.
[drm] radeon kernel modesetting enabled.
radeon 0000:01:03.0: PCI INT A -> GSI 23 (level, low) -> IRQ 23
[drm] initializing kernel modesetting (RV100 0x1002:0x515E 0x103C:0x31FB).
[drm] register mmio base: 0xFBDF0000
[drm] register mmio size: 65536
radeon 0000:01:03.0: VRAM: 128M 0x00000000F0000000 - 0x00000000F7FFFFFF (64M used                                                                                                                              )
radeon 0000:01:03.0: GTT: 512M 0x00000000D0000000 - 0x00000000EFFFFFFF
[drm] Supports vblank timestamp caching Rev 1 (10.10.2010).
[drm] Driver supports precise vblank timestamp query.
[drm] radeon: irq initialized.
[drm] Detected VRAM RAM=128M, BAR=128M
[drm] RAM width 16bits DDR
[TTM] Zone  kernel: Available graphics memory: 12296286 kiB
[TTM] Zone   dma32: Available graphics memory: 2097152 kiB
[TTM] Initializing pool allocator
[TTM] Initializing DMA pool allocator
[drm] radeon: 64M of VRAM memory ready
[drm] radeon: 512M of GTT memory ready.
[drm] GART: num cpu pages 131072, num gpu pages 131072
usb 6-1: new full speed USB device number 2 using uhci_hcd
[drm] PCI GART of 512M enabled (table at 0x0000000037880000).
radeon 0000:01:03.0: WB disabled
radeon 0000:01:03.0: fence driver on ring 0 use gpu addr 0x00000000d0000000 and c                                                                                                                              pu addr 0xffff880037817000
[drm] Loading R100 Microcode
platform radeon_cp.0: firmware: requesting radeon/R100_cp.bin
[drm] radeon: ring at 0x00000000D0001000
[drm] ring test succeeded in 1 usecs
usb 6-1: New USB device found, idVendor=03f0, idProduct=1027
usb 6-1: New USB device strings: Mfr=1, Product=2, SerialNumber=0
usb 6-1: Product: Virtual Keyboard
usb 6-1: Manufacturer: HP
usb 6-1: configuration #1 chosen from 1 choice
input: HP Virtual Keyboard as /devices/pci0000:00/0000:00:1e.0/0000:01:04.4/usb6/                                                                                                                              6-1/6-1:1.0/input/input2
generic-usb 0003:03F0:1027.0001: input,hidraw0: USB HID v1.01 Keyboard [HP Virtua                                                                                                                              l Keyboard] on usb-0000:01:04.4-1/input0
input: HP Virtual Keyboard as /devices/pci0000:00/0000:00:1e.0/0000:01:04.4/usb6/                                                                                                                              6-1/6-1:1.1/input/input3
generic-usb 0003:03F0:1027.0002: input,hidraw1: USB HID v1.01 Mouse [HP Virtual K                                                                                                                              eyboard] on usb-0000:01:04.4-1/input1
Refined TSC clocksource calibration: 2665.908 MHz.
Switching to clocksource tsc
[drm] ib test succeeded in 0 usecs
[drm] Radeon Display Connectors
[drm] Connector 0:
[drm]   VGA-1
[drm]   DDC: 0x60 0x60 0x60 0x60 0x60 0x60 0x60 0x60
[drm]   Encoders:
[drm]     CRT1: INTERNAL_DAC1
[drm] Connector 1:
[drm]   VGA-2
[drm]   DDC: 0x6c 0x6c 0x6c 0x6c 0x6c 0x6c 0x6c 0x6c
[drm]   Encoders:
[drm]     CRT2: INTERNAL_DAC2
[drm] fb mappable at 0xF0040000
[drm] vram apper at 0xF0000000
[drm] size 786432
[drm] fb depth is 8
[drm]    pitch is 1024
fbcon: radeondrmfb (fb0) is primary device
Console: switching to colour frame buffer device 128x48
fb0: radeondrmfb frame buffer device
drm: registered panic notifier
Slow work thread pool: Starting up
Slow work thread pool: Ready
[drm] Initialized radeon 2.22.0 20080528 for 0000:01:03.0 on minor 0
dracut: Starting plymouth daemon
dracut: rd_NO_DM: removing DM RAID activation
dracut: rd_NO_MD: removing MD RAID activation
ata_piix 0000:00:1f.2: PCI INT B -> GSI 20 (level, low) -> IRQ 20
ata_piix 0000:00:1f.2: MAP [ P0 P2 P1 P3 ]
scsi0 : ata_piix
scsi1 : ata_piix
ata1: SATA max UDMA/133 cmd 0x1080 ctl 0x1088 bmdma 0x10a0 irq 20
ata2: SATA max UDMA/133 cmd 0x1090 ctl 0x1098 bmdma 0x10a8 irq 20
ata2.00: SATA link down (SStatus 4 SControl 300)
ata2.01: SATA link down (SStatus 4 SControl 300)
ata1.00: SATA link up 3.0 Gbps (SStatus 123 SControl 300)
ata1.01: SATA link down (SStatus 4 SControl 300)
ata1.00: ATA-7: GJ0250EAGSQ, HPG2, max UDMA/100
ata1.00: 488397168 sectors, multi 8: LBA48 NCQ (depth 0/32)
ata1.00: configured for UDMA/100
scsi 0:0:0:0: Direct-Access     ATA      GJ0250EAGSQ      HPG2 PQ: 0 ANSI: 5
sd 0:0:0:0: [sda] 488397168 512-byte logical blocks: (250 GB/232 GiB)
sd 0:0:0:0: [sda] Write Protect is off
sd 0:0:0:0: [sda] Write cache: enabled, read cache: enabled, doesn't support DPO                                                                                                                               or FUA
 sda: sda1 sda2 sda3
sd 0:0:0:0: [sda] Attached SCSI disk
EXT4-fs (sda1): mounted filesystem with ordered data mode. Opts:
dracut: Mounted root filesystem /dev/sda1
SELinux:  Disabled at runtime.
type=1404 audit(1566239923.324:2): selinux=0 auid=4294967295 ses=4294967295
dracut:
dracut: Switching root
                Welcome to CentOS
Starting udev: udev: starting version 147
shpchp: Standard Hot Plug PCI Controller Driver version: 0.4
EDAC MC: Ver: 2.1.0 Aug 28 2013
iTCO_vendor_support: vendor-support=0
iTCO_wdt: Intel TCO WatchDog Timer Driver v1.07rh
iTCO_wdt: unable to reset NO_REBOOT flag, device disabled by hardware/BIOS
sd 0:0:0:0: Attached scsi generic sg0 type 0
microcode: CPU0 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU1 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU2 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU3 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU4 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU5 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU6 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU7 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU8 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU9 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU10 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
microcode: CPU11 sig=0x206c2, pf=0x1, revision=0x13
platform microcode: firmware: requesting intel-ucode/06-2c-02
Microcode Update Driver: v2.00 <tigran@aivazian.fsnet.co.uk>, Peter Oruba
pps_core: LinuxPPS API ver. 1 registered
pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@li                                                                                                                              nux.it>
PTP clock support registered
dca service started, version 1.12.1
igb: Intel(R) Gigabit Ethernet Network Driver - version 4.0.1-k
igb: Copyright (c) 2007-2012 Intel Corporation.
igb 0000:02:00.0: PCI INT A -> GSI 24 (level, low) -> IRQ 24
igb 0000:02:00.0: added PHC on eth0
igb 0000:02:00.0: Intel(R) Gigabit Ethernet Network Connection
igb 0000:02:00.0: eth0: (PCIe:2.5Gb/s:Width x4) 1c:c1:de:e9:cb:b6
igb 0000:02:00.0: eth0: PBA No: FFFFFF-0FF
igb 0000:02:00.0: Using MSI-X interrupts. 8 rx queue(s), 8 tx queue(s)
igb 0000:02:00.1: PCI INT B -> GSI 34 (level, low) -> IRQ 34
igb 0000:02:00.1: added PHC on eth1
igb 0000:02:00.1: Intel(R) Gigabit Ethernet Network Connection
igb 0000:02:00.1: eth1: (PCIe:2.5Gb/s:Width x4) 1c:c1:de:e9:cb:b7
igb 0000:02:00.1: eth1: PBA No: FFFFFF-0FF
igb 0000:02:00.1: Using MSI-X interrupts. 8 rx queue(s), 8 tx queue(s)
hpwdt 0000:01:04.0: PCI INT A -> GSI 21 (level, low) -> IRQ 21
hpwdt 0000:01:04.0: HP Watchdog Timer Driver: NMI decoding initialized, allow ker                                                                                                                              nel dump: ON (default = 0/OFF), priority: LAST (default = 0/LAST).
hpwdt 0000:01:04.0: HP Watchdog Timer Driver: 1.3.0, timer margin: 30 seconds (no                                                                                                                              wayout=0).
hpilo 0000:01:04.2: PCI INT B -> GSI 22 (level, low) -> IRQ 22
udev: renamed network interface eth0 to rename2
power_meter ACPI000D:00: Found ACPI power meter.
udev: renamed network interface eth1 to eth2
udev: renamed network interface rename2 to eth1
[  OK  ]
Setting hostname pod27b3:  [  OK  ]
Setting up Logical Volume Management:   No volume groups found
[  OK  ]
Checking filesystems
Checking all file systems.
[/sbin/fsck.ext4 (1) -- /] fsck.ext4 -a /dev/sda1
/dev/sda1 contains a file system with errors, check forced.
/dev/sda1: 123739/655360 files (0.6% non-contiguous), 802009/2621440 blocks
[/sbin/fsck.ext4 (1) -- /tmp] fsck.ext4 -a /dev/sda3
/dev/sda3: recovering journal
/dev/sda3: clean, 65/14483456 files, 962230/57903616 blocks
[  OK  ]
Remounting root filesystem in read-write mode:  [  OK  ]
Mounting local filesystems:  EXT4-fs (sda3): mounted filesystem with ordered data                                                                                                                               mode. Opts:
[  OK  ]
Enabling local filesystem quotas:  [  OK  ]
Enabling /etc/fstab swaps:  Adding 2097144k swap on /dev/sda2.  Priority:-1 exten                                                                                                                              ts:1 across:2097144k
[  OK  ]
Entering non-interactive startup
Compat-mlnx-ofed backport release: 3a2d7bf
Backport based on /mswg/git/mlnx_ofed_2_0/mofed-linux-2.0.git 3a2d7bf
compat.git: /mswg/git/mlnx_ofed_2_0/mofed-linux-2.0.git
mlx4_core: Mellanox ConnectX core driver v1.1 (Jan 23 2014)
mlx4_core: Initializing 0000:03:00.0
mlx4_core 0000:03:00.0: PCI INT A -> GSI 30 (level, low) -> IRQ 30
mlx4_core 0000:03:00.0: command SET_PORT (0xc) failed: in_param=0x6098b5000, in_m                                                                                                                              od=0x1, op_mod=0x0, fw status = 0x40
mlx4_core 0000:03:00.0: command SET_PORT (0xc) failed: in_param=0x6098b5000, in_m                                                                                                                              od=0x2, op_mod=0x0, fw status = 0x40
<mlx4_ib> mlx4_ib_add: mlx4_ib: Mellanox ConnectX InfiniBand driver v1.0 (Jan 23                                                                                                                               2014)
mlx4_en: Mellanox ConnectX HCA Ethernet driver v2.1.6 (Jan 23 2014)
NET: Registered protocol family 10
lo: Disabled Privacy Extensions
Default coalesing params for mtu:4092 - rx_frames:88 rx_usecs:16
Default coalesing params for mtu:4092 - rx_frames:88 rx_usecs:16
Loading HCA driver and Access Layer:[  OK  ]
Setting up InfiniBand network interfaces:
ADDRCONF(NETDEV_UP): ib0: link is not ready
Bringing up interface ib0:[  OK  ]
Setting up service network . . .[  done  ]
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
waiting for mlx4_0 card to register within the fabric: Polling
mlx4_core 0000:03:00.0: mlx4_ib: Port 1 logical link is up
ADDRCONF(NETDEV_CHANGE): ib0: link becomes ready
mlx4_0 card is: LinkUp
Bringing up loopback interface:  [  OK  ]
Bringing up interface eth0:  Device eth0 does not seem to be present, delaying initialization.
[FAILED]
Bringing up interface ib0:  [  OK  ]
ntpdate: Synchronizing with time server: [FAILED]
Starting portreserve: [  OK  ]
Starting ntpd: [  OK  ]
Starting syslog-ng: Connection failed; fd='10', server='AF_INET(172.16.254.1:514)', local='AF_INET(0.0.0.0:0)', error='Network is unreachable (101)'
Initiating connection failed, reconnecting; time_reopen='10'
[  OK  ]
Starting irqbalance: [  OK  ]
Starting rpcbind: [  OK  ]
Starting NFS statd: [  OK  ]
Starting system message bus: [  OK  ]
Mounting NFS filesystems:  RPC: Registered named UNIX socket transport module.
RPC: Registered udp transport module.
RPC: Registered tcp transport module.
RPC: Registered tcp NFSv4.1 backchannel transport module.
FS-Cache: Loaded
Registering the id_resolver key type
FS-Cache: Netfs 'nfs' registered for caching
[  OK  ]
Mounting Lustre filesystems:  LNet: HW CPU cores: 12, npartitions: 4
alg: No test for crc32 (crc32-table)
alg: No test for adler32 (adler32-zlib)
alg: No test for crc32 (crc32-pclmul)
padlock: VIA PadLock Hash Engine not detected.
Lustre: Lustre: Build Version: 2.4.3-RC1--PRISTINE-2.6.32-358.18.1.el6.x86_64
LNet: Added LNI 192.168.227.3@o2ib [8/256/0/180]
Lustre: Layout lock feature supported.
Lustre: Mounted home-client
Lustre: Layout lock feature supported.
Lustre: Mounted scratch-client
[  OK  ]
Mounting other filesystems:  [  OK  ]
Starting acpi daemon: [  OK  ]
Starting HAL daemon: [  OK  ]
Starting ipmi drivers: ipmi device interface
[  OK  ]
Starting clusterd: [  OK  ]
Starting sshd: [  OK  ]
Starting xinetd: [  OK  ]
Starting pbs_mom  daemon: [  OK  ]
Starting crond: [  OK  ]

CentOS release 6.4 (Final)
Kernel 2.6.32-358.18.1.el6.x86_64 on an x86_64

pod27b3 login:
```
