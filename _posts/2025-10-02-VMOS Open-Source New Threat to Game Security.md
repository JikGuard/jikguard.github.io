---
layout: post
title: "VMOS Open-Source New Threat to Game Security"
date: 2025-09-25 16:30:00 +0800
categories: anti-cheat
tags: VMOS  Virtual machines  Game Security
---

Virtual machines can simulate multiple operating systems on a single device, solving device limitations in different scenarios and saving on the cost of purchasing software and hardware equipment, providing considerable convenience for work and life, and gaining widespread application.<!-- more -->

However, virtual machine technology has been exploited by the black and gray industry of gaming to run cheats. The system simulated by the virtual machine can provide ROOT permissions for modifiers and can also run multiple instances. Running games in a virtual machine environment poses considerable security risks.

![315_21](/assets/res/2025/vmosvm.png)  

The official of the mainstream virtual machine VOMS announced on Github that it would be officially open-sourced, releasing the software source code and deployment methods. This move means that the field of game security will face new challenges.

![315_21](/assets/res/2025/vmosopen.png)  

Open source means open source code, allowing users to personalise and modify the software, which will lead to more innovation and enhanced features. This move is beneficial to the black and gray industry of gaming.

It means that cheat authors can embed cheat permissions directly into the low-level of the virtual machine and can also disguise the cheat process as a system application to evade detection. For example, JikGuard detects some cheat paths as follows:

/system/priv-app/com.xxx.yyyy/base.apk

Once a customised virtual machine can evade detection, it will quickly spread to various game scenarios, which will have a huge impact on game security.

JikGuard has customized a special response strategy for game security risk environments. This solution has been integrated into many popular games and has proven its excellent protection capabilities.
 
**Security risk environment detection**

Using more low-level detection methods, it accurately distinguishes the game running environment, identifies various risk environments such as jailbreaking, ROOT, virtual machines, virtual frameworks, and cloud phones, and provides customised crush strategies.