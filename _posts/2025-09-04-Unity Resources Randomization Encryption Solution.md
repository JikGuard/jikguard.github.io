---
layout: post
title: "Unity Resources Randomization Encryption Solution"
date: 2025-09-04 16:30:00 +0800
categories: anti-cheat
tags: Unity  Resources  Encryption
---

Unity Resources are simple and easy to use, making them ideal for rapid prototype development. Currently, some games still use this type of resource instead of Assetbundle.<!-- more -->

After packaging, Unity Resources files are stored in the assets/bin/Data path with names based on their hash values, as shown in the figure below:

![315_21](/assets/res/2025/090501.png)  

JikGuard conducted an in-depth analysis of the Unity Resources resource loading principle, found the core points of encryption and decryption, and constructed a solution and algorithm for random encryption of resources.

The original Resources file is shown in the binary below, where you can see a lot of resource version information:

![315_21](/assets/res/2025/090502.png)  

The figure below shows the encrypted resources, where no information can be seen, and the contents of the file are completely different after each encryption.

![315_21](/assets/res/2025/090503.png)  

Using AssetStudio to parse the resources and compare the results before and after encryption.

First, consider an unencrypted resource. Load the resource using AssetStudio's "Load File" feature, and the parsing results after loading are shown in the figure below:

![315_21](/assets/res/2025/090504.png)  

![315_21](/assets/res/2025/090505.png)  

As can be seen, AssetStudio has parsed out a lot of information. The figure below shows the results of loading the encrypted Resources file using AssetStudio:

![315_21](/assets/res/2025/090506.png)  
AssetStudio cannot recognise it.

This Resources randomisation encryption supports Android/iOS/Windows platforms. Combined with previously implemented AssetBundle encryption, global metadata encryption, and SO shelling, JikGuard can perform randomisation encryption on nearly all game-related files within a Unity game package.