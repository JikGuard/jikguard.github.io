---
layout: post
title: "How games detect speed-hack cheats"
date: 2025-10-16 16:30:00 +0800
categories: anti-cheat
tags: speed-hack  cheat engine  GameGuardian
---

Among the many risks of cheats faced by games, in addition to common cheating methods such as memory modification and injection, the black and gray industries also often use "speed-hack" to cheat.<!-- more -->

![315_21](/assets/res/2025/10231.jpg)  
Game security risk distribution chart

"Speed-hack" refers to changing the speed within the game. Games need to play frames in order to run, and calculating the time required to play each frame of animation requires calling C library functions to obtain the system time. For example:

gettimeofday; // Obtain the current exact time
clock_gettime; // Obtain the system time

The principle behind speed-hack cheats is to modify the obtained system time to speed up the flow of time within the game.

In addition, some speed-hack cheats can also achieve speed-hack by calling the time within the game engine. For example, by calling the UnityEngine_Time_set_timeScale function and passing in the desired speed-hack multiplier, a global speed-hack effect can be achieved.

Using speed-hack cheats can quickly collect resources and greatly shorten the game cultivation cycle. For placement and card games with cultivation elements, the proliferation of speed-hack cheats can lead to serious fairness issues.

In addition to speed-hack, these types of cheats can also have different effects depending on the gameplay. For example, music and parkour games can greatly reduce the difficulty of the game by slowing down the game speed, which can also lead to fairness issues and dissatisfaction among normal players.

![315_21](/assets/res/2025/10233.gif)  
Slowing down the speed reduces the difficulty of music games

In addition, JikGuard has observed that the trend of high-dimensional cheating with speed-hack cheats is becoming more and more significant. Some cheating users use Cheat Engine to modify mobile games running on PC emulators and sell their cheats. This type of high-dimensional cheating bypasses traditional detection methods and increases the difficulty of detection and investigation.

The implementation principle involves hooking the following three time-related functions:

timeGetTime (record the start time);
GetTickCount (obtain the current millisecond count);
QueryPerformanceCount (retrieve precise time)

The modifier records the start time of the process, obtains the address of the time function, and through hooking operations, redirects to a custom function. Within the custom function, it modifies the return value or output parameters. The specific calculation method is: current time + (current time - start time) * desired multiplier.

![315_21](/assets/res/2025/10234.png)  
Slowing down the speed reduces the difficulty of music games

The proliferation of speed-hack cheats destroys the fairness of the game and causes dissatisfaction among normal players. If not stopped in time, it will lead to serious consequences such as a shortened game life cycle and direct damage to the manufacturer's profits.

In response to the problem of speed-hack cheats in games, JikGuard has customised a special response strategy. This solution has been integrated into many popular games and has proven its excellent protection capabilities.

**Speed hack crush feature**

Using more low-level detection methods and extensive testing on actual machines, it can ignore any speed s and their variants. Once a speed hack is detected, the game will immediately crash.

**Anti-drive-level speed hack**

For high-dimensional cheating problems, JikGuard delves into the low-level game engine to perform in-depth detection of speed hack, obtain specific speed hack multiples, accurately identify drive-level and process-level speed hacks, and configure crash handling or account suspension measures on its own.

**Anti-cheat features**

In response to the risk of a series of cheat modifications in games, JikGuard has developed a behaviour detection solution with a 300+ dimension intelligent perception system that can effectively protect against all types of cheats and their variants.