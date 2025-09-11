---
layout: post
title: "iOS Code Encryption Solutions"
date: 2025-09-11 16:30:00 +0800
categories: anti-cheat
tags: iOS  Code Encryption  Cydia
---

Unlike Android's open source ecosystem, iOS's closed source ecosystem's hardware, software, and services are strictly reviewed and tested, ensuring a certain level of security and stability. However, this has also led to some companies neglecting security issues during development, such as iOS game anti-cheats and anti-hacking.<!-- more -->

![315_21](/assets/res/2025/AppStore.png)  

According to JikGuard's observations, while the iOS system has a certain level of security, it is not without vulnerabilities, such as the common iOS jailbreak. After an iOS device is jailbroken, users can gain the highest level of system access and install third-party software outside the App Store using tools like the Cydia Manager.

![315_21](/assets/res/2025/Cydia.png)  
iOS jailbreak symbol - installing Cydia Manager

In the current game market, multi-terminal interconnection has become a trend. As a whole, any game security issue on any terminal will have a serious impact. In response to the challenge of anti-cheats for iOS games, JikGuard has developed a mature and comprehensive protection solution, which has been integrated into a number of popular games and verified to have excellent protection capabilities.  

■ Code-level Protection  

JikGuard supports code logic obfuscation and string obfuscation, which are obfuscation passes based on the LLVM IR layer, but it does not use the open-source LLVM project.  

Instead, it uses the HOOK Xcode execution process to minimise user onboarding costs and optimise the user experience, making it completely transparent to users.  

![315_21](/assets/res/2025/JikGuardiOShardening.png)  
JikGuard iOS hardening solution obfuscation effect diagram

■ Code Behaviour Protection

Local storage protection (NSUserDefaults, sqlite file data encryption):

When executing NSUserDefaults and sqlite storage operations, files are encrypted before storage.

Network data transmission protection:

Provides an encryption solution for client data transmission, effectively preventing data interception through network interfaces.
 
■ Code Anti-attack Protection

▶ Anti-debugging

Double protection: first use ptrace, syscall, sysctl, exception and other detection methods, then encrypt and protect the protection code for better results.
 
▶ Anti-jailbreak

Multi-dimensional comprehensive detection, such as checking the installation of certain Apps, the existence of files, directory access permissions, etc. to comprehensively determine whether a jailbreak has occurred.
 
▶ Anti Re-signing

Accurately verifies the signature in the package, uses the signature stored during hardening, and compares it with the signature obtained at runtime.
 
▶ Anti-modifier

During the code countermeasure protection phase, JikGuard provides local detection code and protects its validity.

In addition, JikGuard has developed an online feature update detection feature, which can obtain samples and distribute features immediately, protecting the security of the App in the shortest possible time.