---
layout: post
title: "JikGuard Exclusive Import-Free SO Packing Solution"
date: 2025-07-16 16:30:00 +0800
categories: anti-cheat
tags: SO  Encryption  JikGuard
---

Import function is a very important clue in reverse analysis of Android SO module, the system api used by SO can be seen in the import function table.<!-- more -->  

![315_21](/assets/res/2025/SOused.png)  
The import table of SO used by a game protection SDK

The import function will provide a lot of key information to the hacker, which helps a lot in game hacking. Since the import table is so helpful for hack analysis, is it possible to remove the import table or not use the import function?

A spatial C code project, which does not call any API inside the code, also has about 10 import functions after compilation, because the runtime libraries automatically introduced by the compiler also need to rely on the system API.

Would it be OK if the import table is directly removed? Without the import table, SO loading will report an error because it can't find the import table, and the application can't run normally.

So is there any technical way to remove the import table and at the same time allow SO to load normally?

**Here are a few difficult technical problems:**

1. There is no import function, can not call any system api, but the shelled SO will call a lot of api, these api address how to get in the condition of not using the system api, like dlsym function is not imported, can not be used.

2. Although theoretically you can parse all the function addresses from the system module by yourself, in reality, some functions in Android 4.4 to 7.0 are not exported in the system module. In these systems, some functions are not exported from any system module.

3. For the same api name, there may be more than one system module exported, how to determine which one is the right one, if you use the wrong one, it will cause the process to crash.

4. Compatible simulator problem. Mainstream module ware are running under x86 CPU, and its compatibility with arm instruction set uses a lot of hard-coding-like means, which will have unconventional processing for specific functions.

This is especially complicated when running non-x86 modules, where there are 2 sets of instruction set modules in the process at the same time. If imported functions are present, all this work is done by the system; without imported functions, these system rules need to be analysed without any documentation.

Any one of these technical problems can't lead to a commercially available shelled product. It is the difficulty of these problems that no other manufacturer has been able to make the implementation of shelling without import function.

JikGuard has conducted in-depth research, perfectly solved all the above problems, and developed the industry-exclusive SO shelling without import function, which has been adopted by many games and operated stably online.

The effect of SO shelling without import function, there is no function under Imports.

![315_21](/assets/res/2025/SOshelled.png)  
The effect of SO shelled without import function

In addition to the implementation of no import function, JikGuard SO shelling also provides the following security features:

1. Export function cleaning and encryption
The export function will be cleaned or encrypted. The exported functions can be cleaned or encrypted, leaving no clues for hackers to analyse the exported functions.

2. virtualise elf structure
Virtualise the structure of SO, so that the original structure of SO can be hacked and reconstructed, and the original SO can not be restored, so it can not be decloaked.

3. system call takeover
system functions can be monitored by the way of dynamic hook call parameters, JikGuard SO shelling to take over these system functions, so that the dynamic hook is invalid.

4. Code encryption
SO shelling is the cornerstone of hand game hardening, related to the protection strength of hand game hardening, compatibility, startup time and other security core indicators. JikGuard focuses on Game Hardening and anti-cheats, with a set of mature and perfect encryption solution.