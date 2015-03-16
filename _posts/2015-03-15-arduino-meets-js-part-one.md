---
layout: post
title: "Arduino meets JavaScript (Part one)"
date:  2015-03-15 13:30:00
draft: true
categories: development IoT javascript arduino hardware node
tags: development IoT javascript arduino hardware node
description: Understand a bit about firmata and Johnny-Five library
---


Weeks ago I got a nice insight:

> A Javascript library that would connect Arduino boards by serial port and send specific hardware commands. Leaving all the heavy processing to the computer itself, using the board just as an I/0 device for physical interactions.

Well, happens to be a nice insight, I actually did get enthusiastic about it, and I started to code right away! But, also happens that someone already got the idea before, and coded on an hackathon, published at github/npm as [johnny-five](https://github.com/rwaldron/johnny-five), and it's actually very very nice.

You still can check my project at [github](http://github.com/marceloboeira/arnode), I'm going to code the idea, now based on firmdata, just for fun. :)

---

## About Johnny-Five

>Johnny-Five is an Open Source, Firmata Protocol based, IoT and Robotics programming framework, developed at Bocoup. Johnny-Five programs can be written for Arduino (all models), Electric Imp, Beagle Bone, Intel Galileo & Edison, Linino One, Pinoccio, Raspberry Pi, Spark Core, TI Launchpad and more!

# How it works?

First of all lets understand some concepts:

## Classic Process
 Usually to make an Arduino do something, you:
 * code
 * compile
 * burn into the board
 * test

Once the code is done, you compile it to a hex file, which contains the specific bytes that need to be written to the program the [memory](http://arduino.cc/en/Tutorial/Memory) of the chip on the Arduino board. This file is then uploaded to the board: transmitted over the USB or serial connection via the bootloader already on the chip or with external programming hardware.

After the code is "uploaded" into the chip, you have, most of the times, a stand-alone system, which means that it doesn't require the computer to work, so you can unplugg the USB port, connect it into a power source and it will run *forever*.

If by any chance you need to make changes on your code, you MUST make the process all over again.

#### Limitations

Every Arduino Board has a specific Flash storage size, that limits your code size to be around 30k, or 200k depending on the board type.

It also has a very interesting memory limitation, specified on the datasheet, the program memory supports at least 100,000 cycles, so it means that, you do have a limit of times that you can repeat the code uploading process, it's a very huge amount, but not endless.

Anyway, check [this](http://cybergibbons.com/uncategorized/arduino-misconceptions-5-youll-wear-out-the-flash-memory/) and [this](https://learn.adafruit.com/memories-of-an-arduino/arduino-memories).

## New Process

The "new process" consists on the firmdata protocol, let see how it works.

### Firmata

>Firmata is a generic protocol for communicating with microcontrollers from software on a host computer. It is intended to work with any host computer software package.

To get a better picture of this, lets go trought an example:

#### Problem

Imagine yourself coding a system that allows the user to hookup up to 30 lamps into arduino ports and turn then on and off by the computer, on a cloud server, from anywhere in the world.

Let say your firmware, on the arduino consists on a API client that requires every X seconds an URL of your cloud server, and retrieve a JSON file with all the pins and if they should be on or off.

That's nice, pretty neat, but now imagine that you want to make improvements, so now, people could hookup PWN devices, read temperature, and then they can create rules like, if the room temperature is >= 30 degress celsius, turn the air-conditioner on, and all sort of rules.

* What would do to mantain legacy hardware/software up?
* Would you ask to your 10.000 customers to upload new code on their boards? Will you do that?
* If in the future you need to create plans, where the user needs to pay $10,00 for 10 rules, $20,00 for 30 rules, $30,00 for 50 rules, how would you implement that, without compromise the current hardware/software? (imagine that your current hardware already support those specifications).


It's getting hard now, isn't ?

#### Solution

What if, you could, instead of sending JSON file with just "pins" and leaving the process to arduino, make the heavy process on the server and just send to arduino "low-level" I/O commands ? Would that solve your problems ?

Yeap! With firmata, you actually CAN do that, so your board would request the API url and wait for commands, like `digitalWrite`, `analogWrite`. This way you would not need to worry about anything related to the firmware on your board, legacy code, ...

Johnny-Five library uses the firmata to provide a very nice way to code with arduino + nodejs.


---

## Showtime

After this theorical first part, lets

## Sources

* http://arduino.cc/en/Tutorial/Memory
* http://arduino.cc/en/Hacking/BuildProcess
* http://openhardwareplatform.blogspot.com.br/2011/03/inside-arduino-build-process.html
