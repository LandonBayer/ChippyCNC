# Chippy
CNC Mills are expensive, large, and generally not very accessible to the average maker in their home. With Chippy, a small, simple, cheap but powerful CNC router, these capabilities may become available to the hobbiest at a relatively low price. Unlike the commonly found [3018-style](https://a.co/d/4NDyeWJ) cnc, which is a respectable $150 but fails to do anything more than engraving, Chippy boasts linear rails rather than guides, ball screws in place of lead screws, a 500W ER16 spindle, and an extrusion frame to maximize performance. Even the similarly priced Lunyee [3018-pro](https://a.co/d/8d0D7FV) still uses guides and lead screws in place of high quality parts, making Chippy a more compelling DIY package.

I personally had a lot of experience using CNC machines through my robotics team, where I regularly ran an [Omio X8-2200L](https://www.omiocnc.com/products/x8-series/x8-2200l-usb-cnc-desktop-engraver.html) to manufacture parts. Using that experience, I designed Chippy to best compromise performance, ease of use, and reliability in the ways I sought throughout the build seasons. I also did my best to use some parts that I had on hand, such as the linear rails, ball screws (without nuts), a Z stage, and 8020 extrusion. This minimizes my personal input cost, as well as recycles otherwise useless components that I own.

Project Goals:
 - Create a usable but cheap CNC
 - Small footprint (small volume will encompass most parts)
 - Functional speeds, expected to be slow but reasonable
 - Minimum Z probing, ideally X and Y as well
 - Rigid Frame
 - Effective clamping solution
 - Be able to mill aluminum (not just engrave, and not only wood/plastics)

Specs:
- 200 x 180 x 90mm working area (more on the sides for clamping)
- Linear rails to maximize rigidity
- Ball screws to maximize accuracy (not found on any other low cost machines)
- All aluminum frame
- 500 Watt 12000 RPM ER16 spindle
- GRBL Control (outdated but will function perfectly in most scenarios)
- High torque stepper motors on all axis
- Option to switch between a wooden spoilboard for plate work and a machinist vice for 3D parts (note: I can't find exact dimensions on the vice, so that will be added at a later date)
- Integrated E-stop

![finalscreenshot][final]

[final]: Journal-Entries/cncmillnewclamps.png

[Onshape Link](https://cad.onshape.com/documents/fe491084e56455da2d5a649d/w/3d810b1fec2b376e1d8655d1/e/08e152ea0122b69bfa13cece)

[BOM Link](https://docs.google.com/spreadsheets/d/1udPoCN8MQFdChB4r3Y68Km0VLGHvW1hfCCyUqifvbzs/edit?usp=sharing)

Here's a rough wiring diagram of how to put this machine together, as per Hack Club requirements:

![wiringdiagram][wires]

[wires]: Journal-Entries/cncwiringdiagram.png

| ITEM | PRICE | QUANTITY | TOTAL PRICE | SOURCE | Ordered | Owned | LINK |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mainboard | 19.57 | 1 | 19.57 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256805662918330.html |
| 400mm ball screw | 22.1 | 2 | 44.2 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256802936754324.html |
| ball screw nut mounting block | 4.76 | 2 | 9.52 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/2255800872193882.html |
| Daedalus CNC Spindle Motor Kit, 500w, ER16, Brushed | 99.99 | 1 | 99.99 | Amazon | FALSE | FALSE | https://a.co/d/ilFF7XH |
| 24V 8A power supply (for steppers + control) | 16.99 | 1 | 16.99 | Amazon | FALSE | FALSE | https://a.co/d/3KXWlDU |
| Nema 17 2 amp high torque stepper motors (3 pack) + wires | 32.99 | 1 | 32.99 | Amazon | FALSE | FALSE | https://a.co/d/6JUlACn |
| 5mmx8mm coupler | 6.58 | 1 | 6.58 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256807349420029.html |
| Z touch probe | 6.42 | 1 | 6.42 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256808663692081.html |
| 3 inch cnc vice + mounting bolts | 44.77 | 1 | 44.77 | Amazon | FALSE | FALSE | https://a.co/d/5kOnS3H |
| E-stop and Limit Switch Kit | 9.78 | 1 | 9.78 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256807406356837.html |
| M4 T-nuts for the linear rails (3030 sized work for 1x1 extrusion) | 6.39 | 1 | 6.39 | Amazon | FALSE | FALSE | https://a.co/d/hFEOWDT |
| M10 3pack 25mm pins (for clamping) | 4.9 | 2 | 9.8 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256805291847458.html |
| Ball screw support bearings (8mm ID) | 2.99 | 1 | 2.99 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256805324873222.html |
|  |  |  |  |  |  |  |  |
| Assorted Metric screws (mostly for M4, I have these already) | 17.83 | 1 | 17.83 | Amazon | FALSE | TRUE | https://a.co/d/3Fa4UwA |
| 90 degree 8020 brackets + bolts (can be used in place of 2x2 ones as well) | 18.9 | 3 | 56.7 | Amazon | FALSE | TRUE | https://a.co/d/7QSxBpf |
| Z stage (recommended 100mm, I had 200mm) | 55.98 | 1 | 55.98 | Amazon | FALSE | TRUE | https://a.co/d/2d2hLF8 |
| 350mm HGH15 linear rails (by far the most expensive part) | 89.92 | 2 | 179.84 | Aliexpress | FALSE | TRUE | https://www.aliexpress.us/item/3256801410951679.html |
| 450mm 2x1" 8020 extrusion (cut to length) | 14.51 | 3 | 43.53 | Other | FALSE | TRUE | https://8020.net/1020.html |
| 450mm 1x1" 8020 extrusion (cut to length) | 9.5 | 2 | 19 | Other | FALSE | TRUE | https://8020.net/1010.html |
| 200mm 2x1" 8020 extrusion (cut to length) | 7.73 | 2 | 15.46 | Other | FALSE | TRUE | https://8020.net/1020.html |
| 400mm 1x1" 8020 extrusion (cut to length) | 8.76 | 2 | 17.52 | Other | FALSE | TRUE | https://8020.net/1010.html |
| 350mm 1x1" 8020 extrusion (cut to length) | 7.97 | 2 | 15.94 | Other | FALSE | TRUE | https://8020.net/1010.html |
| 1kg PLA Pro filament (for clamps and mounting plates if desired) | 24.99 | 1 | 24.99 | Other | FALSE | TRUE | https://us.polymaker.com/products/polylite-pla-pro?variant=39574346334265 |
| 6mm shank 2mm ball NO 3D Probe | 52.35 | 1 | 52.35 | Aliexpress | FALSE | FALSE | https://www.aliexpress.us/item/3256808425022835.html |
|  |  | Necessary total: | 756.78 |  |  |  |  |
|  |  | My total: | 309.99 |  |  |  |  |
|  |  | With probe: | 362.34 |
