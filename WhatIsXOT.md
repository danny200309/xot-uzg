# The History #

XOT was born from a XBMC Script called Uitzendinggemist made by somebody called BaKMaN (http://xbox.readrss.com). It allowed playback of the Dutch public TV streams. It was however not kept up to date, so in december 2006 I decided to update the script to have it work again and called it Uitzendinggemist.v2

After some time I started extending the script with a larger history of episodes and eventually added more Dutch channels like RTL 4,5 & 7 and Talpa. As people were so enthusiastic about it more requests came for more channels. Because the original script was not made with the purpose of adding many more channels, I deciced to give the script an overhaul and to make adding a channel more straight forward.

I stripped the complete script and created separate libraries for url-handling, update-checking and logging. I implemented WindowXML which allowed skinning. Removed channels from the main script and gave them their own folder with their own media files. The result is the XOT Framework: XBMC Online TV Framework.

# The Now #

This framework can be used a couple of different ways:
  * Creating your own [channels](ChannelScript.md) and adding them to my XOT-UZG script (the former Uitzendinggemist.v2). You will get stuck with my userinterface and my configuration.
  * Create your own script by using the XOT Framework and [customizing](XOTFramework.md) the configuration and skins.

# The Future #

At this moment a number of (international) channels are on the to do list.

to be continued...