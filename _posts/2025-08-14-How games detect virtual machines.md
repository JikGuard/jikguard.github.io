---
layout: post
title: "How games detect virtual machines"
date: 2025-08-14 16:30:00 +0800
categories: anti-cheat
tags: virtual machines  root  Android
---

In recent years, the game market has been developing at a high speed, and along with it, there are also game black and grey industry that seek to make profits. Driven by profit, the scale of game black and grey industry is expanding rapidly, and the attack trend shows the characteristics of diversified angles.<!-- more --> 

Under this trend, the detection coverage of game security protection is particularly important. If the game protection is missed in a certain part of the inspection, in a short period of time, the game cheats will complete the iteration, which will lead to the failure of the game security protection. 

![315_21](/assets/res/2025/gameattack.png)  
Common game black and grey industry attack methods

In the process of high-intensity game security confrontation, some general-purpose tools are also used by the game black grey industry, which becomes the tool for running cheats.

For example, the common virtual machine technology can simulate multiple Android systems on a mobile phone, and the simulated systems run independently and can be flexibly configured as needed to run multiple applications at the same time.

![315_21](/assets/res/2025/virtualmachines.png)  
Some of the common virtual machines on the market

Virtual machines are widely used by black and grey industry, game cheats can run games in virtual machines to achieve multi-instance operations; in addition, virtual machines simulated Android system can also provide ROOT permissions, providing an environment for the operation of cheats. When the game is detected running in the virtual machine environment, in fact, there is a greater security risks.

![315_21](/assets/res/2025/vmos.jpg)  
vmos virtual machine

Virtual machine technology is widely used by the game black and grey industry, causing problems for many games. How to effectively and accurately detect and identify virtual machines has become a major pain point for the industry, and virtual machines have the following detection difficulties:

The development of virtual machine technology is mature, and the management tools and ecosystem are perfect, compared with other risky environments, the detection of virtual machines is more difficult.

In the virtual machine with the use of Magisk and other plug-ins, you can achieve the game to hide the process of cheats to avoid detection.

![315_21](/assets/res/2025/MagiskHide.png)  

JikGuard has developed a customised solution for virtual machines and other risky environments faced by games. The solution has been applied to a number of popular games and has proven to be an excellent protection solution.
 
**Risky Environment Detection**

Unlike other products on the market, JikGuard uses a lower-level detection method to accurately differentiate between the operating environments of games, identifying various risky environments such as virtual machines, virtual frameworks, jailbreaks, ROOT, cloud phones, etc., and providing personalised crush strategies.