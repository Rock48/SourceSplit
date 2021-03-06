﻿SourceSplit
===========

SourceSplit is a [LiveSplit] component for Source engine games. It aims to support every game and engine version, but some features are only available on games where support has been added.

Features
--------
  * Keeps track of Game Time to get rid of loading times. Emulates demo timing perfectly.
  * Splits when the map changes. Configurable with map whitelists.
  * Auto start/stop/reset the timer. (supported games only)

Install
-------
Starting with LiveSplit 1.4, you can download and install SourceSplit automatically from within the Splits Editor with just one click. Just type in the name of one of the fully supported games (see below) and click Activate. If your game isn't on the list, try entering "Half-Life 2 Mods". If you want to use your game's real name, you'll have to add SourceSplit to your layout via the Layout Editor instead.

Configure
---------
Click "Settings" and see below. After configuring everything you'll most likely want to turn on game time as primary timing, so that your splits will run off game time. You can do this by right-clicking LiveSplit and going to Compare Against->Game Time.

#### Auto Split
The default settings are fine unless you feel it's splitting too often. In that case you can use the whitelist and add maps you think it should split on completion. Use the delete key to delete items from the list. Note to those unfamiliar with LiveSplit: you must add a split in the Splits Editor for every map it's going to auto-split on.

#### Auto Start/End/Reset
Auto-reset updates your best times without asking, so reset manually if you don't want them updated.

#### Game Processes
You don't need to mess with this unless your game's process isn't listed. All of the fully supported games (and a few others) are added by default.

#### Alternate Timing Method
This makes it show Real Time when comparing against Game Time, and vice versa. Doesn't work when SourceSplit is activated via the Splits Editor. Use [Alternate Timing Method by Dalet] as an alternative.

Fully Supported Games
---------------------
  * Half-Life 2
  * Half-Life 2: Episode One
  * Half-Life 2: Episode Two
  * Portal
  * Portal 2
  * Aperture Tag
  * Portal Stories: Mel
  * (more soon)

Technical Information
---------------------
#### How It Works
Reading game memory and [signature scanning]. This method is used in order to try to support every game and engine version, including ones I've never tested at all. The code would be a lot simpler if it were targetting just one game. A ton of reverse engineering was required to do this. Tools used: IDA Pro, OllyDbg, Source SDK.

#### Timing Accuracy
Note: 1 tick is 15 or 16.666... milliseconds. You can think of it as around the same as one frame at 60FPS. The timing emulates what the engine does when recording a demo.

Many hours were put into making sure the timer is as accurate as possible. For games with auto-start/end support, timing has tick-perfect accuracy >99% of the time. Otherwise timing accuracy depends on the user (start, end), just like RTA.

There are some situations where the timing can be off by a few ticks:

  * If your frame rate is lower than the tick rate, a few ticks can be lost on auto-start/end. 
  * Due to the nature of how SourceSplit reads game memory on a time interval, a few ticks can be lost if it misses the interval.

tl;dr The timing is very accurate and should never be more than half of a second off.

Change Log
----------
https://github.com/fatalis/sourcesplit/releases

Contact
-------
  * [@fatalis_](https://twitter.com/fatalis_)
  * [fatalis.twitch@gmail.com](mailto:fatalis.twitch@gmail.com)
  * [twitch.tv/fatalis_](http://www.twitch.tv/fatalis_)

[PayPal Donate](http://fatalis.pw/donate)

[LiveSplit]:http://livesplit.org/
[signature scanning]:https://wiki.alliedmods.net/Signature_scanning
[Alternate Timing Method by Dalet]:http://livesplit.org/components/
