---
layout: post
title: "Algorithmic approach of the Doppler effect"
date:  2015-03-07 13:30:00
draft: true
categories: development algorithm doppler effect
tags: development algorithm doppler effect
description: Lets get real nerdy
---

> A nice approach on how physics and computing together are fun

### Motivation

Recently I've been studying a little bit about a pretty interesting use of the doppler effect as an interpreter of "natural gestures" based on sound waves "reflex" and a pretty nice algorithm. So take a look on this funny, but useful, explanation below.

### What exacly is the Doppler Effect?

By definition, the doppler effect is:

> The apparent change in the frequency of a wave caused by relative motion between the source of the wave and the observer...

So, right question should be:

#### What does the motion do to waves?

Perhaps isn't so simple to understand without an example, so let's picture the most common used example to visualize. Imagine that you stand on the street and a ambulance passes by with the sirens turned on. While it is getting closer to you, you'll hear the tune is on a higher frequency because of ambulance movement effect on the sound wave.



Soon as the ambulance starts to move away from you, you'll start to hear the tune getting "slower", now the frequency is getting lower, again because of the movement effect on the sound wave.

More technically the Doppler effect is observed whenever the source of waves is moving with respect to an observer, it can be described as the effect produced by a moving source of waves in which there is an apparent upward shift in frequency for observers towards whom the source is approaching and an apparent downward shift in frequency for observer's from whom the source is receding. It is important to note that the effect does not result because of an actual change in the frequency of the source.

The effect is noticed not only on sound waves, but actually on every kind of wave.

To get a better "picture", take a look at this:

{% youtube h4OnBYrbCjY 600 %}


## Ok, but what is has to do with computers ?

As the title imples, if you think on a nice way to manage and mensure this changes of frequency in order to quantify them, you could make you computer acts as a interpreter and create something nice, like the guys [Unicomp have made](http://research.microsoft.com/en-us/um/redmond/groups/cue/SoundWave/).

They've created a pretty nice research based on the use of doppler effect to interpret gestures arround the computer.


#### How it works ?

It actually generates an human-inaudible frequency, on the notebook speaker and listens for the feedback of the waves on the microphone calculating the variation to predict the change of position and the speed of the object causing the feedback.

Take a look on a video exemplifying it:

{% youtube wK_u8-UQmOs 600 %}







