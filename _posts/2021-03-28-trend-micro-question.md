---
title: ISSessions CTF - Trend Micro - Who Builds Their Own Protocols!?
author: Pocholo Arangote
---

Trend Micro - Who Builds Their Own Protocols!?

File: iperius.pcap


General Description
Alright, this challenge was hard. You're given a .pcap, and it has your usual TCP ACKS, TLS Traffic, IPv4 traffic and some UDP mixed in there. The juicy bits (read: flag) are all caught up in the TLS traffic, but that's encrypted, so we'll leave it for now. Our primary goal then, is to somehow find a way to decrypt the TLS traffic. The TCP packets don't have anything too useful, but the UDP packets have a sizable amount of data. 

![[Screenshot (164) 2.png]]
*Figure 1: Some TLS and TCP traffic* 

![[Screenshot (163).png]]
*Figure 2: Here is some IPv4, and some UDP traffic. The UDP traffic is the key!*

To see what the UDP packets are transporting, we check the UDP stream.

![[Screenshot (166).png]]
*Figure 3: How to follow the UDP stream. *


We get an odd looking file - this file has CAPITALWORDLETTERS followed by a whole lot of zeros. It repeats, until you hit a   

CLIENT\_HANDSHAKE\_TRAFFIC\_SECRET
  

SERVER\_HANDSHAKE\_TRAFFIC\_SECRET

Then the whole BIGCAPITALLETTERSOFDOOM followed by zeros comes back.
You can actually save this as a .txt file. This file is crucial to solving the problem.

![[Screenshot (167).png]]
*Figure 4: The weird file, that we save for later.*

You get a .txt file from UDP traffic, I called it premaster1.txt, call it what you want.

Now, Wireshark needs a Pre-Master-Secret(PMS) log file, to decrypt TLS traffic. Luckily, we have that - we just found that! In Wireshark: Select a TLS packet, right-click it. Then, select protocol preferences, Transport Layer Security, then open Transport Layer Security preferences.
![[Screenshot (168).png]]
*Figure 5: How to open the Transport Layer Security Preferences menu.*
At the very bottom, you should see a Pre-Master-Secret log filename box, where you should enter the location of the text file you extracted.

![[Screenshot (169).png]]
*Figure 6: The menu where you enter the PMS file.*

This will allow you to read TLS traffic. 

![[Screenshot (175).png]]
*Figure 7: Yes! Now we can actually read some TLS traffic.*

Now, we can finally figure out the flag. The file containing the flag is in one of the HTTP2 packets. Hint: it has DATA in the info tab of Wireshark.

![[Screenshot (173).png]]
*Figure 8: The file containing the flag, as Wireshark shows it.*

However, this file is encrypted. 

![[Screenshot (171).png]]
*Figure 9: Oh no! What are we to do? There's a password, and we don't know it!*

Luckily, the people who were sending the file also sent the password for the file. It's located in one of the Websockets. These Websockets are where you can glimpse the conversation between two figures: hippo and raven. 

![[Screenshot (172).png]]
*Figure 10: This is what the Websockets look like. They're the same color as the TLS, because TLS was encrypting them.*


Once you have the password, all you need to do is open up your .png reward, and obtain the flag. 
