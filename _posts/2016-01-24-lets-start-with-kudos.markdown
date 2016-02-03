---
layout: post
title: "Let's start with Kudos"
date: 2016-01-24 11:56
permalink: Kudos
---

Well, here we are. It only took me until 2016 to make my very own website, and
there's a lot of catching up to do. I want to start by talking about Kudos, a
robot that I built way back in the summer of 2014. Kudos was born from the
skills developed over four years of FRC combined with a rush of inspiration
from Richard and Charles Raitt's robot
[Hormes](https://www.sparkfun.com/news/1450) all put together with the money
earned over a summer internship.

## Inspiration

The time it took me to decide that I wanted to build my own robot was about
five minutes. In August 2014, my friends Nygel Meece and Richard Raitt were
spending the night on their way to a convention in Baltimore. Richard had
brought with him Hormes, a robot that he and his brother Charles had built and
then showcased at several FRC regionals, which demonstrates how skills taught
by FIRST can be applied outside the scope of the competitions. I thought that
Hormes was the coolest thing ever! It had huge wheels and a strong frame so it
could go over sidewalks and through ditches - and it was controlled with an
Xbox 360 controller! And what was more, after taking a look inside, I was
confident that I could build a robot that was just as cool.

## Design and Preparation

Following my introduction to Hormes, I spent a solid week prototyping design
ideas in CAD, sourcing materials and parts, and evaluating the
feasability of the project as a whole. The parts I needed were expensive, and
I wanted to make sure that if I started the project that I would complete it.
I knew that the best way for me to ensure that was to have a design and build
plan all laid out before even buying the parts. I went through two full
CAD design ideas in Fusion before settling on the one I built, and I identified
the Arduino and shields I would need for the control solution, as well as
their corresponding libraries. I settled on an
[Arduino Leonardo](https://www.arduino.cc/en/Main/ArduinoBoardLeonardo) and
Richard directed me to the
[USB Host Shield](https://www.circuitsathome.com/products-page/arduino-shields/usb-host-shield-2-0-for-arduino)
and it's [library](https://github.com/felis/USB_Host_Shield_2.0) used on
Hormes for the Xbox 360 controller integration.

Here's a snapshot of the first iteration of my design for Kudos. This was
designed in Autodesk Inventor 2014.

![Robot Design 1](/assets/Kudos/Robot1Top.png)

In this design I was fixated on the rollcage, which would serve to protect the
battery and electronics from damage. I scrapped this due to the complicated
design and large material costs.

This is much closer to the design I settled on for Kudos, with a flat frame
construction using 1x1 inch aluminum square tubing and 1/16" aluminum gussets.
This version was also designed in Inventor, though the final revision I used
for fabrication was developed in Autodesk Fusion 360.

![Robot Design 2](/assets/Kudos/Robot2BatteryBack.png)

A nice feature of Fusion 360 is that all of your design data is saved in the
cloud via Autodesk 360 in their "MyHub" subdomain, which means that I can
generate shareable links and embedded views of my designs. Below is a minimal
[model of Kudos](http://a360.co/1TjRhoL).
Since I'd already hashed out how it would look in Inventor, I only designed as
much in Fusion as I needed to generate cutpaths for the ShopBot.

<iframe src="https://myhub.autodesk360.com/ue29ffab2/shares/public/SHabee1QT1a327cf2b7a6cb3617bf692b2cb?mode=embed" width="800" height="600" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

Note: The rendering above is based on WebGL which can be finicky on some
systems, so I apologize in advance if you can't view it.

## Fabrication

After I had decided on my design, I began constructing the frame of Kudos
while I waited on electronics and other parts shipped. My mentors from FRC were
more than willing to let me use equipment in the team's workshop, which
ultimately made Kudos a higher quality product overall. In fact, my CAD design
of Kudos was largely influenced by the fabrication paradigm my team had
developed over the previous year after we added a ShopBot CNC router to our
shop. The paradigm was based on two principles: exchange thorough design for
an easy assembly; and incorporate the complex design requirements into 2D
materials for the ShopBot to handle. Kudos's frame exhibits both of these
qualities, as can be seen in it's square-tube-held-together-with-gussets style.
Gussets, for those unfamiliar, are the aluminum plates that you can see in the
designs that hold adjacent square tubes together.  To make the parts trivial to
assemble, all bolt holes follow a universal 1" spacing. On the square tubes,
the holes run at 1" intervals down the center (i.e. 1/2" from each edge), and
on the gussets the holes fall into a 1x1 grid. The bottom plate of Kudos
also follows this pattern, but is much larger and spans the entire center of
the chassis. This serves to provide a platform to mount the battery and control
system, but mechanically it also grants rigidity to the entire frame.

<div style="margin:auto;">
 <div style="float:left;width:48%;margin-right:10px">
  <img src="/assets/Kudos/FrameCNC.jpg">
 </div>
 <div style="float:left;width:48%;">
  <img src="/assets/Kudos/FlatFrame.jpg">
 </div>
</div>

Here's the bottom plate when it was being cut on the ShopBot, and afterward
when it was built into the base frame.

This is a little fast-forward, but you can get see the full bottom plate
much clearer in this picture.

![Kudos's Frame Bottom](/assets/Kudos/FrameBottom.jpeg)

The next big thing to talk about would be the drive setup. The wheels are 10"
diameter pneumatic wheels with a 5/8" bearing bore. The gearboxes are
AndyMark CIMple boxes with one CIM motor on each side, with an output shaft
to a double sprocket. This style of construction is also directly taken from
Hormes, which is obvious to see at even a glance of the two robots. Since
the wheels have bearing-bores, the axle on Kudos is what's known as dead-axle,
where the wheel spins <i>around</i> the axle, which remains fixed. This means
that in order to drive the wheels, there needed to be a method to transfer
power from the gearbox to the wheels, hence bike chain. However, the pneumatic
wheels didn't have sprockets on them to receive the chain. Luckily, I'd been
keeping in touch with Richard while sourcing the parts, and he pointed me to
the exact parts he used on Hormes. While the wheels didn't have sprockets
as-shipped, conveniently there are sprockets available online that have the
exact same hole pattern as the wheels, so by using long bolts and spacers,
the sprockets can become fixed to the wheels.

![Wheel with Sprocket](/assets/Kudos/WheelSprocket.jpeg)

Above, you can see the sprocket on top with bolts protruding downward, with
the bolt heads on the opposite side of the wheel. The sprocket needed to be
spaced away from the wheel, so I used 3 layers of 3/4" plywood that I cut on
the ShopBot to have a matching hole pattern.

This is a side view of Kudos after the drive system was all put together. You
can see the chains driving both wheels while leaving plenty of clearance
underneath.

![Drive View](/assets/Kudos/KudosDriveSide.jpg)

Below you can get a really good look at the chain hookup.

<div style="margin:auto;">
 <div style="float:left;width:48%;margin-right:10px">
  <img src="/assets/Kudos/CloseupWheel.jpg">
 </div>
 <div style="float:left;width:48%;">
  <img src="/assets/Kudos/CloseupSprocket.jpg">
 </div>
</div>

This brings me to another point I want to talk about really quickly. I was
building Kudos right after an FRC season in which my team used timing belts
instead of chain for the first time. Timing belts aren't adjustable once you
have them, because they don't stretch and aren't resizeable like chain.
Because of that, I'd adopted a design approach that involved incorporating
slots so that one of the pulleys in the belt would be slightly adjustable,
allowing any slack to be tightened. While this approach is more necessary for
belt - and I admit, with a precise enough design, belts can be made to work
without the need for adjusting pulleys - it also works very well for making
chain much easier to work with. Unlike belts, chain <i>can</i> be adjusted,
but only by one or one-half link at a time, which can result in the predicament
of choosing a setup that's slightly too tight or slightly too loose. Making
the change is also a hassle, because it requires the proper tools and parts
to be on-hand, and fumbling with master links and half-links isn't the most
fun thing to do.

<div style="float:left;width:38%;margin-right:10px;">
 <img src="/assets/Kudos/AxleBlock1.jpg"/>
</div>
<div style="float:left;width:60%;">
 <div sytle="float:top;height:48%;">
  <img src="/assets/Kudos/AxleBlock2.jpg"/>
 </div>
 <div style="float:top;height:48%;margin-top:10px;">
  <img src="/assets/Kudos/AxleBlock3.jpg"/>
 </div>
</div>

I designed this set of what I like to call "axle blocks" which are inteded to
provide the sliding adjustment described above. These blocks have 5/8" holes
with just enough tolerance for the 5/8" steel axle to fit snugly, with slots
toward Kudos's frame large enough to fit 1/4-20 bolts through. The three
possible axle mount points, plus the ability to slide the entire block,
provides a flexible way to keep the chains tight with only the need for a
socket wrench.

## Control

I feel like I've covered most of the significant mechanical features, so let's
take a look at the control system. Kudos is controlled by an
[Arduino Leonardo](https://www.arduino.cc/en/Main/ArduinoBoardLeonardo) and
two [Talon SR Speed Controllers](http://www.andymark.com/Talon-p/am-talon-discontinued.htm).

![Open Control Box](/assets/Kudos/ControlboxOpen.jpg)

The two devices in the lower right hand corner of the box are the Talon SRs,
on the lower left is the Arduino, to the top left is a power distribution
module, and on the top panel is the Xbox 360 receiver.

![Arduino and Shields](/assets/Kudos/ArduinoSide.jpg)

This is a great shot to explain the Arduino and shields setup. The Arduino
Leonardo itself is the bottom board, which is the microprocessor development
board that contains all of the programming for what Kudos does. On top of it
are two "shields", which is just a term in the Arduino world to refer to
expansion boards. The one in the middle is a USB Host shield, which allows me
to plug in the Xbox 360 receiver (the plug on the left in the picture) so that
I can interpret button and joystick actions on any connected Xbox 360 remote.
The shield on the very top is a prototyping board that I used to make
neat connectors for the PWM wires. PWM stands for "Pulse-Width Modulation",
and is a technique for adjusting the ratio of "on" time to "off" time in the
electrical signal. These PWM-carrying wires connect to the Talon SRs, which
use the signal to determine how much voltage to supply to the motors (which
determines motor power) as well as the polarity (which determines motor
direction). The small chip attached by four wires to the top of the protoboard
is a bluetooth module, which I didn't end up using for Kudos but made it into
the picture anyway.

# Talons

![Talons](/assets/Kudos/TalonSRs.jpg)

The reason the Talons are necessary is because large motors like the CIMs
require a lot of power to run. If we tried to draw that power straight from
the Arduino, it'd most likely get fried. Instead, the Talons draw current
directly from the battery and use the PWM signal from the Arduino to determine
how to apply it to the motors. Above, you can see the connectors on top which
attach to the battery, and the ones on the bottom that go to the motors. The
three small wires on top of each Talon are carrying the PWM signal from the
Arduino.

![Closed Control Box](/assets/Kudos/ControlboxClosed.jpg)

Here's the control box when it's all tidied and closed up. The large cable
and connector connect to the battery, and the two pairs of smaller wires go to
the CIM motors. The box itself was cut out of polycarbonate on the ShopBot,
with a square fit pattern on the edges to help it seal up. The cut quality was
actually terrilble from a machining standpoint, but the jagged edges ironically
give the box a nice "snap together" feel. That's also red gaffer's tape holding
the sides together, which I figured would be a temporary solution but has held
up perfectly for two years.

![Kudos all put together](/assets/Kudos/KudosFinished.jpg)

Here's the full picture when all of the components are put together. The
control box and battery both have their own neat little compartments, and the
wire routing is pretty straightforward. The only thing in this picture I
haven't talked about yet is the main breaker. It's the little black box on the
lower right hand corner of the frame and is a safety device for current
overdraw or an emergency stop switch.

# Code

The code for Kudos is entirely open source and kept on
[GitHub](https://github.com/nicholastmosher/Kudos), written in C++. Feel free
to read and learn from my code, use it, change it, and even let me know if you
feel that there could be some improvements!

## Origin of the name

Another cool thing Richard told me about Hormes was what it's name meant. I'll
quote from Wikipedia because I don't remember exactly how he said it: that
Hormes was "the Greek spirit personifying energetic activity, impulse or
effort... eagerness, setting oneself in motion". I thought that the meaning fit
really well, so I checked to see if I could come up with a Greek name for my
robot to compliment his. Kudos is from greek origin at least, meaning
"acclaim or praise for exceptional achievement." It may be a little boastful,
but I like to think of Kudos as a praise to Hormes for the achievement of both
of them.

## Thanks

One last quick shoutout to everyone who helped me out on this project: Richard
for his help sourcing parts, Charles for Hormes's source code to get me
started, and to my robotics mentors for teaching me the skills I needed!
