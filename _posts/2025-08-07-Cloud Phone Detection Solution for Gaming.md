---
layout: post
title: "Cloud Phone Detection Solution for Gaming"
date: 2025-08-076:30:00 +0800
categories: anti-cheat
tags: Cloud Phone  Detection
---

Risky gaming environments are environments that are independent of the original device or disrupt the original system of the device. Common risky environments for gaming are: cloud phone, virtual machine, virtual framework, iOS jailbreak, Android device rooting, etc.<!-- more -->  

Risky environments can provide high-level device permissions needed for game cheats and hacks, and when the game is in these risky environments, the game will have greater security risks.

In this paper, we will analyse the implementation principle and detection difficulties of cloud phone and provide detection solutions through case studies.

The implementation principle of cloud phone is to rely on the public cloud and ARM virtualisation technology to provide users with an Android instance in the cloud, and by means of video streaming, users can remotely control the cloud phone in real time, and ultimately realise the cloud operation of Android native APP and mobile games.

![315_21](/assets/res/2025/commoncloudphones.png)  
Several common cloud phones on the market

Users can upload the applications on their mobile phones to the cloud, and the computation, storage and other capabilities that originally need to be provided by the mobile phone are instead provided by servers in the cloud. In this way, the physical device can get rid of the hardware and achieve features such as batch simulation, creation of devices, and synchronised control.

![315_21](/assets/res/2025/cloudphone.png)  
cloud phone batch simulation device

In addition, based on the development of ARM server virtualisation technology, cloud phone simulation of the device performance compared to the virtual machine, virtual framework is higher, and can even exceed the real machine; and can be based on cloud technology for elastic expansion, upgrading, flexible migration.

With the cloud phone batch multi-open, elastic expansion, flexible migration, high performance, low cost and other ‘advantages’, the studio to achieve a low-cost, fast, batch raising account, a short period of time will have a serious impact on the game economic ecology.

![315_21](/assets/res/2025/cloudphonescost.png)  
The cost of cloud phones is very low

Cloud phones are widely used by the game black and grey industry, causing problems for many games. How to effectively and accurately detect and identify cloud phones has become a major pain point for the industry. It has been observed that cloud phones have the following detection difficulties:

Cloud phone technology development is mature, for the ARM same platform architecture, compared with other risky environments, cloud phone simulation is high and difficult to detect.

By using plug-ins such as Magisk in cloud phones, it is possible to hide cheats from games to avoid detection. Some cloud phones come with individual application rooting features, which can enable rooting for cheats individually without opening the game, so as to avoid detection.

![315_21](/assets/res/2025/cloudphonesroot.png)  
Some cloud phones can enable rooting for individual applications

JikGuard has tailored a special strategy to deal with the risky environments faced by games such as cloud phones, and the solution has been connected to a number of popular games and proved to have excellent protection capabilities.
 
**curity Risk Environment Detection**
Unlike other products on the market, JikGuard's reinforcement adopts a more fundamental detection method to accurately distinguish the operating environment of the game, identifying various risky environments such as cloud phones, virtual machines, virtual frameworks, jailbreaks, ROOT, etc., and providing personalised crushing strategies.