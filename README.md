# It's recommended to download the RAW README.md file from github. - Merciless.
# Every file needed is provided by me in the archive! (NOT ISLC).
# Optimize
Optimize Windows 10 22h2 for minimal latency and great hitreg
1. Install Windows X-Lite Optimum 10.
2. Set Windows language to ENG.
3. Download the files.
4. Follow the guide.
5. IMPORTANT! Run everything in this guide as Administrator!

# Chapter 1
1. Install latest network(Ethernet/LAN) adapter drivers and do a clean GPU driver installation and reboot.
2. Open wincry, go to services and click apply.
3. Open AncelsPerformanceBatch and go through it, optimize everything.
4. IMPORTANT: Leave monitor sound ON and DISABLE TOUCHPAD (MOUSE SMOOTHING)!

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
4. We will use other batches later.
5. DONE.

# Chapter 5 - INTEL ONLY - RWeverything
1. Download RWEverything
2. Click the PCI Devices Button on the top left, then click the 32 bit button when the window opens
3. Select your xHCI USB Controller in the drop down box
4. Look at your first Bar Address Register (BAR) on the right, then double click the box that has the same numbers. Usually its the second one in the first column
1. IMPORTANT: For the Address part, if you have two BAR's, you put the numbers in the second BAR first, then the first one. If you have only one, you just put the first BAR.
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
1. MSR_DRAM_POWER_LIMIT=0x618
2. MSR_PP1_POWER_LIMIT=0x640
3. MSR_PKG_RAPL_POWER_LIMIT=0x610
4. MSR_PPO_POWER_LIMIT=0x638
5. Click Done
6. IMPORTANT! Don't close the windows in RWeverything! Close RWeverything only.

PART 3
1. Copy XHCI-IMOD-Interval.ps1 to C drive (C disk).
2. Go to windows task scheduler (Win+R taskschd.msc).
3. Create task
4. https://imgur.com/a/61iC9FD
5. Program for task: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
6. Arguments: -ExecutionPolicy Bypass -File "C:\XHCI-IMOD-Interval.ps1"

# Congrats! The easy part is done. Now for the manual optimizations!
# UDP and HitReg
1. https://youtu.be/IqVZK74yeNE?si=gkYNuL9xca6X0vuw
2. https://youtu.be/es-I4-MVHI4?si=bRp8Zu3PXl2-tgBy
3. https://youtu.be/rfIqPHPuOUs?si=_J5zGtaWiRTrbvoU
4. DONE 100% BULLET REG!

# 0 INPUT LAG POWER PLAN
1. https://youtu.be/PDeYn4-eXTU?si=Lszf823g60VxP9Rk
2. DONE!

# CORRECT TIMER RESOLUTION FOR WINDOWS 10 (FURTHER DECREASE INPUTLAG)!
1. Download ISLC
2. Copy dpclat.exe from my archive>programs To C drive (C disk).
3. Win+R > taskschd.exe
4. Create task for dpclat.exe at logon. https://imgur.com/a/7dEcfPV
5. Open ISLC https://imgur.com/a/IHhMtdo
6. Open measuresleep.exe from my programs and keep watching delta
7. Keep increasing TimerResolution in ISLC until you get minimal delta in measuresleep.exe
8. Reboot and check that dpclat starts at logon and islc starts with a delay.
9. Check measuresleep.exe to make sure everything is right.
10. IMPORTANT! Always keep dpclat running in background (just click stop)! It decreases delta from 15ms to 0.9ms :D
11. DONE!

# INSANE PERFORMANCE TWEAK - PROCESS LASSO
1. Install process lasso from my archive.
2. https://youtu.be/9twBwLU-D-8?si=X2_1ggUu5cFdo8S9
3. DONE!

# MSI TOOL
1. Open MSI Utility from my archive.
2. Set MSI Mode for your graphics card, network adapter and usb controller.
3. Set all priorities to Undefined.
4. DONE!

# SPEED UP KEYBOARD INPUT
1. Open FilterKeysSetter from my archive.
2. Check everything like me and click apply.
3. https://imgur.com/a/fgSxRmT
4. DONE!
