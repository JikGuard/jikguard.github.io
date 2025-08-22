---
layout: post
title: "Unreal Engine Resource Encryption Solution"
date: 2025-08-21 16:30:00 +0800
categories: anti-cheat
tags: Unreal Engine  Resource  Encryption
---

According to data, Unreal Engine and Unity are the most widely used game engines in the current game market, with Unreal Engine holding a 28% market share, second only to Unity.<!-- more -->

![315_21](/assets/res/2025/uemarket.png)  

Compared to Unity, Unreal Engine's advantage lies in its powerful graphics and visual effects, which align with the game market's demand for high-quality, premium games. However, like Unity, Unreal Engine also faces serious security issues.

The main code logic of Unreal Engine is located in the EXE and resource files of the project. The resource extraction tool UnrealPakViewer can be used to analyse the game's pak files. By opening the files with the tool, various resources such as code, images, and videos can be extracted, greatly reducing the threshold for cheats and hacking.

![315_21](/assets/res/2025/UnrealPakViewer.png)  
UnrealPakViewer can view various resources and code after analysing the package

These resources are important assets of the game. Once leaked, they can lead to competition plagiarism, intellectual property damage, game content spoilers, game resource tampering, and the production and sale of cheats. How to effectively encrypt Unreal Engine resources, raise the threshold for hacking, and protect game resources has become a must for game manufacturers.

To strengthen the engine, two major challenges must be solved. The first is compatibility. Unreal 4 and Unreal 5 have many minor versions, which differ in performance, technology, and experience. Can the encryption solution be perfectly compatible?

The second is how to balance encryption strength and performance consumption. If encryption alone affects game performance and causes problems with game smoothness, it will be unacceptable to both game manufacturers and players.

In response to the above issues, JikGuard has developed a resource encryption protection solution for the Unreal Engine. This solution is perfectly compatible with all versions of UE4/UE5 and has a carefully constructed algorithm that effectively solves the problem of balancing encryption strength and performance consumption, ensuring high encryption strength while minimising performance consumption.

In addition, this solution has the following features:

■ The encryption solution only encrypts key core locations, with virtually no impact on game loading speed or running process, achieving imperceptibility.

■ High encryption strength, with customised obfuscation of the encryption and decryption algorithm, making it impossible for hackers to analyse the algorithm. The algorithm flowchart is shown below:

![315_21](/assets/res/2025/JikGuardflowchart.jpeg)  
JikGuard algorithm flowchart

■ Core file blocks are very small and do not vary with the size of the entire resource file. When tested on mainstream mobile devices, decrypting 300 resource files at once adds less than 10ms of additional decryption time. The encryption algorithm has undergone high-intensity custom obfuscation, carefully designed to balance complexity and efficiency, resulting in minimal runtime overhead.

■ The JikGuard reinforcement solution can effectively prevent unpacking and debugging. After reinforcement, the package cannot be extracted or analysed, and no clues are provided to hackers.

■ The JikGuard Unreal Engine resource encryption solution supports Android, iOS, and PC platforms, and supports online hot updates of resources.

■ It is very easy to use. You can encrypt the entire game resource with just one command line.