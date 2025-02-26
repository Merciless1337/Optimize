# Optimize
Optimize Windows 10 22h2 for minimal latency and great hitreg
1. Install Windows X-Lite Optimum 10.
2. Set Windows language to ENG.
3. Download the files.
4. Follow the guide.

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

# Chapter 3 - TCP Optimizer.
1. General settings
  MTU: 1472
  TCP Window Auto-Tuning: Disabled.                                  Time to Live (TTL): 64
  Windows Scaling Heuristics: Disabled.                              ECN Capability: Disabled.
  Congestion Control Provider: ctcp.                                 Checksum Offloading: Disabled.
  Receive-Side Scaling: Enabled.                                     TCP Chimney Offload: Disabled.
  R.Segment Coalescing: Disabled.                                    Large Send Offload (LSO): Disabled.
                                                                     TCP 1323 Timestamps: Disabled.

2. Advanced settings
   IMPORTANG: STARTING FROM THE LEFT > DOWN > RIGHT > DOWN!
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
