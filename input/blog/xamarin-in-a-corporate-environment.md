---
Title: Xamarin In A Corporate Environment
Published: 2015/12/14
Tags:
  - xamarin
  - vmware workstation
  - virtual machine
---

When working in a corporate environment I usually have my Macbook Pro setup as follows:


```
+--------------------+    USB PASS-THROUGH INTO VIRTUAL MACHINE
|                    | <------------------------------------------+
|                    |    WHEN DOING UWP DEVELOPMENT              |
|                    |                                            |
|   VIRTUAL MACHINE  |                                            |
|                    |                                            |
|                    |           MACBOOK PRO LAPTOP               |
|                    | +-----------------------------------+      |
|                    | |                                   |      |
|                    | |                                   |      |
|   CORPORATE SOE    | |                                   |      |
|   WINDOWS 7/8/10   | |              MAC OSX              | +----+---+
|   VISUAL STUDIO    | |          XAMARIN STUDIO           | |        |
|                    | |                                   | |        |
|    UWP UI & PCL    | |        IOS UI & ANDROID UI        | |        |
|                    | |                                   | |        |
|                    | |                                   | | MOBILE |
|                    | |                                   |<+        |
|                    | |                                   | |        |
|                    | |                                   | |        |
|                    | |                                   | |        |
|                    | |                                   | |        |
+---------^----------+ +--------------------^--------------+ +---^----+
      |                                 |                    |
+---------+----------+ +--------------------+--------------------+----+
|    CORP NETWORK    | |              DIRECT INTERNET                 |
|  USB ETH ADAPTER   | |           INBUILT WIFI ADAPTER(s)            |
+--------------------+ +----------------------------------------------+
```

By using an Apple USB Network Adapter ([which does work on Windows](/blog/apple-usb-network-drivers-for-windows)) and using the USB pass-through feature of VMWare Workstation it is possible for a single machine to be connected to two different networks without violating your IT security policy.

When I need direct internet access on the virtual machine then that is achieved by disconnecting the adapter and temporarily changing the virtual network adapter mode from host to bridged/nat.

This setup allows the best of both worlds, simultaneous direct internet access and access to corporate resources such as bug trackers, source control, email, intranet and timesheet systems.

I find some form of direct internet connectivity is an absolute must when doing mobile development otherwise productivity tends to go out the window. If you are in the unfortunate circumstance whereby you have to use a Windows NTLM based authentication proxy server on Mac OSX then I suggest reading [this article for a solution](/blog/to-view-this-page-you-need-to-login-to-the-proxy-server).
