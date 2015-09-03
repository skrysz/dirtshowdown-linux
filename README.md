# Dirt Showdown

**Official** GitHub page used for tracking issues related to Dirt Showdown on Linux.
Please use this repository for reporting bugs and issues for the game.

# Conduct

This issue tracker is here for reporting bugs and issues ONLY, and some basic rules of conduct apply:

* Do not insult, harrass, or demean any other member or the developers
* Do not start "flame wars"
* Do not use ALL CAPS when creating an issue report.
* Do not intentionally multi-post an issue
* Do not repeatedly update an open issue remarking that the issue persists

We want this to be an effective environment for passing on useful feedback to help us improve the game.
Offenders will be cautioned. Persistent offenders will be banned and reported to GitHub.

# Instructions

Please make sure that you search the open issues before creating a new one to prevent duplicates. Include closed issues in your search as we may have already resolved them.

When reporting a new issue, post the following:

  * A short, descriptive title of the problem
  * A detailed description of the issue, including any relevant output
  * A step by step guide for reproducing the issue, if possible
  * Your system information
  * The game's "eon.txt" log file, which can be found at "~/.local/share/vpltd/dirtshowdown/"

Post your system information as follows:

  * General system info i.e. CPU type/speed, RAM amount etc...
  * Linux Distro, including release version
  * Desktop environment and compositor in use
  * Graphics Card type, including Video RAM amount
  * Graphics driver and version

You can easily retrieve your system specifications using Steam: Help -> System Information. Appropriate output from tools such as "ls /proc/cpuinfo", "lspci" etc are also acceptable.

Please post system info and logs using a [code block](https://guides.github.com/features/mastering-markdown/) or a [gist](https://gist.github.com) where appropriate. gist is generally more appropriate for posting log files.

# Public Betas

Unfortunately we will not be able to offer public betas for this game.

# Announcements

**3 September 2015 14:48 BST - Update (BuildID 761021)**

This update should address the following issues:
* SDLGamepad.config was not being parsed correctly, which meant the mappings described in it had no effect. This has been fixed, and the mapping for PS4 pads has been updated so that the triggers are registered as axes, not buttons.

If you still have problems with controllers after this, you may want to try experimenting with your controllers mappings. In the eon.txt log file you will see entries beginning with "Gamepads:" which is information from the gamepad code about what is happening. As an example, my wired Xbox 360 pad using the xpad driver is detected like this:

```
Gamepads: New potential device at device file '/dev/input/event14'
Gamepads:     New potential device under path '/dev/input/event14' is 'Microsoft X-Box 360 pad'
Gamepads:     Device GUID calculated as: 030000005e0400008e02000014010000
```

You can see the entry for this in SDLGamepad.config. If you are having problems, I'd suggest finding out what Device GUID your controller is detected as, and check its mapping in SDLGamepad.config. You may want to verify it against jstest-gtk or evtest to see if it is correct.

You can also enable extra logging from the gamepad system by passing the command line option ``--eon_log_gamepads``

**1 September 2015 12:11 BST - Update (BuildID 757342)**

This update should address the following issues:
* Fix the loading screen lockups issue on both Linux and Mac
* The Shift key is now definable as an action key on Linux
* Improved gamepad support on Linux to avoid having to calibrate gamepad on every game launch (the old "Don't trust what the driver says" method is still available, by setting ``—eon_calibrate_gamepads`` on the command line)

**21 August 2015 12:53 BST - GitHub tracker now available**

We've opened a GitHub issue tracker for the game. So far we're not aware of any huge issues with this game, but if you have any feel free to let us know here :)
