# It's recommended to download the RAW README.md file from github. - Merciless.
# Optimize
Optimize Windows 10 22h2 for minimal latency and great hitreg
1. Install Windows X-Lite Optimum 10.
2. Set Windows language to ENG.
3. Download the files.
4. Follow the guide.
IMPORTANT! Run everything in this guide as Administrator!

# Chapter 1
1. Install latest network(Ethernet/LAN) adapter drivers and do a clean GPU driver installation and reboot.
2. Open wincry, go to services and click apply.
3. Open AncelsPerformanceBatch and go through it, optimize everything.
  IMPORTANT: Leave monitor sound ON and DISABLE TOUCHPAD (MOUSE SMOOTHING)!

# Chapter 2 - DNS Jumper
1. Open with admin privileges.
2. Click "Fastest DNS".
3. Click "Start DNS test".
4. Click "Apply DNS Server".
5. Close the window and click "Apply DNS".
6. Close the app.

# Chapter 3 - TCP Optimizer. (View RAW on github).
1. General settings
  MTU: 1472
  TCP Window Auto-Tuning: Disabled.                                  Time to Live (TTL): 64
  Windows Scaling Heuristics: Disabled.                              ECN Capability: Disabled.
  Congestion Control Provider: ctcp.                                 Checksum Offloading: Disabled.
  Receive-Side Scaling: Enabled.                                     TCP Chimney Offload: Disabled.
  R.Segment Coalescing: Disabled.                                    Large Send Offload (LSO): Disabled.
                                                                     TCP 1323 Timestamps: Disabled.

2. Advanced settings
   IMPORTANG: GOING LEFT TO RIGHT!
   4                                                                 0
   2                                                                 optimal
   4                                                                 disabled
   5                                                                 gaming
   6                                                                 disabled
   7                                                                 enabled
   2                                                                 disabled
   disabled                                                          default
                                                                     optimized
   2000                                                              65534
   300                                                               30
   
APPLY CHANGES!

# Chapter 4 - Batches.
1. Run Disable Mitigations.
2. Run Disable_MPO_FSO.
3. Run Disable_SPECTRE+MELTDOWN_Protection.
We will use other batches later.
DONE.

# Chapter 5 - INTEL ONLY - RWeverything
1. Download RWEverything
2. Click the PCI Devices Button on the top left, then click the 32 bit button when the window opens
3. Select your xHCI USB Controller in the drop down box
4. Look at your first Bar Address Register (BAR) on the right, then double click the box that has the same numbers. Usually its the second one in the first column
   IMPORTANT: For the Address part, if you have two BAR's, you put the numbers in the second BAR first, then the first one. If you have only one, you just put the first BAR.
5. Click the Address Box in the new window that comes up
6. Enter your Bar Address Register's in the address box
7. After entering your Address, delete the last 4 digits and replace it with 2024, then click Ok
8. If you're at the right address, the top left box should be 00C8
9. Double click the 00C8 box, then replace all 1s in the dataset with 0
10. Click Done
VIDEO GUIDE PART 1 https://streamable.com/sp4naf

PART 2
1. Click Access
2. CPU MSR
3. Click the icon that says User
4. Add these commands one by one:
   MSR_DRAM_POWER_LIMIT=0x618
   MSR_PP1_POWER_LIMIT=0x640
   MSR_PKG_RAPL_POWER_LIMIT=0x610
   MSR_PPO_POWER_LIMIT=0x638
5. Click Done
IMPORTANT! Don't close the windows in RWeverything! Close RWeverything only.

PART 3
1. Copy XHCI-IMOD-Interval.ps1 to C drive (C disk).
2. Go to windows task scheduler (Win+R taskschd.msc).
3. Create task
4. https://imgur.com/a/61iC9FD
  Program for task: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
  Arguments: -ExecutionPolicy Bypass -File "C:\XHCI-IMOD-Interval.ps1"

# Congrats! The easy part is done. Now for the manual optimizations!
