---
layout: post
title: "iOS App Challenge at RIT"
date: 2016-02-03 8:00
permalink: Apple-Hackathon
---

Over the past weekend, I participated in Apple's fourth iOS App Challenge
Hackathon, where teams compete to design and build brand new apps from scratch.

My team consisted of [Sneha](https://github.com/svaswani),
[Blake](https://github.com/wbsllvn), and myself, all of who
had previously developed for Android but never iOS. Luckily, we had a lot of
guidance from [Stewart](https://github.com/sman591) and the folks at
Apple, who helped us to get started with Swift and Xcode, and to debug our
problems when we were helplessly lost.

# [Death by QR](https://github.com/svaswani/DQR)

Near the beginning of the hackathon, we decided to build an app based around
the traditional party/group game known as "Death by Dagger", "Assassin", and
other names. In these games, players are randomly assigned targets which they
have to catch unawares and "kill" them. To do this on iOS, we decided to use
QR codes as the killing medium. Each player in a game gets a QR code that
represents their identity, and a scanner which they can use to tag other
players with. Obviously, if the only objective were to not get scanned
by your attacker, there would be no incentive to let anyone scan your QR code
at all! So, we added a twist. Each player gains points by <i>allowing</i>
other players to scan their identity code. The trick is to try to avoid your
attacker in the process.

# Building DQR

To start building our app, we split up into different roles - Sneha started
designing the UI and flow of the game, Blake created the game logic on iOS to
track player status locally, and I threw together the QR scanner/generator
functions and the game server. This team composition worked very nicely because
we were almost never editing the same files at the same time, so committing,
merging, pushing and pulling were rarely problematic.

# Wrapping up the Hackathon

By the end of the challenge, we had an app with an intro screen, game lobby,
player QR identity, QR scanner, and win/loss screens. The server was also
ready to handle the game, but unfortunately we ran out of time before we
implemented the connectivity from iOS. We're hoping to continue on with DQR
by adding an Android client and bundling the server into each client so that
users don't need to rely on a 3rd party (our) server.
