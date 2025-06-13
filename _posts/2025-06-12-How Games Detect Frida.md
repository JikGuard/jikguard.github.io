---
layout: post
title: "How Games Detect Frida"
date: 2025-06-12 16:30:00 +0800
categories: anti-cheat
tags: Frida  IDA  injection cheats
---

In the process of game security confrontation, there are a lot of cheats based on the implementation of the game memory module modification, this kind of cheats usually use memory modifiers, in addition, there is a relatively higher threshold, but also more difficult to detect the “injection cheats”.<!-- more -->  

According to JikGuard game security statistics, among the many security risks faced by games, injection cheats accounted for as much as 21%. Such a high percentage shows the seriousness of the harm caused by injection cheats.

![315_21](/assets/res/2025/GameSecurityRisks.jpg)  
JikGuard game security statistics: the proportion of game security risks

The principle of injection cheats is also very diverse. Android system can use SO injection, ptrace injection, Zygote injection and infection of ELF files and other ways to realize. In this article, we will focus on explaining the injection principles and solutions of the Frida framework and its variants.

Frida is a dynamic staking tool that can insert code into the memory space of the native APP and perform dynamic debugging and modification.

![315_21](/assets/res/2025/Frida1.png)  
Frida official website

The injection principle is based on ptrace, Frida injects frida-agent-xx.so module into the game process by calling system ptrace, and then communicates with frida-server installed on the cell phone through this module, thus realizing a series of analysis and hook operations, such as hooking the attack function of your own character in the game to achieve the cheating functions such as doubling the attack and so on. doubling and other cheating features.

![315_21](/assets/res/2025/Fridaida1.png)  
Frida and ida joint debugging apk

Due to the simple configuration environment, convenient operation, support for Java layer and Native layer hook operation, and the use of python, JavaScript language, greatly reducing the threshold of reverse analysis, cheat modification, in addition, Frida also has the following detection difficulties:

Numerous variants, Frida as a mature open source tool, has a large number of variants, such as the common hluda-server, these variants can hide the Frida features, bypassing the traditional means of detection, increasing the difficulty of detection and elimination.

Complexity of cheating, Frida is based on python and javascript language, which can be adapted to Android, iOS, Linux, Windows and other platforms, and can be used with different tools to realize cheating on different platforms.

**For the risk of injection cheats faced by games, JikGuard has customized a special response strategy, and the solution has been connected to a number of popular games and verified the excellent protection ability.**

**Active Recognition of Malicious Modules**

Unlike other security products in the market, which need to obtain samples to combat cheats, JikGuard's exclusive “active identification of malicious module mechanism” actively identifies suspicious modules, and together with the online combat features, achieves proactive defense, which significantly shortens the cycle of cheats investigation.

**Anti-Injector Features**

JikGuard prohibits the use of Xposed, Frida, and other cheats module injectors, preventing the injection from modifying the game memory and other malicious behaviors, and immediately flashing back once it is found.

**Anti-Debugging Features**

Prevent cheats authors from debugging the game, prevent static or dynamic analysis of the game, and immediately flashback once found.

**Security environment detection features**

Unlike other products on the market, JikGuard Hardening adopts a more underlying detection method, which can accurately identify all kinds of risky environments such as virtual frameworks, virtual machines, jailbreaks, ROOT, cloud phones, etc., and provide personalized flashing strategies.