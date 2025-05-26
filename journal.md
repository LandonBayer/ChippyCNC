---
title: "CNC Mill from Random Stuff"
author: "LandonBayer"
description: "Designing and building an extremely cheap CNC mill using as many random parts I have as possible to minimize cost"
created_at: "2025-05-25"
---

## **5/25/2025 Log 1: Initial Concepts**

I began by trying to figure out if this is even possible. To get my ideas flowing, I made a quick [Google doc](https://docs.google.com/document/d/1eDa18zaTmOcg4O9jXUVwCgunUB5oY8t1EJznX5E89rA/edit?usp=sharing ) with each part of the CNC as I thought of them and explained how I would fulfill that requirement: either with parts I have or links to a cheap option I could use.

I set up this repo, made an Onshape document, and my research document above. I'm doing my best to fit into the $150 price tag to avoid the extra bar for $350 funding, but I may apply for it as necessary in the future. It would certainly be a huge upgrade to the machine, but the goal is a minimum functioning product for as little as possible. 

I'm looking to follow a basic CNC configuration with the spindle moving in XZ and the bed in Y, much like a bedslinger 3D printer or a 3018 style CNC.  

Time Spent: 45 Minutes (mostly research)

## **5/25/2025 Log 2: Ideation**

Some parts are not in my house at this exact moment so I need to wait a few days to go and grab them. In the meantime, I'll try to design most of the printer and be able to swap out the CAD models as I get the real ones and create/find models for them.

It is also worth noting that I have access to an Omio CNC router through my robotics team, which will enable me to make custom parts in aluminum or polycarbonate as I please (though I may have to buy stock as part of my budget). I also recently set up a 4th axis on it, so I can even do some more complex parts too.

Here are some sources of inspiration:

![Cubiko CNC](https://www.sainsmart.com/cdn/shop/files/Cubiko-12001.png?v=1741315636)
![3018 CNC](https://www.sainsmart.com/cdn/shop/files/4ee0482982cfa89bb4d1cff3333a55e6-_1.png?v=1694156155)

Time Spent: 15 Minutes

## **5/26/2025 Log 3: More Research**

I can't get some of the parts that I need until tomorrow, so I'm mostly holding off on CAD work until then to avoid extra work. In the meantime, I'm continuing to look into how I'm going to put this all together. I'm currently examining [GRBL-Mega](https://github.com/gnea/grbl-Mega), since I have an Arduino Mega with some sort of motor driver hat that hopefully is compatible. I also have a random Raspberry Pi 3B that I could use as a standalone computer for the CNC (just so it doesn't have to sit next to my real computer).
I'm doing as much pre-requisitve research as possible while I wait for those parts and so I don't waste time doing something that isn't possible (or I know where to put more of my budget). So far, the main budget items I have planned for are a spindle (cheapest one I could find is $27, the 3018 type spindle with an ER11 collet), a fixture table that I will likely make myself on the Omio CNC, stepper motors, and possibly a second ball screw of the same model I already have (~60, comes with a motor). Again, I'm hoping to stay under $150 but I may expand beyond that to accomodate any necessary parts for the functioning of the machine, or add more features like probing, an enclosure, or a better spindle.

Time spent: 45 Minutes
