---
title: "CNC Mill from Random Stuff"
author: "LandonBayer"
description: "Designing and building an extremely cheap CNC mill using as many random parts I have as possible to minimize cost"
created_at: "2025-05-25"
---

## **5/25/2025 Log 1: Initial Concepts**

I began by trying to figure out if this is even possible. To get my ideas flowing, I made a quick [Google doc](https://docs.google.com/document/d/1eDa18zaTmOcg4O9jXUVwCgunUB5oY8t1EJznX5E89rA/edit?usp=sharing ) with each part of the CNC as I thought of them and explained how I would fulfill that requirement: either with parts I have or links to a cheap option I could use.

I set up this repo, made an [Onshape document](https://cad.onshape.com/documents/fe491084e56455da2d5a649d/w/3d810b1fec2b376e1d8655d1/e/48dd41e2a4bf65c8f3ef253b?renderMode=0&uiState=683f1efbca486b0820284a82), and my research document above. I'm doing my best to fit into the $150 price tag to avoid the extra bar for $350 funding, but I may apply for it as necessary in the future. It would certainly be a huge upgrade to the machine, but the goal is a minimum functioning product for as little as possible. 

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

## **6/02/2025 Log 4: Finding Parts**

Most of this past week, I've been busy with the end of the school year, but I still took some time to get together all the parts I currently have and what needs to be purchased. To recap, I have two 400mm ball screws without nuts, four 350mm HGH15 linear rails, a RATTMMOTOR CBX 1605-200mm Z axis without a motor, and have since determined that the Arduino Mega with the Reprap RAMPS V1.4 sheild I have will not work as it is more suited for 3D printers and doesn't have the power to run a spindle. With these decisions, I am currently leaning toward [this](https://www.aliexpress.us/item/3256805662918330.html) control board, two of [these](https://www.aliexpress.us/item/3256807902881311.html) ball nuts, and finally [this](https://a.co/d/bSWRW8X) power supply and spindle combo, which I know will be compatible with the chosen control board.

Of these, my biggest concern is the spindle, as it is quite small and has a high risk of lacking rigidity. I really just want this to function, so even if it is very slow or only mills soft materials, I'll be happy and can expand upon it later. The total cost for these parts is around $105, leaving me only $45 left in my budget to purchase any other components like the stepper motors, structural hardware, limit switches, wiring, and other necessary components like shaft couplers, bolts, etc. Because of this, alongside the potential for a significantly more powerful machine by spending just slightly more, I am likely going to propose my project to the $350 budget range in order to make this viable.

## **6/03/2025 Log 5: Beginning Design**

Given that I'm starting with many parts on hand, I'm getting 3D models of them where possible. I was able to find a model for the [spindle](https://www.thingiverse.com/thing:4856147), [linear rails](https://grabcad.com/library/hgh15ca-hgr15r-1), and [ball screw nuts](https://grabcad.com/library/sfu1204-ballscrew-nut-22mm-1). I also whipped up a model for the lead screw in Onshape using a helix curve and a sweep toolpath with a 2.5mm circle and a 5mm pitch helix. Unfortunately, this mainly leaves the Z stage without a model, of which I may need to replicate myself. To minimize the amount of CAD work to be done, I only plan to model the block (nut) on the screw, since those mounting features are the only part of the assembly that I really care about, alongside the back of it which has rails with captive nuts for mounting. With these parts accounted for, I'll now move into more modeling of the machine, based around a few design constraints: the parts I have, using 8020 for structural pieces where possible, and doing any custom parts based on 1/4" plate as I have access to it in small quantities.

Separately, I've tentatively decided on [this](https://a.co/d/2pTGfU2) 3-pack of NEMA 17 stepper motors that should be compatible with the control board as well and are quite cheap at $26 for all three. I have added the associated [3D model](https://grabcad.com/library/nema-17-17he15-1504s-1) to my Onshape document as well.