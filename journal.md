---
title: "Chippy CNC"
author: "LandonBayer"
description: "Designing and building a cheap CNC mill using as many random parts I have as possible to minimize cost"
created_at: "2025-05-25"
---
Total time spent: 20 hours

## **5/25/2025 Log 1: Initial Concepts**

I began by trying to figure out if this is even possible. To get my ideas flowing, I made a quick [Google doc](https://docs.google.com/document/d/1eDa18zaTmOcg4O9jXUVwCgunUB5oY8t1EJznX5E89rA/edit?usp=sharing ) with each part of the CNC as I thought of them and explained how I would fulfill that requirement: either with parts I have or links to a cheap option I could use.

I set up this repo, made an [Onshape document](https://cad.onshape.com/documents/fe491084e56455da2d5a649d/w/3d810b1fec2b376e1d8655d1/e/48dd41e2a4bf65c8f3ef253b), and my research document above. I'm doing my best to fit into the $150 price tag to avoid the extra bar for $350 funding, but I may apply for it as necessary in the future. It would certainly be a huge upgrade to the machine, but the goal is a minimum functioning product for as little as possible. 

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

![parts I have][parts]

[parts]: Journal-Entries/parts.jpg

Of these, my biggest concern is the spindle, as it is quite small and has a high risk of lacking rigidity. I really just want this to function, so even if it is very slow or only mills soft materials, I'll be happy and can expand upon it later. The total cost for these parts is around $105, leaving me only $45 left in my budget to purchase any other components like the stepper motors, structural hardware, limit switches, wiring, and other necessary components like shaft couplers, bolts, etc. Because of this, alongside the potential for a significantly more powerful machine by spending just slightly more, I am likely going to propose my project to the $350 budget range in order to make this viable.

Time spent: 1 hour (over the week)

## **6/03/2025 Log 5: Beginning Design**

Given that I'm starting with many parts on hand, I'm getting 3D models of them where possible. I was able to find a model for the [spindle](https://www.thingiverse.com/thing:4856147), [linear rails](https://grabcad.com/library/hgh15ca-hgr15r-1), and [ball screw nuts](https://grabcad.com/library/sfu1204-ballscrew-nut-22mm-1). I also whipped up a model for the lead screw in Onshape using a helix curve and a sweep toolpath with a 2.5mm circle and a 5mm pitch helix. Unfortunately, this mainly leaves the Z stage without a model, of which I may need to replicate myself. To minimize the amount of CAD work to be done, I only plan to model the block (nut) on the screw, since those mounting features are the only part of the assembly that I really care about, alongside the back of it which has rails with captive nuts for mounting. With these parts accounted for, I'll now move into more modeling of the machine, based around a few design constraints: the parts I have, using 8020 for structural pieces where possible, and doing any custom parts based on 1/4" plate as I have access to it in small quantities.

Separately, I've tentatively decided on [this](https://a.co/d/2pTGfU2) 3-pack of NEMA 17 stepper motors that should be compatible with the control board as well and are quite cheap at $26 for all three. I have added the associated [3D model](https://grabcad.com/library/nema-17-17he15-1504s-1) to my Onshape document as well.

Time spent: 1 hour

## **6/04/2025 Log 6: Base sketches**

I did out some sketches in Onshape, making this as parametric as possible. I'm using some variables to name certain values like the length of my rails, ball screws, and the gap between the table and the spindle (Z-gap). I'm taking the time to think through these sizes and constraints to ensure they will propogate down correctly later on if I need to change things. I also made a small subassembly for the linear rails with limited slider mates on the blocks.

![onshape][def]

[def]: Journal-Entries/onsh.png

Time spent: 30 minutes

## **6/16/2025 Log 7: More Onshape**

I worked out the back of the mill, which is the X axis and will hold the Z axis on it. I'm starting very simple, with some 8020 extrusions going around and some 2x1 ones at the bottom to give me some space for the rails and ball screw on the Y axis. My main issue with this was that the 8020 featurescript in Onshape is really difficult to use, as it generates facing straight up all the time. I spent quite a while trying to figure out a workaround and eventually settled on a not-ideal but somewhat parametric way to get the lengths set in the part studio.

![cncmillvertical][vert]

[vert]: Journal-Entries/cncmillvertical.png

Time spent: 1.5 hours

## **6/17/2025 Log 8: Onshape Struggles Continue**

As I build out the rest of the machine in Onshape, I am beginning to really hate the 8020 featurescript and even using it as a part in CAD. Since it has rounded corners, I cannot add mate connectors to the corners exactly and instead have to use some strange face mates to connect the pieces. After discussing these issues with another Hack Club member, he recommended I simply model the 8020 as a solid 1x1 inch box, which I will convert now before the design gets too large. This means I will basically have to re-do both the part studio and assembly, but it will make things much easier going forward. You can also see some corner braces and attachment methods being added, though they aren't completely cadded in yet. I have some small 1x1 corner brackets, large 2x2 brackets for the inside of the base, and square pieces that are meant to attach three tapped 8020 extrusions in the corners (more details to come). Let's get to the conversion!

Before pic:

![cncmill8020][eightytwenty]

[eightytwenty]: Journal-Entries/cncmill8020.png

Time spent: 1 hour

## **6/18/2025 Log 9: Onshape grind + Rethinking the machine**

I'd like to touch on that rethinking part first: I was initially trying to hit the $150 price point Hack Club offers, but after reviewing the guidelines more closely, I believe this is likely to fall into the advanced $350 category. For this reason, I'm looking at possible changes to my spindle (easiest) or even to the control board, drivers and motors (harder). The spindle is a straightforward upgrade with the same controller up to a 500W spindle, which makes it an ideal easy solution. However, the main limiting factor at this point would be the stepper motors I'm using to drive the whole machine, which are limited to 2 amps of maximum current based on the A4988 drivers the control board has. If I choose a different control board without integrated drivers, I could increase the power of those drivers up to 4A or higher, giving me room to put on larger stepper motors that will make the machine run much better. I will be continuing to consider this option as I move forward with the design, as it should not be heavily reliant on this choice.

As for Onshape, now comes the time to re-do all the 8020 extrusions to be simple boxes for ease of design. Here is what it looks like after:

![cncmillbox][box]

[box]: Journal-Entries/cncmillbox.png

Naturally, after doing all of this, I began rethinking my work from the start. I'm now realizing it could be easier for the operator (myself) to use if the bed is completely stationary and the spindle moves in XYZ, much like a typical cnc router. I will also be considering this as I continue working, and might create a branch in Onshape to test this out if it appears to be desirable. I am still unsure how this would complicate or simplify my ability to move each axis with the ball screws, which I am yet to figure out exactly in either design. I may replace some 8020 sections with 1/4" sheet aluminum milled to my specifications (on the router I have access to). This is likely to be more expensive, but may produce better end results.

Time spent: 1.75 hours

## **6/19/2025 Log 10: Big progress**

Today I really locked in on cad and got a lot done, fixing many issues and continuing the design phase. After much thought, I stuck with the bedslinger style of kinematics (XZ on the head, Y on the bed), but realized that the XZ section must be centered on the mill to reach all of the millable area. I also replaced the front and back of the machine with 1/4" aluminum plate that I will mill out, simplifying the design by allowing me to easily mount the motor that drives the Y axis (pictured in the grey motor below). That said, I'll probably re-do it again to have a smaller mounting plate because that one is massive and impractical.

I continued at sorting out the core kinematics, first by adding some 40-1620 8020 extrusion as a bed to the printer. My hope is that this will make it easy to clamp parts and add a spoilboard on top. The main downside is cost, at a whopping $60 for the build plate pictured. I will keep in consideration another spoilboard mounting solution as well as possibly some way to add a machining vice for larger 3D milling operations (possibly a way to detach the bed and add a vice directly to the linear rails?)

As you can see, I got around to creating a 3D model of my [Z axis](https://a.co/d/2vU4E41) to continue figuring out my placement for the spindle motor and X axis power. In an ideal world, the X axis ball screw could run between the rails, just behind the Z axis assembly to increase rigidity. Doing so may require some kind of custom motor mounting plate, which is certainly fine within the scope of this project.

![cncmillprogress][prog]

[prog]: Journal-Entries/cncmillprogress.png

Time spent: 3 hours (honestly much more but let's just count 3)

## **6/20/2025 Log 11: Keeping it Moving**

I redid the front and back again to use smaller milled plates, though I may even make the back a single piece of extrusion as it isn't entirely needed. I got around to creating models for the spindle and the clamp it comes with, which will need some kind of adaptor plate to the Z axis. I'm getting relatively close to a point where I can begin ordering parts (aka submitting to HC), so I'm super excited for that! The major tasks that remain are the X axis power, creating various mounting plates and adaptors, and sorting out smaller details like modeling in bolts where needed, adding shaft collars to the motors to connect the ball screws, etc. I already have most of my plans sorted out for the controls and such, which aren't currently modeled as it doesn't really make a functional difference just yet. Here's the progress photo for today:

![cncmillalmostdone][almost]

[almost]: Journal-Entries/cncmillalmostdone.png

Time spent: 1.5 hours

## **6/27/2025 Log 12: Tidying Up Loose Ends**

This log will cover the small pieces I've been doing over the course of that last week (I've been busy so it's all clumped together). First, I found that I can buy ball nut housings for quite cheap, giving me a strong aluminum connecting piece for X and Y power. However, the threads they come with don't match perfectly with my other parts so some adaptor plates were made too. Here's one of them on the X axis power:

![cncmillxpowerplate][powerplatex]

[powerplatex]: Journal-Entries/cncmillxpowerplate.png

The pockets are countersinks for the bolts going into the block, while the holes above and below are for the slots on the Z axis. 

I also made some plates to mount the X axis rails to the Z axis, which are nice and simple: they keep the two carraige blocks close as to minimize any reduction in travel distance while also maintaining rigidity. I will do the same for the Y axis soon. Here's what those look like:

![cncmillxlinearrailplate][linearrailx]

[linearrailx]: Journal-Entries/cncmillxlinearrailplate.png

Here's what the full assembly looks like at the moment (note: the X axis motor plate is modeled but not in the assembly yet):

![cncmillfullassemblyupdate][fullassembupd]

[fullassembupd]: Journal-Entries/cncmillfullassemblyupdate.png

Of course, there are still many small pieces to figure out! One big thing is changing out the bed: I want to change it from that extrusion (very expensive for what it is imo) to a simple spoilboard (which I need anyway). This way, I can simply have holes drilled to bolt directly to the linear rails and the ball screw (no adaptor plates), as well as some kind of hole-based clamping system [like this one](https://youtu.be/O-rqf4uSXRE?si=c4zoKhAtzv9de5E1). I also need to make 3D printed end stops to the rails, 3DP parts with bearings to hold the ends of the ball screws, and some other final touches. Looking forward to finishing this off!

Time spent: 2 hours

## **7/11/2025 Log 13: Final Log!**

We're just about finished and ready for submission to Hack Club! First some updates since the last note:
- Switched to the spoilboard base as planned for cost reasons
- Re-did the colors in Onshape to look nicer and be more informative by material
- Created the spoilboard clamping system as a clone of [Marius Hornberger's design](https://youtu.be/O-rqf4uSXRE?si=c4zoKhAtzv9de5E1), using 3D printed cam clamps (may be adjusted if too weak in the future)
- Completed the [BOM](https://docs.google.com/spreadsheets/d/1udPoCN8MQFdChB4r3Y68Km0VLGHvW1hfCCyUqifvbzs/edit?usp=sharing) with all parts needed for construction

With these, I'm calling the project done! I may need to make some minor adjustments later on as I run in to issues and such, but for the time being it's all set. Thank you for reading and to Hack Club for providing this opportunity!

![finalscreenshot][final]

[final]: Journal-Entries/finalcncwithclamps.png


Time spent: 5 hours (mostly finishing BOM and writing this/the readme)