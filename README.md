# DIY OneWheel
Custom DIY OneWheel Electric Board. I decided to try to make an easy to follow guide on my one wheel process in hopes that everyone else doesn't have to go through the same pain as me in order to do their own DIY OneWheel. Very fun project with great opportunities for learning to engineer.

Link to the CAD File --> https://a360.co/2GcbuvP

# Disclaimer!
Do your research! I do not take responsibility for any issues you may encounter during your build if you attempt to make a onewheel. It is difficult and there are many roadblocks you must engineer your way through. Learning comes through failure and troubleshooting so get used to it now if you plan on doing more projects in the future.

# Finished Project
### _Max Range: 5.5 miles (8.8 km), Max Speed: 20mph (32 kmh)_
<p align="center"><img src="OneWheel%20Photos/whole_angle.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Rail_switch.jpg" height=45% width=45%></p>
<p align="center"><img src="OneWheel%20Photos/Brains_tray2.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Brains_tray_close_marked.jpg" height=45% width=45%></p>
<p align="center"><img src="OneWheel%20Photos/battery_tray_full.jpg" height=45% width=45%> <img src="OneWheel%20Photos/battery_tray_full_close_marked.jpg" height=45% width=45%></p>


# Components
**Fundamental Components**
1. MPU6050 gyro, you can get these anywhere.
2. TORQUE ESC BLDC ELECTRONIC SPEED CONTROLLER (VESC-Motor Controller): https://diyelectricskateboard.com/products/torque-esc-bldc-electronic-speed-controller
3. 10inch 10 inch 10x6.00-5.5 wide tubeless tyre brushless gearless dc wheel hub motor (600W, 48V): https://www.aliexpress.com/item/32823573279.html?spm=a2g0o.productlist.0.0.72e6465ebj6ewY&algo_pvid=851b054b-e5d0-4ce6-a4b5-11497fe5d88c&algo_expid=851b054b-e5d0-4ce6-a4b5-11497fe5d88c-8&btsid=ef94e4fb-6a05-4494-a79c-043c26847dfc&ws_ab_test=searchweb0_0,searchweb201602_10,searchweb201603_55
4. Grip Tape (Get this anywhere that fits and has good reviews)
5. 13 18650 3.7 single cell batteries: (Get this anywhere, preferably samsung brand)
6. 48V 13s Battery Management System (BMS): https://vruzend.com/product/48v-13s-battery-management-system-bms/
7. VRUZEND battery kit V2.1 (Battery Clips): https://vruzend.com/product/vruzend-battery-kit-v2-0/
8. Relay 12v switch, 120A max (really only needs to be more Amps rating than your fuse by a little): https://www.amazon.com/Heavy-Duty-Relay-Split-Charge/dp/B07T35K8S2/ref=sr_1_12_sspa?gclid=Cj0KCQiAxrbwBRCoARIsABEc9sig7-S4l6okahDaEJmfuOvVVYE2xkklJyqML_9cLc2hu3RcjMeeA-QaAli5EALw_wcB&hvadid=322362950837&hvdev=c&hvlocphy=1014046&hvnetw=g&hvpos=1t2&hvqmt=e&hvrand=14030937440563530796&hvtargid=kwd-303078168660&hydadcr=5707_9590301&keywords=12v+120a+relay&qid=1578031911&sr=8-12-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUEzUVRFV0JYT1hGSEFJJmVuY3J5cHRlZElkPUEwMjE5MzQwN05PSko5NEJDM0hCJmVuY3J5cHRlZEFkSWQ9QTA4MDc4NDRON01RVzNMUzNWU1Mmd2lkZ2V0TmFtZT1zcF9tdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl
9. 60v to 3v-32v step-down converter, preferably one with a flyback diode, you can get them everywhere and I got one on ebay


**Other Components**
1. Pressure-Sensitive Conductive Sheet: https://www.adafruit.com/product/1361
2. Aluminum Rectangular Hollow Tube 2" x 1" https://store.buymetal.com/aluminum/rectangular-tube/6061-t6-t6511/aluminum-rectangular-tube-6061-t6511-2-1-0.125.html
3. Switch, I used an aircraft style switch because they look cool...but any will work as long as it works with the output voltage of your voltage step-down converter. In my case it was 12v
4. If you are doing the arduino method you need another voltage step-down from 48ish volts to 5v to power your arduino board
5. I suggest using JST Connectors!!! It's super cheap to get on Amazon and will help you undo your mistakes much easier
6. Rubber wheels with bearing: https://www.mcmaster.com/catalog/126/1524

# Build Info
- 48v 13s 2p Battery Pack
- (Easy) Vesc open source balancing tool
- (Hard) Arduino self made balancing logic

# Build Progression

### Step One: The frame
I have created a CAD file (Uses Fusion 360 which is FREE!) for the frame if you want to follow my process, but generally you need two rails that will hold the wires going from the battery compartment to your other component and mounts for connecting the motor axle to your rails. If you are a machinist this will be fairly easy, but if not I suggest you have someone else do this part. My CAD files provide the general outline but you need to decide how you want to do your own motor mounts. The third pic is after I finished and put my switch and stuff in. The yellow male connector is wired for charging to the bms and pack.
<p align="center"><img src="OneWheel%20Photos/Rail_IsoView.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Rail_TestFit.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Rail_Finished.jpg" height=30% width=30%></p>

- Two rails
- Motor mounts: I attached straight to rails with a slot lock washer that comes with the wheel. Did not hold up very long : ( 
- Holes on top of rails to attach component trays and foot pads
- I would suggest getting the rails extra long just in case you need larger component trays than you first thought, you can cut them later

The Aluminum was too weak to support the motor axle twisting back and forth constantly so I made some L shaped steel brackets with a slot in the middle for the axle. I don't have any pics of them when I was working on them but here you can see them on the rails.
<p align="center"><img src="OneWheel%20Photos/motor_mount_bot.jpg" height=45% width=45%> <img src="OneWheel%20Photos/motor_mount_top.jpg" height=45% width=45%></p>



### Step Two: Battery Pack
I would suggest that if you are unfamiliar with batteries you do some research prior to building your packs. Essentially I built two 13 cell packs and ran them parallel, but it's not apparent from my final photo because I did some wiring magic to make more space in my battery tray.
<p align="center"><img src="OneWheel%20Photos/Batt_OldSeriesPack.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Batt_Finished.jpg" height=45% width=45%></p>

- 26 18650 3.7 cells total
- 13 cells in series (x2)
- Put both those packs in parallel
- (You could do this with 13 cells and just make one pack if you really want, it will have the same voltage, but I wanted more amp-hours)
- Look at the wiring guide for your battery management system (BMS) and wire accordingly. In my case I soldered 1 balancing wire to each two cell groups for a total of 13 wires. Then I connected the + and - wires to their respective locations. This video helped me a lot: https://www.youtube.com/watch?v=m4DGDkwFr54

### Step Three: Component Wiring
At this point in the project I 3D printed two trays to hold my batteries and components. I also printed a plate to hold all of my non battery components, all these components are in the OneWheel frame CAD file.
![alt test](OneWheel%20Photos/Wiring_Plate.jpg)

Here is a general wiring diagram for the OneWheel. Sorry for how unprofessional it is. Keep in mind if you are using something besides the VESC balancing app you need to wire the arduino board or whatever you use for the balancing logic in between the vesc and relay.
![alt test](OneWheel%20Photos/Wiring_Drawing.jpg)

This is the adjustable voltage step down converter I used
![alt test](OneWheel%20Photos/converter.jpg)


Here is a photo of the hall sensor connection to the VESC, from left to right in the pic it goes 5v,Temp,H3,H2,H1,GND
I'm pretty sure the order of hall sensors doesn't matter, if it doesn't work in vesc than just switch two and it should.
Same goes for the phase wires (The 3 bullet connectors coming from the motor).
The motor listed in the parts section does not have a temp wire so leave that pin empty.
![alt test](OneWheel%20Photos/Wiring_Hall.jpg)

This is the wiring for the MPU6050...
![alt test](OneWheel%20Photos/Wiring_MPU.jpg)

And its connection to the VESC, it's the connector at the front of the picture.
The wires you don't see in the MPU (Dark Blue, two greens) are the wires for the switches, which will be wired to footpads later, but it's best to just use them as bare wires for testing. Dark blue is the 3.3v pin, and when connected with one or both green wires (MISO, SCK) it will toggle switches on the VESC we will use later.
![alt test](OneWheel%20Photos/Wiring_Switch.jpg)

#### Finished Component and Battery Tray
<p align="center"><img src="OneWheel%20Photos/componentTray.jpg" height=30% width=30%> <img src="OneWheel%20Photos/batteryTray.jpg" height=30% width=30%> <img src="OneWheel%20Photos/onewheelAlmostDone.jpg" height=30% width=30%></p>

### Step Four: Metal Trays
The 3D printed trays were not holding up in early tests so I made some metal trays out of very thin steel sheet metal.
<p align="center"><img src="OneWheel%20Photos/tray_template.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Metal_Tray.jpg" height=45% width=45%></p>
<p align="center"><img src="OneWheel%20Photos/Open_full.jpg" height=80% width=80%></p>




### Step Five: VESC App
With everything now wired up I would suggest you test using a multimeter from the beginning of your wiring to the end to make sure you don't fry anything. This is also why I say to use a fuse.

Plug in your vesc and open the app (Google how to get the app, it's easy). Then turn on your OneWheel
Here is a good video on how to set it all up: https://www.youtube.com/watch?v=0y5ME2SgwLg

I have XML files for the settings of the motor and app configuration in this repo

After this you can technically ride it fairly easily but it will only go 12mph so I went ahead and added some other stuff to make the ride better.


### Safety Wheels
I bought some rubber wheels with bearings from McMaster-Carr but sadly I measured something wrong and they didn't fit inside the rails, so I attached them on the outer side of the rail, with the bolt going through a hole on the other side for rigidity.

Here they are attached to the side of the rails
<p align="center"><img src="OneWheel%20Photos/Wheel.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Rail_mount_close.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Rail_wheel.jpg" height=30% width=30%></p>


### Motor Modification
So this motor comes stock wired in the “wye”(star) configuration which for bldc motors means high torque low rpm. So after getting advice from others I went ahead and wired the motor to be in the “delta” configuration. This enabled me to reach speeds of 20mph, but with roughly 70% less torque so less acceleration. But for me as a 190 lb dude I can still ride it with ease.

For great info on this read up: https://forum.esk8.news/t/redstar-diy-onewheel/10595/73
Also this video helped me, it’s basically the conversion but in reverse: https://www.youtube.com/watch?v=b7DkOYdarkU

Here's some pics of my process…
<p align="center"><img src="OneWheel%20Photos/Motor_wheel.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Motor_start.jpg" height=30% width=30%> <img src="OneWheel%20Photos/Motor_wip.jpg" height=30% width=30%></p>
<p align="center"><img src="OneWheel%20Photos/Motor_tape.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Motor_done.jpg" height=45% width=45%></p>


### Footpads
I really thought this would be the easiest part but it ended up taking much longer than I wanted. I couldn't get the built in footpad sensing in the VESC app to work with my velostat, I think it may have been because my velostat was barely changing the voltage. So I used a small arduino board to do the footpad logic and then feed that to the VESC.

<p align="center"><img src="OneWheel%20Photos/Footpad_arduino.jpg" height=45% width=45%> <img src="OneWheel%20Photos/Footpad_under.jpg" height=45% width=45%> </p> 
<p align="center"><img src="OneWheel%20Photos/Footpad_data.jpg" height=80% width=80%></p>

I powered the arduino off of the 5v and GND from the CAN-BUS port on the VESC

Arduino code is in this repo


## Demos

<p align="center"><img src="OneWheel%20Photos/Riding_pic.jpg" height=50% width=80%></p>


### Maiden Voyage
-First time testing the OneWheel --> https://www.youtube.com/watch?v=Fk23jWkvQ68

-First good rides --> https://youtu.be/yCfcjczSD3g  |  https://youtu.be/kdDiJmPOgKU 





## Future Plans
1. Added parallel pack to fit in the brains tray
2. More compact battery packs so I can shrink tray depth
3. More concealed wheels



