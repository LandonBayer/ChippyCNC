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
- Option to switch between a wooden spoilboard for plate work and a machinist vice for 3D parts
- Integrated E-stop

