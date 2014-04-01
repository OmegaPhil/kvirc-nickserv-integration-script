NickServ Integration Script is an attempt to implement complete automated NickServ identification and ghosting, replacing KVIrc's NickServ tool. So far I use this to maintain my primary nick on:

* BCnet
* freenode
* Immortal-Anime
* Irc2P
* IRCHighway
* LostIRC
* P2P-NET

Please let me know if you have success with other networks.

Note that ident passwords are saved in plaintext by this script.

Last updated on 1.04.14 for v1.2.


Installation
============

To load the script into KVIrc (which then persists until you uninstall) and run its startup alias, in a KVIrc console window:

    /parse <path to script file, speechmark-delimited if the path contains spaces>
    /NickServIntegrationScript::Startup

Once the script is installed, NickServIntegrationScript::Startup is automatically called when KVIrc is started.


Dependencies
============

This script depends on the Common Scripting Services script, see the [Github repo](https://github.com/OmegaPhil/kvirc-common-scripting-services).


Uninstallation
==============

In a KVIrc console window:

    /NickServIntegrationScript::uninstall::uninstall


General Use And Configuration
=============================

Firstly, ensure that the current KVIrc NickServ functionality doesn't conflict with this script - in KVIrc preferences, go IRC -> Tools -> NickServ and disable NickServ Identification (or at least disable/remove the rules that you want this script to take on).

The 'Scripts' menu is created on the main KVIrc menubar, which then hosts the NickServ Integration Script menu. This allows you to turn the script on/off, add/edit/remove networks and report on the current configuration:

![Script menu](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7461/script-menu.png)

Add network dialog:

![Add network dialog](https://f92fac806bf10a96c0b8-8a0a46e5f1a5cc9854958bc3503f0f88.ssl.cf1.rackcdn.com/media_entries/7462/add-network-dialog.png)

The primary nick is used to detect when the server has forced you to use a different one - the script attempts to change your nick back, and upon meeting resistance ghosts whatever has your nick and/or parts any channel that tries to prevent you from changing nick (the latter happens when you/everyone is banned on a particular channel).

'Network supports cs/ns shortcut' allows you to instruct this script to use the relevant shortcut command to address ChanServ/NickServ. These commands are more secure than the normal option of sending a private message to the user holding the relevant nick (which you hope is the genuine ChanServ/NickServ). To see if your network supports these shortcuts, try the following commands in the console window:

    /cs help
    /ns help

If the server responds with 'Unknown command' then the command is not supported and this checkbox should be left off.

Edit network dialog:

![Edit network dialog]()

Works in the same way as the add network dialog.

Remove network dialog:

![Remove network dialog]()

Select the network you no longer want the script to manage and remove it.

'List details of particular network' pops up an identical dialog - use it to select the relevant network - the details are echoed to the current window. 'List all networks with recorded details' outputs everything to the current window without using a dialog.


Alias/Scripting Usage
=====================

The script is fully commented so should be fairly accessible for those wanting to see how to take its use further - for alias usage, see comments preceeding the alias, or run the alias without parameters for help/errors.


Development
===========

Try out my modification of the [geany](http://www.geany.org/) IDE, extending it to syntax highlight, parse KVIrc Script for aliases, events, variables, shortcut for loading scripts into KVIrc etc: [Github documentation](https://github.com/OmegaPhil/geany-kvircscript/wiki/README---KVIrc-Script-Integration).


Bugs And Feature Requests
=========================

Please create an issue on the [Github issue tracker](https://github.com/OmegaPhil/kvirc-nickserv-integration-script/issues).


Contact Details
===============

OmegaPhil+KVIrc.Script@gmail.com
