---
layout: post
title: "Building My Own Watch: Threading"
---

{{ page.title }}
================

<p class="meta">Tiny tool time.</p>

In previous steps, you'll have noticed that my watch case has two holes<sup>[1](#foot1)</sup>: one for the glass, and one for the mechanism to go in, closed with a *case back*. Nearly all watches work this way. The case back needs to be held in some way, and in this case<sup>[2](#foot2)</sup> it's threaded.

Specifically an m35x0.5 thread. So 35mm outer diameter, with threads every 0.5mm. That's a very big, and very fine thread. This is such a weird thread that even the mighty 3000 page [Machinery's Handbook](https://www.amazon.com/Machinerys-Handbook-Toolbox-Erik-Oberg/dp/0831137320/) denies all knowledge of it.

![](/misc-blog/images/handbook.jpg)

The typical way to cut an internal thread is with a [tap](https://en.wikipedia.org/wiki/Tap_and_die), a kind a cross between a drill bit and a screw. For this weird thread, tapping isn't ideal. First, not even the mighty [McMaster-Carr](https://www.mcmaster.com/products/taps/thread-size~m35/) stocks an M35x0.5 tap, and even if they did I'd expect it to run over $500. Second, given the geometry, it'd need to be *bottoming tap*, likely to be even harder to find. Third, aligning a tap like that would be impossible.

So we need another option. One option is to [cut it on the lathe](https://www.youtube.com/watch?v=Lb_BURLuI70). This is a technique I'm familiar with, and the whole point of my silly hybrid electronic lathe conversion was to make it easier. But I wanted to try something new here: thread milling.

![](/misc-blog/images/thread_cam.png)

Here's the basic idea: we take a tiny milling tool with a 60° corner, and spiral it down along the thread profile. Thread milling is fast, theoretically very accurate, flexible, and apparently easy.

But I've never tried it before.

And the tool for this 0.5mm pitch is, no kidding, *very tiny indeed*.

![](/misc-blog/images/thread_mill.jpg)

So, here's the plan: we're going to spin this wee guy around at 10,000 RPM, spiral down at 400mm a minute, and nibble out the thread 0.1mm at a time. Six passes and we're done. Less than five minutes.

The problem with a tiny tool like this is that there's no margin for error. Its 1.25mm carbide shaft is strong, but brittle. Even the tiniest mistake and it'll snap like a twig. No pressure.

![](/misc-blog/images/thread_mill_2.jpg)

To get this right we have to nail two things: dialing in the tool so it has very little runout, and getting the work piece in exactly the right place. This is important because each tooth of this tool is going to be biting out only 13μm of metal, so if the runout or location is wrong by even 10μm it'll nearly double the chip load. The second was easy: do the bores, then thread without resetting the machine or moving the work. The latter was a little harder.

The first collet I tried I got nearly 30μm of runout at the tip! A brand new collet, very clean collet holder, and a couple goes getting the tightening torque right, and I was within 5μm. Not all bad.

![](/misc-blog/images/internal_thread.jpg)

And, in the end, it all worked out fine. First time, which is honestly kind of amazing. Thanks to [NYC CNC](https://www.youtube.com/watch?v=ggo24jmlpWA)'s tutorial, even the dimensions came out perfect, and the stock case back screwed right it. When I get around to making the case back, I'll make the external thread on that. In stainless, which is likely to be even less fun than in bronze.

**Footnotes**

1. <a name="foot1"></a> Or one, if you're a topologist.
2. <a name="foot2"></a> And this case.