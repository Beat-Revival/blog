+++
date = '2024-02-25'
title = "Progress Report 2"
+++

Welcome to our second progress report. This post will cover everything we've done since our break.

Most of our time was spent working on TDF decryption. TDF is the proprietary file format that Catalyst uses for its packet encryption.  
When we captured packets (which you can read about in our last post), we captured the TDF encrypted packets, meaning they have to be decrypted manually.

[After a lot of hard work](https://github.com/ploxxxy/node-tdf), we've managed to get to a point where we can decrypt and encrypt some of the basic server functions in real-time and we've successfully managed to get the game to communicate with the server.

We've also been working on building the Catalyst API emulator and the Blaze server emulator (If you want to learn more about Blaze, check our previous post). They currently aren't very functional, but we have the groundwork of them which we're starting to build on.

**Now, this doesn't mean that we're close to finishing the project.** However, we now have the framework to build the rest of the project on. Most of the work from now on will be decrypting/deobfuscating functions and implementing them.
