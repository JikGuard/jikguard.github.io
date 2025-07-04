---
layout: post
title: "Mobile Game Anti-Frame Capture Solution"
date: 2025-07-03 16:30:00 +0800
categories: anti-cheat
tags: Anti-Frame Capture  Adreno profiler  RenderDoc
---

According to the statistics, game R&D cost accounts for about 15%-35% of the revenue, and the proportion of art resources in R&D cost reaches 50-70%. If you want to occupy a place in the fierce market competition, the importance of game art is self-evident.<!-- more -->  

From the perspective of game security, the protection of game art resources is also an extremely important part. Leakage and theft of game art resources occur from time to time, which can be quickly copied and reproduced by competitors, causing serious operational accidents.

Game frame capture is a malicious means of stealing game art resources. During the game process, malicious users will capture and save one or more consecutive frames of the game screen through frame capture tools, and these captured frames can be used to analyse game art materials, rendering techniques and so on.

Based on different operating systems, a large number of frame capture tools have appeared in mobile games. For example, Frame Capture is commonly used in iOS; Adreno Profiler is commonly used in Android.

![315_21](/assets/res/2025/FrameCapture3.png)  
Frame Capture is a frame capture tool to analyse mobile games

Adreno Profiler is a performance analysis and frame debugging tool for graphics and GPU technology applications running on Qualcomm Snapdragon processors, supporting analysis and debugging of OpenGL ES, OPenCL and DirextX.

Thanks to Adreno Profiler's powerful ease-of-use, it is possible to grab any application for analysis, debugging and frame capture to view texture, programe, shader and other resources. In addition to being used by developers for analysis and tuning, it is also used by malicious analysts.

![315_21](/assets/res/2025/AdrenoProfiler3.png)  
Adreno Profiler can view various data after acquiring art resources

After using Adreno Profiler for frame capture analysis, you can use the interface features to analyse the rendering data of the game screen and package the resources for export. For example, the usage of art materials, data of different stages of rendering, shader data, and so on. Once this information is leaked, it also means that there is a possibility of game art resources being stolen and rendering technology being stolen.

In addition, some malicious users will connect their mobile devices to PC and use PC frame capture tools and Android emulators for frame capture and analysis, commonly used tools include: RenderDoc, NVIDIA Nsight, Intel GPA and so on.

![315_21](/assets/res/2025/RenderDoc3.png)  
RenderDoc frame capture tool for hand game analysis

In the daily confrontation, we found that this kind of frame capture tool will use the injection means, can be detected on the injection module, but some malicious users will modify the module features to hide, which has higher requirements for the game security products of the anti-frame capture features.

JikGuard has developed a mature and perfect solution for game security problems caused by game frame capture tools, which can effectively prevent game resources from being stolen and leaked, and avoid game rendering technology from being analysed maliciously. Currently, the solution has been connected to a number of popular games and has proved its excellent protection ability.

**Anti-frame capture Features**

Even if a malicious user hides, JikGuard Game Hardening solution can accurately identify frame capture tools such as Adreno Profiler, Frame Capture, RenderDoc, Intel GPA, etc., which can effectively prevent game resources from being stolen and leaked, and prevent game rendering technology from being maliciously analysed.

In addition, the JikGuard solution is specially optimised for frame capture operations in some live broadcasting software, avoiding false positives through multi-dimensional data judgement.