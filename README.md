# Custom DMCS Rules for Foo Fighters

This repository contains my customizations for the DMCS enhancement board for Stern's Foo Fighters pinball.

## DMCS

Short for "Dream Mods Control System", this awesome board allows you to build your own mods to your Stern pinball machines. It allows for customization by using a simple scripting language which can monitor for events like a switch press and trigger a custom rule to control attached devices.

It was created by Pinside user HighVoltage and can find it on the Pinside forums:

* [Foo Fighters DMCS Save Post & Spinning UFO](https://pinside.com/pinball/forum/topic/foo-fighters-dmcs-save-post-and-spinning-ufo-mods)
* [Godzilla DMCS Animated Interactive Backbox Light Kit](https://pinside.com/pinball/forum/topic/godzilla-dmcs-mods-xilien-saucer-heatray-diverter-burning-building)
* [Have Save-post envy playing non-FF game? Try the DMCS Save Diverter!
](https://pinside.com/pinball/forum/topic/have-save-post-envy-playing-non-ff-game-try-the-dmcs-save-diverter)

## Save Post Rule

My rule is an enhancement around the base "Emulate Premium" (`savepost-05.txt`) rule, which is:

* Hit both Sonic Radio standup targets to earn a save post save
* When the left outlane rollover switch is triggered the save post will pop up for 2 seconds

I've added the following features in my version (`savepost-11.txt`):

* Save post is automatically awarded at the start of each ball, as well as after a ball lock when receiving a skill shot opportunity
* RGB indicator strip uses different colors for each sonic radio target (white and red which matches up to the text around the targets) to make it easier to see which you've triggered from your peripherval vision
* RGB indicator strip matches general illumination state (e.g. it turns off when GI turns off)

## Utilities

I built a utility that was useful when debugging my rule.

### RGB Color Picker

I found that RGB color values displayed on a screen didn't quite corelate to RGB LED colors on the indicator strip, so I built `utility-01.txt` which allows for easily previewing colors on the indicator strip.

To use this, you press targets to seperately increment the red, green, or blue value of the color by 10. If you keep a count of the number of times you've pressed each target, when you stop when you have a color your like, you'll have a rough estimate of the RGB value to use.

* Left inlane target: red
* Sonic Radio target (bottom): green
* Sonic Radio target (top): blue
* Right inlane target: clear

So if you press the left inlane switch 5 times, and the bottom sonic radio target once, you'll get a nice amber color which is `rgb(50,10,0)`.
