---
description: Beginnings of creating the keyboard 
title: Creating basic switch arrays
slug: creating-basic-switch-arrays
layout: ../../layouts/Logs.astro
featuredImage: https://res.cloudinary.com/aleksbry/image/upload/c_fill,g_center,h_400,q_auto:eco,w_1000/v1657366002/creating-basic-switch-arrays/14_i5pwea.webp
---

# Introduction

Using a [Quentin Lebastard's](https://www.youtube.com/user/qlebastard) tutorials from his channel I started to model my first parts of the keyboards. The tutorial was about creating the [design in Fusion 360](https://www.youtube.com/watch?v=scoX8NZv4MI). In the beginning I'm pretty sure there will be a lot of overlap between his work and mine, but I have a bit of a different vision where to take the keyboard, besides 3D printing, so the approaches should diverge eventually.

> I'm inspired by a lot of people and I want to make a promise to credit everyone that influences my work. I'll try to keep it as best as I can and link to everything that progresses my work. I'd only like for you, the reader, to show some love to the creators that influence my work whenever I mention them as I owe them my hobby and maybe potentially a job in the future.

# Switch holder

The approach Quentin takes really resonates with me and makes the whole project approachable. He broke down the development of his keyboards into smaller chunks which he then tackles in order.

His first step was to create a Switch Holder that is a socket for the MX style switch that we'll also be using. Here is how it went.

I first made a holder to test the fit for one switch. This is meant to establish a sort of a building block that I can then repeat throughout the design.

I am keeping the dimensions of the switch holder and other crucial ones as variables in Fusion, so I can always go back and change them slightly in one spot. I believe Fusion calls them parameters and you can add however many you want of them to parametrize your design. I really like that approach, comming from a programming background, as it reduces complexity and gives a name to sometimes magical numbers and/or calculations.

![single switch holder](https://res.cloudinary.com/aleksbry/image/upload/c_scale,q_auto:eco,w_700/v1657365746/creating-basic-switch-arrays/1_qlmfyl.webp)

Here are the dimensions I used for the switch holder.

![dimensions of the switch holder](https://res.cloudinary.com/aleksbry/image/upload/c_scale,q_auto:eco,w_700/v1657365725/creating-basic-switch-arrays/2_defxzj.webp)

![dimensions for the notch in the switch holder](https://res.cloudinary.com/aleksbry/image/upload/c_scale,q_auto:eco,w_700/v1657365747/creating-basic-switch-arrays/3_k1proi.webp)

*width: 4.5mm, height: 1.3mm offset from the top*

The small inset in for the switch pins is inset by 0.5mm.

The measurements from Quentin's video were very similar to mine so this is the design I will go with. Keep in mind that I can always tweak them just by changing one variable.

*Edit 1*: Going back to note that for some switches the 1.3mm gap from the top might be a tiny bit too small and the switch doesn't click in fully. This doesn't mean that it doesn't stay inside. Just that the element that's supposed to click in is staying a bit bent, but the switch itself is going nowhere.

*Edit 2*: Turns out it's a good idea to add a chamfer to the small inset for the locking pins. I added it to the top line and made it go all the way (0.5mm just like the inset). Now all of my switches sit there much better.

*Side note:* It might be good idea to keep the switch holder as a separate part in Fusion, to be able to import it multiple times and have the same reference, instead of copying the body of the holder from the beginning.

# Switch array

## First array

> I'm calling a column of switches an array. No reason for it, just sounds fun.

My first attempt at creating the switch array was mimicking what Quentin had designed - using 170mm circle as a guide for repeating a pattern of switch holders.

![arc to revolve the switch holder array around](https://res.cloudinary.com/aleksbry/image/upload/c_scale,q_auto:eco,w_700/v1657365962/creating-basic-switch-arrays/4_kmmyyz.webp)

The circle from the picture has a diameter of 150mm as I'm currently testing much bigger wells, but the first design I printed and is shown on the picture below is using 170mm diameter and a distance between the switches of 20mm.

The circle is created by placing a sketch on the side of the holder without indentations and making circle coincident with the top corners of the switch holder. These 20mm are pretty much an educated guess, as I knew a keycap has a dimension of 19mm, so I added some arbitrary space between them. This worked out actually very well and the keys are very tightly kept together but they never touch.

The operation for repeating bodies along the path is hidden in `Create > Pattern > Pattern on path`. Keep in mind that, to some extent, you can always go back to edit the circle to test other variants and the pattern should propagate throughout the timeline. If you do go back and change them, make sure you pay attention to the `Distance` in the pattern as it might need to be bigger so the keycaps don't clash.

![settings to create the array along the arc](https://res.cloudinary.com/aleksbry/image/upload/c_scale,q_auto:eco,w_1000/v1657365789/creating-basic-switch-arrays/5_e4mocj.webp)

After generating the holder array I connected them with lofts. I selected to-be-connected sides of neighbouring holders and used a loft with the default settings. As far as I know this can't really be done with one action so the timeline will have, in my case, 3 lofts for the 4 switches.

We should end up with one body, of an array for four switches. Here is a screenshot of one.

![switch array based on 170mm arc - cad model](https://media.graphassets.com/kIRNLSP2QgiO2JQOV4OF)

After that comes first 'integration hell' and \_probably* some thinking - where do I want to take this? I can partially answer the first question and as for the second part I'll try to answer it in a dedicated `Project Direction` post.

As for the integrations - here are the pictures of the first printed array of 4 switches with 170mm arc.

![switch array based on 170mm arc - printed version](https://res.cloudinary.com/aleksbry/image/upload/c_fill,h_500,q_auto:low,w_1000/v1657366001/creating-basic-switch-arrays/7_bp7lhy.webp)

![switch array based on 170mm arc - printed version](https://res.cloudinary.com/aleksbry/image/upload/c_fill,g_center,h_1000,w_1000,x_0/v1657366015/creating-basic-switch-arrays/8_olheg3.jpg)

![switch array based on 170mm arc - back view with switches in](https://res.cloudinary.com/aleksbry/image/upload/c_fill,g_center,h_400,q_auto:low,w_1000/v1657365996/creating-basic-switch-arrays/9_uzpluc.webp)

![switch array based on 170mm arc - side view with switches and keycaps](https://res.cloudinary.com/aleksbry/image/upload/c_fill,h_400,q_auto:low,w_1000/v1657366070/creating-basic-switch-arrays/10_ysaoxh.webp)

![switch array based on 170mm arc - top view with switches and keycaps](https://res.cloudinary.com/aleksbry/image/upload/c_fill,h_400,q_auto:low,w_1000/v1657366032/creating-basic-switch-arrays/12_qwyw1t.webp)

As you might have spotted the switches have wrong orientation. I fixed that in the screenshots from cad and in the new design, but just for fit-testing there is no difference. Also the print isn't the cleanest as the supports were pretty awkward for the second row to print - I'll tune that when it matters, by reorienting the whole array to either stand up or float it up by a millimeter from the build plate for supports to fully form and break of easier.

*Edit 1:* My dum dum brain didn't think I could print the holders on their side and just wasted probably 3h of my life. You live you learn I gues...

## Second array

As I've mentioned earlier I wanted to experiment with tighter welling, that's based on smaller diameter circles, so here are some pictures of 150mm.

I've changed the distance between the switch holders to 23mm, which was too big of a correction. After measuring the gap between the switches in this state I'd say it's 2mm to big. I do like the welling though. I might even benefit of making it even bigger for example exclusively for my pinky.

![150_array_front.jpg](https://res.cloudinary.com/aleksbry/image/upload/c_fill,h_400,q_auto:low,w_1000/v1657366030/creating-basic-switch-arrays/11_eoccyv.webp)

![150_array_side.jpg](https://res.cloudinary.com/aleksbry/image/upload/c_fill,g_center,h_1000,q_auto:eco,w_1000,x_0,y_0/v1657366066/creating-basic-switch-arrays/13_tulgbl.webp)

## Third array

My previous try has shown that the distance between keys was a bit too big for my taste, so with this one I made it smaller - 21mm. Now the keycaps have a gap of roughly 1mm between them and still don't touch each other. The tenting feels much more to my taste.

Here is a current result of a 150mm diameter arc for 4 switches with a 21mm distance between them.

![150_array_tight-front.jpg](https://res.cloudinary.com/aleksbry/image/upload/c_fill,g_center,h_400,q_auto:eco,w_1000/v1657366002/creating-basic-switch-arrays/14_i5pwea.webp)

![150_array_tight-side.jpg](https://res.cloudinary.com/aleksbry/image/upload/c_fill,h_400,q_auto:eco,w_1000/v1657366059/creating-basic-switch-arrays/15_u5fqyn.webp)

## Next steps

I'll probably measure the radius of rotation for each of my fingers, on the second joint from the top, as this is the one that does most of the work in my case. The other ones work because the keyboards I use are flat. For reference I'm using Ergodox EZ and I do like it, but I know I can go much further, which my experiments with Dactyls have shown me.

This does mean that there might be different welling (the diameter of a circle the holders are repeated on) for each finger and I absolutely don't think that this is a bad idea.

