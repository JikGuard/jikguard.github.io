---
layout: post
title: "Unity Resources Randomized Encryption Solution"
date: 2025-07-24 16:30:00 +0800
categories: anti-cheat
tags: Unity  Resources  global metadata
---

Compared to Assetbundle, Unity Resources resources are great for rapid prototype development because of their simplicity and ease of use, and there are still a lot of games that use this type of resources.<!-- more -->  

Unity Resources resource files are packaged and exist as a file named with a hash value under assets/bin/Data path, as shown in the following figure:

![315_21](/assets/res/2025/72401.png)  

JikGuard has conducted an in-depth analysis of the Unity Resources resource loading principle, found the core point of encryption and decryption, and constructed a solution and algorithm for random encryption of resources.

The original Resources file, in binary, is shown below, and you can see a lot of information about the version of the resources:

![315_21](/assets/res/2025/72402.png)  

After JikGuard encrypted resources, no information can be seen, and the content of the file is completely different after each encryption, as shown in the figure below:

![315_21](/assets/res/2025/72403.png)  

Then use AssetStudio to parse the resources and compare the effect before and after encryption.

First of all, look at the unencrypted resource file, use AssetStudio click Load file to load the resource, after loading the parsing results are shown in the following two charts:

![315_21](/assets/res/2025/72404.png)  

![315_21](/assets/res/2025/72405.png)  

We can see that AssetStudio parses out a lot of information.
 
The following figure shows the result of using AssetStudio to load the encrypted Resources resource file with JikGuard:

![315_21](/assets/res/2025/72406.png)  

In addition, JikGuard also provides high-strength assetbundle encryption, global metadata encryption, SO shelling and other features, can be almost all the files related to the game in the Unity game package to do randomised encryption processing, support for Android/iOS/Windows multi-platform.