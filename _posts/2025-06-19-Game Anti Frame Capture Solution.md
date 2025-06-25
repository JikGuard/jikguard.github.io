---
layout: post
title: "Game Anti Frame Capture Solution"
date: 2025-06-19 16:30:00 +0800
categories: anti-cheat
tags: Frame Capture
---

For a game, the art performance that the players pay attention to at the first sight will largely determine whether the players will be interested in the game and continue to understand the game content. The importance of game art is self-evident if you want to occupy a place in the fiercely competitive market.<!-- more -->  

Black Myth: Wukong, which has won numerous awards, has impressed countless players with its art design and stunning game quality during its first exposure, and the heat continues to this day.

![315_21](/assets/res/2025/BlackMyth.jpg)  
Black Myth: Wukong game original drawing

From the perspective of game security, the protection of game art resources is also an extremely important part. Leakage and theft of game art resources occur from time to time, and they can be quickly copied and duplicated by competitors, causing serious operational accidents and shortening the life cycle of the game.

Game frame capture is a malicious means of stealing game art resources commonly seen in end-game, which refers to the operation of capturing and saving a certain frame or multiple consecutive frames of the game screen through frame capture tools during the game process. These captured frames can be used to analyze game art materials, rendering techniques, etc. Common frame capture tools include RenderDoc, PIX, NVIDIA Nsight, Intel GPA.

![315_21](/assets/res/2025/RenderDoc.png)  
Frame capture tool RenderDoc

RenderDoc is a common end-game frame capture tool, its principle is through the injection, in the game engine Graphics API (the underlying drawing function) before the call, in the target process mount renderdoc.dll, in the process of calling the Graphics API, the record of all the parameters of the API call, so as to complete the record of each frame data, to facilitate the subsequent analysis operations. This will record the data of each frame and facilitate the subsequent analysis.

![315_21](/assets/res/2025/RenderDoc1.png)  
RenderDoc can view the rendering data after acquiring the game's art resources.

After recording, RenderDoc can analyze the rendering data of the game screen through the interface features, such as the use of art materials, data of different rendering stages, shader data, etc. If this information is leaked, it means that the rendering data of the game screen will be analyzed by RenderDoc. Once this information is leaked, it means that the game art resources may be stolen and the rendering technology may be stolen.

In addition to RenderDoc, there are also PIX, NVIDIA Nsight, Intel GPA and other end-game frame capture tools, all of which have the possibility of maliciously stealing game art resources. Generally, these frame capture tools will use injection means, which can detect the injection module, but some malicious users will modify the module features to hide them, which puts a higher demand on the anti-frame capture features of game security products.

JikGuard has developed a set of mature and perfect solutions for game security problems caused by game frame capture tools, which can effectively prevent game resources from being stolen and leaked, and avoid game rendering technology from being maliciously analyzed. At present, the solution has been connected to a number of popular games and verified the excellent protection ability.
 
**Anti Frame Capture Features**
Even if malicious users hide, JikGuard Game Hardening solution can accurately identify frame capture tools such as RenderDoc, PIX, NVIDIA Nsight, Intel GPA, etc., which can effectively prevent game resources from being misappropriated and leaked, and avoid game rendering technology from being maliciously analyzed.

In addition, JikGuard Hardening solution is specially optimized for the frame capture operation of some Game Hardening software, avoiding the phenomenon of false alarms through multi-dimensional data judgment.