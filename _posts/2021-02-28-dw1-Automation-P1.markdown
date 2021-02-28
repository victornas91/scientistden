---
layout: post
title: Digimon World Automation Part 1!
date: 2021-02-28 13:59:00 +0300
description: Beginning to believe. # Add post description (optional)
img: mj.png # Add image post (optional)
tags: [Python, AI] # add tag
---
You know, back when I was a little lad, I used to play this game called Digimon World for the Ps1. The mix of being a babysitter for a digital monster and the intense battles made me love the game. And as everything in our world, currency is a big thing in this game too.
To make things quick here: there's a exploit that help the player amasses a ton of coin but at the cost of pressing the same buttons over and over again D: 

Recently after revisiting the game and having to make the exploit work I've decided to use instead my small brain coupled with the knowledge of Python and Machine Learning to automate the tedious parts of the game. So this is a multi-part series where I build a bot and increment it with Machine Learning techniques. This part one is about the basic concept of keybindings and how to build a bot that just mindlessly does what you want.

First a brief explain of how the exploit works: 

![medrec]({{site.baseurl}}/assets/img/medrec.PNG)

By mid-game us players already have a shop available where we can buy recovery items. The trick is to buy a specific one: the med recovery. By doing that and trading with one of the npcs(non-player-character, basic anyone that's not us in the game) we can turn a $500 item into a $2000 one. Selling the resulting item allow us to get rich "quick".

![mj]({{site.baseurl}}/assets/img/mj.PNG)

After talking with this npc (Mojyamon is its name) we can begin the bargain. But here the tedious part begin: we have to select the npc, select the item we want him to trade with us, then select our item from the inventory and then confirm. Doing this 5 times is not a problem but for all the greedy people that buy 99 med recovery (since 99 is the inventory individual limit) imagine doing this whole shenanigan 99 times FOR EACH item. That's where Python with our time saviour module pyautogui comes to the rescue. PyautoGUI let us emulate inputs from keyboards and mice. That and much more, you all will see here!

![pyautogui]({{site.baseurl}}/assets/img/pyautogui.PNG)

First we import pyautoGUI.

![ct]({{site.baseurl}}/assets/img/ct.PNG)

Now we will create a basic infinite loop. Remember that this initial bot lacks refinement. It will just emulate a player doing a repetetive task endlessly. 

![kp]({{site.baseurl}}/assets/img/kp.PNG)

Using the keyDown() function we emulate a person pressing the desired keyboard key and holding it down, in my case since i'm using an emulator, the corresponding key to the Circle of the Ps1 is the numpad6 of the keyboard. Next with the PAUSE function we are saying to the bot "hey, wait half a second before doing the next thing". Finally with the keyUp() function we emulate the act of letting go the key.

![fullkeys]({{site.baseurl}}/assets/img/fullkeys.PNG)

And that's the rest of the loop: these are the exact number of key pressess to do the whole operation, including making the selector go down once (notice the change of the key pressed from numpad6 to 's' halfway through).

![dwbot_1]({{site.baseurl}}/assets/img/dwbot_1.gif)

And with that demonstration we end this first chapter! The next steps will gradually turn the bot into a sentient being! Or something close to that :D

Cheers!

