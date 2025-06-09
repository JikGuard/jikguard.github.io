---
layout: post
title: "How Games Detect Root Permissions"
date: 2025-05-15 16:30:00 +0800
categories: anti-hack
tags: anti root  root detection  root
---

Root permissions, i.e. super user permissions, in Android system, obtaining root permissions means that users can modify system files, remove pre-installed apps, install special apps and so on.<!-- more -->  

Under the Root environment, games face considerable security risks. Users obtaining the highest permissions means that they can read and tamper with the game's memory through various tools, providing an environment for game cheats, Hack and other operations.

![315_21](/assets/res/2025/ggmodifiers.gif)  
▲ Using modifiers to tamper with game memory in a rooted environment  

Although there are fewer systems with root permissions after Android 6.0, there are still many ways to get root permissions, mainly through brushing, virtual environments and PC emulators.

Obtaining root permissions through brushing usually involves unlocking the bootloader and brushing a customized ROM with root permissions, and online tutorials on brushing different models of cell phones are very detailed, which greatly reduces the threshold of brushing.

At present, the common way is to brush the device with the Magisk tool, which runs in a “systemless” way, allowing users to gain root permissions without modifying the system partition, and supporting the maintenance of root status after a system update.

![315_21](/assets/res/2025/magisk.png)  

However, due to the security risks such as warranty invalidation and system instability of brushing, it is safer and more convenient to use virtual machines, virtual frameworks, emulators, etc. to obtain root permissions.

Virtual machines and virtual frameworks can simulate multiple Android systems on a single phone, and the simulated systems run independently and can be flexibly configured to run multiple applications simultaneously, and they come with root permissions, which can be turned on in the interface.  

![315_21](/assets/res/2025/vmos.jpg)   

In addition, there are also Android emulators running on the PC side, which can simulate multiple Android systems on the PC side and also come with a root permission switch, which provides convenience for cheats and hacks.

It has been observed that certain features of emulators are also utilized, such as MuMu emulator, which does not require a reboot when opening/closing root permissions. Players can open root permissions to open the cheats first, and then close the root permissions to run the game, so that the cheats get the root permissions, while the game side does not detect the root environment.

Under the root environment, users can use modifiers to search the game's memory and tamper with it, such as the number of currencies, character data, key props, etc. in the game, or use reverse tools to analyze and tamper with the game to create hack and ad-free versions of the game.

The above problems will destroy the fairness of the game, leading to serious consequences such as the loss of normal players, damage to the manufacturer's revenue, and even the shortening of the game's life cycle.

In the security confrontation, cheaters also try to hide the root permissions by all means to avoid the security detection of the game. A common method is to use Magisk to randomize the package name and edit the new app name and reinstall it.

After repeating the operation of hiding the Magisk app several times, we found that the randomized Magisk Manager apk packages are not the same in different installations, not only the package name is randomized, but also the signature is changed.

![315_21](/assets/res/2025/MagiskHide.png)  
▲ Using modifiers to tamper with game memory in a rooted environment  

Magisk can also hide root permissions globally with the Shamiko module. Simply install the module, reboot the device, and hide the root permissions.

Cheaters can also add game cheats, game modifiers and other applications to the template and set them to be invisible through the LSP framework in Magisk, and then apply the template to the game, thus hiding the cheats and modifiers during the game operation to avoid security detection.

By doing so, the device's root permissions, Magisk apps, cheats and other possible detection clues are hidden, which can bypass most of the traditional detection methods.

**JikGuard has customized an exclusive solution to address the root permissions cheating problem faced by games, which has been accessed by a number of popular games and proven to have excellent detection capabilities.**  

**Security Risk Environment Detection**

Unlike other products on the market, JikGuard Hardening uses a lower-level detection method to accurately distinguish the operating environment of the game, identifying various types of risky environments such as Root, virtual machines, virtual frameworks, cloud phones, jailbreaks, etc., and providing personalized flashing strategies.

**Magisk Specialized Detection**

JikGuard's exclusive detection program can accurately identify and perform flashing operations even if Magisk has all hidden options turned on.

**Anti-Memory Modification**

JikGuard has developed a behavioral detection solution that accurately identifies memory modification and kills all types of memory modification cheats and their variants, providing effective protection against the risk of memory modification.
