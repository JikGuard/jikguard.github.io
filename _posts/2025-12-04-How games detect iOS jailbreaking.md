---
layout: post
title: "How games detect iOS jailbreaking"
date: 2025-12-04 16:30:00 +0800
categories: anti-cheat
tags: iOS  jailbreaking  cydia
---

Unlike Android's open-source ecosystem, iOS has always adhered to a closed-source ecosystem with higher security. The hardware, software, and services in the system undergo rigorous review and testing to ensure security and stability.<!-- more --> 

According to JikGurd's observations, although the iOS system has a certain level of security, it is not without vulnerabilities, such as the common cheating method known as iOS jailbreak.

![315_21](/assets/res/2025/12043.jpeg)  
iOS jailbreak tool Unc0ver

iOS jailbreaking refers to removing or bypassing Apple's operating system restrictions on iOS devices through software or hardware vulnerabilities in order to obtain the highest privileges on the device.

After jailbreaking the device, users can obtain the highest privileges to install software such as Cydia Manager, thereby bypassing the App Store to install various unreviewed plug-ins and cheats, modify system files, and even access system-level APIs.

![315_21](/assets/res/2025/12044.jpg)  
Cydia Manager

In the specific case of game cheating, cheat authors can hack game programs for reverse analysis, or use substrate to hook the game logic to create various game cheats.

These game cheats can be installed directly by other jailbroken players, or distributed through Cydia Manager. Given the potential negative impact of users using jailbroken devices, many games will check whether the device is jailbroken.

Common jailbreak detection methods include: checking for jailbreak files and directories, verifying permissions, and inspecting the Sandbox. These methods can be used to determine whether a device is jailbroken, but they also have some limitations.

![315_21](/assets/res/2025/12045.png)  
Common iOS jailbreak detection methods

For example, when checking for jailbreak files and directories, the system typically verifies the existence of /Application/Cydia.app. However, if a jailbroken device has not used the Cydia store, this can result in false negatives.

Another scenario is when a device uses an imperfect jailbreak and the Cydia store, and after a reboot, the device reverts to its non-jailbroken state, but /Application/Cydia.app remains present, leading to a false positive.

In other cases, cheaters can use anti-jailbreak detection plugins to evade detection. Common plugins include HideJB/abapass/fyjb, etc.

These plugins perform numerous hooks on the system interface layer, filtering all strings related to jailbreaking, thereby preventing application-level detection.

![315_21](/assets/res/2025/12046.png)  
HideJB interface

Additionally, JikGuard has collected and analysed a large number of anti-jailbreak detection plugins, summarising some of their common methods for bypassing jailbreak detection:

Hooking NSFileManager's fileExistsAtPath to filter out jailbreak-related strings.

Faking the process module list to prevent jailbreak-related modules from being detected.

Hooking C-layer APIs such as stat/access/lstat to filter out jailbreak-related files.

Patch hook the svc assembly code in the app code to hide jailbreak-related files.

In response to the jailbreak challenges faced by iOS, JikGuard analysed a large number of anti-jailbreak plug-ins and developed a jailbreak detection module and accompanying security features. It has been integrated into a number of popular games and has proven its excellent protection capabilities.

**Anti-jailbreak protection**

Using exclusive detection technology, it accurately identifies false positives and comprehensively judges based on a variety of runtime information to detect unknown anti-jailbreak plug-ins/jailbreak methods and process anti-jailbreak plug-ins without missing any reports.

**Anti-debugging protection**

Double protection, first using ptrace, syscall, sysctl, exception and other detection methods, then encrypting and protecting the protection code for better results.

**Anti re-signing protection**

Accurately verifies the signature in the package, uses the signature stored during hardening, and compares it with the signature obtained at runtime.

**Anti-modifier protection**

During the code countermeasure protection phase, JikGuard provides local detection code and protects its validity.

In addition, JikGuard has developed an online feature update detection feature, which can obtain samples and distribute features immediately, protecting the security of the app in the shortest possible time.