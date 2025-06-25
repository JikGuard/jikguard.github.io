---
layout: post
title: "iOS Rootless Jailbreak Detection Solution"
date: 2025-06-19 16:30:00 +0800
categories: anti-cheat
tags: iOS  Rootless  Jailbreak
---

Unlike Android's open-source ecosystem, iOS has always been a closed-source ecosystem with a higher level of security. Hardware, software, and services in the system undergo strict auditing and testing to ensure security and stability.<!-- more -->  

According to JikGuard's observation, although the iOS system has a certain degree of security, it is not without loopholes, such as iOS jailbreaking, a common means of cheating in the market.

![315_21](/assets/res/2025/jailbreak.png)  

iOS jailbreaking refers to removing or bypassing Apple's operating system restrictions on an iOS device through software or hardware vulnerabilities, so as to obtain the highest privileges on the device.

After the device is jailbroken, users can use software such as Cydia Manager to bypass the App Store to install a variety of unaudited plug-ins and cheats, modify system files, and even access system-level APIs through the highest privileges gained.

![315_21](/assets/res/2025/Cydia.jpg)  

In order to obtain advanced user privileges, traditional jailbreaking will reinstall the file system and modify the system partition, resulting in the jailbreak device can not be updated normally, the operation will become unstable, and want to restore the device needs to go through a series of complex operations, the cost of cheating is high.

Moreover, traditional jailbreaking also leaves more obvious traces of cheating such as destroying the file system image and disabling signature checking, which can be used to determine whether the device is in a jailbreak environment.

![315_21](/assets/res/2025/iOSJailbreak.png)  
Common iOS Jailbreak Detection Methods

As the shortcomings of traditional jailbreaking become more and more difficult to realize technically, the black and grey industry has discovered a new means of “rootless jailbreaking”.

It has been observed that rootless jailbreak tools are very diverse, the common ones are unc0ver, rootlessJB, Dopamine and so on. Next, let's take the Dopamine tool as an example to analyze the rootless jailbreak process.

The way to bypass the App Store censorship is to use the Trollstore tool, which is based on the CoreTrust vulnerability. The tool installs applications through the ipa installer, does not require a certificate, in a non-jailbreak environment can also bypass the App Store, to realize the random installation of external applications.

![315_21](/assets/res/2025/Trollstore.jpg)  

Through the Trollstore, download and install the Dopamine tool, after a series of settings, you can write a rootless jailbreak for the device, thus facilitating all kinds of modifiers, cheats, and realize the game cheats.

![315_21](/assets/res/2025/Dopamine.png)  
Dopamine Tool

Compared with traditional jailbreak, rootless jailbreak does not grant access to the root directory of the file system (“/”), and does not change the contents of the system partition, so you can delete the jailbreak environment and restore the system at any time.

In addition, Rootless Jailbreak provides all the content needed for file system extraction without bundling additional content, with fewer traces of cheating and hidden jailbreak features. These features make rootless jailbreak widely used by black and gray industries.

![315_21](/assets/res/2025/Dopaminehide.png)  
Dopamine can hide and remove jailbreaks

**For the jailbreak problem faced by iOS, JikGuard has analyzed the jailbreak plug-ins and developed a jailbreak detection module and supporting security features, and accessed a number of popular games and verified the excellent protection capabilities.**

**✔ Anti-jailbreak protection**
Using exclusive detection technology to achieve accurate identification without false alarms, will be based on a variety of runtime information comprehensive judgment, unknown anti-jailbreak plug-ins/jailbreak methods to do the detection, and for anti-jailbreak plug-ins to do the processing, not miss the report.

**✔ Anti-debugging protection**
Double protection, first use ptrace, syscall, sysctl, exception and other detection methods, and then encrypt the protection code for better results.

**✔ Anti-re-signature protection**
Accurately verify the signature inside the package, use the signature stored at the time of reinforcement, and compare it with the signature obtained at runtime.

**✔ Anti-Modifier Protection**
In the code counter protection phase, JikGuard provides local detection of code and protects its validity.

In addition, JikGuard has developed online feature update detection features, which can be issued at the first time after acquiring samples to protect the security of the app in the shortest time.