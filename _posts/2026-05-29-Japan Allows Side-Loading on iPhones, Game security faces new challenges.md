---
layout: post
title: "Japan Allows Side-Loading on iPhones, Game security faces new challenges"
date: 2026-05-29 16:30:00 +0800
categories: anti-cheat
tags: iOS  iPhone  App Store
---

Recently, Apple announced on its official website that to comply with Japan's newly enacted Act on Promotion of Competition in the Market for Specific Smartphones, the Japanese version of the iPhone has officially opened up third-party app stores and app sideloading distribution, while also permitting developers to use third-party payment systems.<!-- more --> 

![315_21](/assets/res/2026/05291.png) 

The term “sideloading” refers to the practice where iPhone users can choose to download apps not from the App Store, but instead from the official website of the relevant app or third-party app stores.

For developers, this news is a mixed blessing. The introduction of sideloading will grant developers greater flexibility in releasing applications while also saving them some of the fees charged by the App Store.

However, developers must also pay greater attention to application quality, security, and privacy protection. The influx of external applications will inevitably disrupt closed-source ecosystems, leaving users more vulnerable to malware, scams, data tracking, and other issues.

For gaming applications, a new wave of Cheats and Hack may emerge. Cheating methods for iOS games will extend beyond traditional jailbreaking, giving rise to a series of Game Black/Gray Industry, intensifying the battle for game security.

![315_21](/assets/res/2026/05292.jpg) 

To address Cheats and Hack issues in iOS games, JikGuard has developed a mature and comprehensive protection solution. This solution has been integrated into multiple popular games and has demonstrated outstanding protection capabilities.

**■ Code Protection**

JikGuard supports code logic obfuscation and string obfuscation. It is an obfuscation pass based on the LLVM IR layer, but it does not utilize the open-source LLVM project. Instead, it hooks into Xcode's execution flow to minimize user onboarding costs and impact on user experience, remaining completely transparent to users.

![315_21](/assets/res/2026/05293.png) 

**■ Code Behavior Protection**

Protection during local storage (NSUserDefaults, sqlite file data encryption): Files are encrypted before storage during NSUserDefaults and sqlite storage operations.

Network data transmission protection: Encryption solutions are provided for client-side data transmission, effectively preventing data interception through network interfaces.

**■ Code Anti-Tamper Protection**

**Anti-Jailbreak Protection**

Utilizes proprietary detection technology to achieve precise identification without false positives. It comprehensively evaluates multiple runtime indicators to detect unknown anti-jailbreak plugins or jailbreak methods, and processes anti-jailbreak plugins without missing any threats.

**Anti-debugging Protection**

Dual-layer defense: First employs detection methods such as ptrace, syscall, sysctl, and exception handling, then encrypts the protective code for enhanced effectiveness.

**Anti-Re-Signing Protection**

Precisely verifies the package's internal signature by comparing the signature stored during hardening with the signature obtained at runtime.

**Anti-Modification Protection**

During the code countermeasure defense phase, JikGuard provides local detection code and safeguards its integrity.

Additionally, JikGuard has developed an online signature update detection feature. Upon acquiring samples, it can immediately distribute signatures to protect app security in the shortest possible time.