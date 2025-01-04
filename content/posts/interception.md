+++
date = '2023-12-14T14:23:04Z'
title = 'Interception (Progress Report 1)'
+++

In this post, We'll be covering the ways that we lifted the hood on EA/DICE's MEC server.


---

What exactly is a packet? A packet is simply a small chunk of data that gets sent to and from the MEC server.  
They're critical to internet communication and contain a lot of juicy data that we would like to get our hands on.



However, game companies aren't (completely) stupid and do try to protect the packets that get sent and recieved. They do this with encryption.


There are ways to crack encryption. However, Catalyst uses somewhat recent encryption methods so there aren't many exploits.  
We also can't try and bruteforce guess the decryption key as to do that in a reasonable amount of time would require a quantum computer and we unfortunately don't own one of those 😔


Okay then, so how did we manage to get past it? Well the answer is to do with the server software that EA/DICE use.   
EA/DICE build all of their game servers on top of their own "Blaze" software. This software has been used to build all EA/DICE game servers roughly since 2008 and is indeed the software that is used for the MEC server.


The issue with using the same software across lots of different online games is that it makes more people want to take a stab at attacking it. Think of all the possibilities! Well indeed, people did try to attack the Blaze server software and eventually were successful. Thus, the EA-MITM project was created.


EA-MITM attacks Blaze's ProtoSSL implementation and bypasses it to give us access to those sweet sweet unencrypted packets as they enter and exit our computer.


So that's where the story ends, right? Of course not! EA-MITM can only get us so far as Blaze data that's specific to Catalyst can only be revealed to us in binary, requiring them to be manually translated back to JSON, which is what we're working on right now with the [Catalyst-MITM](https://github.com/ploxxxy/catalyst-mitm) project 🙂


If you would like to find out more about Blaze, you can look at [this slideshow](https://www.slideshare.net/DICEStudio/battlelog-building-scalable-web-sites-with-tight-game-integration) made by DICE. Do keep in mind however that it is pretty old and outdated :p