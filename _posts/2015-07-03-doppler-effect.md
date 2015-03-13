---
layout: post
title: "Algorithmic approach of the Doppler effect"
date:  2015-03-07 13:30:00
draft: false
categories: development algorithm doppler effect
tags: development algorithm doppler effect
description: Lets get real nerdy
---

> A nice approach on how physics and computing together are fun

### Motivation

Recently I've been studying a little bit about a pretty interesting use of the doppler effect as an interpreter of "natural gestures" based on sound waves "reflex" and a pretty nice algorithm. So take a look on this funny, but useful, explanation below.

----

### What exacly is the Doppler Effect?

By definition, the doppler effect is:

> The apparent change in the frequency of a wave caused by relative motion between the source of the wave and the observer...

So, the right question should be:

#### What does the motion do to waves?

Perhaps isn't so simple to understand without an example, so let's picture the most common used example to visualize. Imagine that you stand on the street and a ambulance passes by with the sirens turned on. While it is getting closer to you, you'll hear the tune is on a higher frequency because of ambulance movement effect on the sound wave.

Soon as the ambulance starts to move away from you, you'll start to hear the tune getting "slower", now the frequency is getting lower, again because of the movement effect on the sound wave.

![ambulance](/static/images/doppler.gif)

More technically the Doppler effect is observed whenever the source of waves is moving with respect to an observer, it can be described as the effect produced by a moving source of waves in which there is an apparent upward shift in frequency for observers towards whom the source is approaching and an apparent downward shift in frequency for observer's from whom the source is receding. It is important to note that the effect does not result because of an actual change in the frequency of the source.

The effect is noticed not only on sound waves, but actually on every kind of wave.

To get a better "picture", take a look at this:

{% youtube h4OnBYrbCjY 600 %}

----

## Applications

If you think on a nice way to manage and mensure this changes of frequency in order to quantify them, you could make you computer acts as a interpreter and create something nice, like the guys at [Unicomp have made](http://research.microsoft.com/en-us/um/redmond/groups/cue/SoundWave/).

They've created a pretty nice research based on the use of doppler effect on sound waves to interpret gestures around the computer, check out their paper [here](http://research.microsoft.com/en-us/um/redmond/groups/cue/publications/guptasoundwavechi2012.pdf).

---

#### How it works ?

In order to measure the doppler effect for motion detection on a conventional computer, what you can do is send out a sinusoid at some known (human-inaudible) frequency, say, 20 kHz. If something is moving in the room, then, after the sinusoid has bounced around on the walls and into the microphone, the sound will shift in frequency. This can be measured by looking at the frequency spectrum in the nearby region of the 20 kHz tone. One of cool things is that you don't need a special equipment to make it work, but only a speaker and a microphone, already present on your notebook.

Take a look on a video exemplifying it:

{% youtube wK_u8-UQmOs 600 %}


[Here](http://danielrapp.github.io/doppler/) you can find pretty nice JavaScript approach, and cool effect on webpages by scrolling with gestures.

---

### Playground

I've used the [javascript](http://danielrapp.github.io/doppler/) implementation to create this little example below. The ball is controlled by movement around the computer, try shake your hands near it:

<center>
  <iframe width="600" height="600" src="http://jsfiddle.net/rvsq3bbe/12/embedded/result,js" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
</center>

## Sources

* http://danielrapp.github.io/doppler/
* http://www.einstein-online.info/spotlights/doppler
* http://www.physicsclassroom.com/class/waves/Lesson-3/The-Doppler-Effect




