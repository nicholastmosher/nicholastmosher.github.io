---
layout: post
title: "Easycom Android Bluetooth Library"
date: 2016-09-15 14:49
permalink: Easycom
---

# What's Easycom?

Easycom is an Android library that aims to simplify the way developers use
data transfer mechanisms such as Bluetooth and TCP. Originally, Easycom was an
idea I had for a fully-fledged Android app that would act as a configurable
remote control for robotic or other electronic projects. I wanted something
that could support multiple communication strategies so that a device
controlled with a Bluetooth adapter could be reconfigured with a Wifi or
Ethernet adapter without worrying about underlying implementation details.

# The original design

Since Easycom started as a full app idea, there were three main sections of the
app that I needed to create.

* A communications framework so that I could switch between interfaces easily.
* A basic UI layout for discovering, creating, and managing the connections.
* A reconfigurable controls palette for virtual joysticks, buttons, and other
interactive elements.

With this in mind, I knew that this was a huge project if I wanted to see it to
completion. I decided that my best bet was to achieve a minimum viable app
first, then expand upon it. That placed the communications framework squarely
in the top priority, so that's what I began focusing on.

# Communications framework design

When I began researching how to use the Android Bluetooth libraries, I noticed
that they followed the exact same organizational pattern as the traditional
TCP socket interface. While there were discrepancies in the details, they both
shared the concept of establishing sockets and opening input/output stream
pairs. After discovering this, I realized that most communication strategies
could probably be abstracted in a similar way. I concluded that at a high
level, all communications shared the following operations:

* Connecting
* Sending data
* Receiving data
* Disconnecting

With this in mind, I began my framework with an abstract Connection class with
these four operations as abstract methods which would be implemented by
subclasses.

# New developer obstacles

Since I was new to Android development when I began this project, I ran into a
lot of complications as I tried to fulfill my design. As any new developer
could, I made the mistake of thinking that the app's Activities were a place
for putting *all* of the business logic of the app. I quickly discovered that
Activities were a terrible place for putting network code because of how easily
they get created and destroyed, such as when transitioning through Activities
in the app or rotating the screen. In order to prevent that from happening, I
had to discover and read up on how Services work in Android. It seemed simple
enough in theory, but implementing it was deceptively difficult. In order to
effectively use Services I had to figure out how Intents worked, and then I had
to know how to coordinate the lifecycles of the Activities and Services as they
interacted with one another. Once I figured out how to launch into a Service
and begin routines, I thought I was golden. However, it turns out that
networking code is full of blocking calls, and I soon found that after
launching a Service to connect or transfer data over a connection, the UI
would stutter and freeze. After more extensive research, I realized that
although Services intuitively ran in the background, they actually executed on
the main UI thread by default. In order to combat this, I had to redesign the
Service so that as new connections were opened, they would operate on
independent, non-UI threads.

# The objective redirect.

By the time I had a reasonably functional communications framework, more
than half a year had passed and I'd graduated high school and begun college.
While I was still attached to the project, I was branching out into other
technical areas and didn't have nearly as much time to dedicate to the project.
In order to bring decent closure to what I'd made, I decided to take the
functionality offered by the framework I'd made and repackage it as an Android
library. I spent a lot of time retracing my steps and documenting the project,
highlighting how to use it and how it could be extended in the future.

# Outlook

Easycom is one of my favorite early developer projects because it was a
challenging problem that required a lot of learning to accomplish. When I
started, I had a good handle on Java but no experience with Android, but by the
time I finished I'd learned about the roles of Activities and Services, how to
use class hierarchies to pass implementation to subclasses, how to use
multithreading and callbacks effectively, and how to organize a public-facing
interface with strong documentation to make a concise library.

# Links

If you're interested in using or improving Easycom, feel free to check it out
[here](https://github.com/nicholastmosher/easycom-core), and the repository for
the original app for managing connections is
[here](https://github.com/nicholastmosher/easycom).
