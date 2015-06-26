# XOT Framework #
_So, you want to use the XOT Framework for your own Online TV Script?_

This can be done and is not too difficult. This small tutorial will give an introduction into the XOT Framework. Bare in mind that the XOT Framework consists of the Framework and channels. This page contains the XOT Framework configuration. The [ChannelScript](ChannelScript.md) page deals with the creation and configuration of the individual channels.

This WIKI page will contain the following items:
  1. XOT Framework Folder and files Layout
  1. XOT Framework Files
  1. XOT Framework Configuration Files
  1. XOT Framework Channel files
  1. and finally the XOT Skinning files

## XOT Framework FolderLayout ##
The XOT Framework has a very specific folderlayout that should be be kept intact:
```
 XOTFramework
  + Cache
  |
  + Channels
  |    |
  |    + Channel1
  |    |    + chn_channel1.py
  |    |    + channel1icon.png
  |    |    + channel1largeicon.png
  |    |    + channel1background.png
  |    |    + channel1background16x9.png
  |    |   
  |    + Channel2
  |    |  
  |    + Channel3
  |    |  
  |    + Etc, Etc, Etc......
  |
  + Libs
  |    + chn_class.py
  |    + common.py    
  |    + config.py
  |    + contextmenu.py
  |    + controls.py
  |    + logger.py
  |    + progwindow.py
  |    + update.py
  |    + uriopener.py 
  | 
  + Skins
  |    + Default
  |    |    + Media
  |    |    + PAL
  |    |    + PAL16x9 
  |    |    
  |    + Skin2
  |    |    + Media
  |    |    + PAL
  |    |    + PAL16x9 
  |    |    
  + default.py
  + default.tbn
  + readme.txt
  + logfile.log
  + logfile.old.log
```
## Framwork Files ##
The main framework is based on a small number of files. These files are very dependent on eachoter and **should not be modified**:

| **Filename** | **Description** |
|:-------------|:----------------|
| default.py   | Default python script that load all other modules and starts the logger and download handler|
| default.tbn  | Button icon for XBMC. Just an renamed .PNG file (Can be changed)|
| readme.txt   | Name says it all|
| logfile.(old.)log| The two logfiles that are being kept. Logfile.log is the most recent one. Logfile.old.log the one from the previous runs|
| chn\_class.py| Base class on which all channel scripts are bases. See [chn\_class](chn_class.md) page for more information|
| common.py    | Library with some common objects|
| contextmenu.py| The name says it all|
| controls.py  | Just constants for mapping to default XBMC actions and Skin objects|
| logger.py    | Custom Logging for XOT|
| progwindow.py | Main XOT window |
| update.py    | Update checker  |
| uriopener.py | Download handler |

So what files can you change? Well, there is only one obvious one left: config.py.

## Configuring your XOT ##

The main configuration is done via the _config.py_ file. Consists of two parts. The first part should not be changed:
```
import os, logging

rootDir = os.getcwd().replace(";","")
if rootDir[-1]!='\\': rootDir=rootDir+'\\'

cacheDir = os.path.join(rootDir,'cache')
if cacheDir[-1]!='\\': cacheDir=cacheDir+'\\'

skinFolder = "" #get's set from default.py
```
The second part is the real configuration part:
```
appName = "Uitzendinggemist.v2"
appSkin = "uzg-progwindow.xml"
contextMenuSkin = "uzg-contextmenu.xml"

logLevel = logging.DEBUG
logDual = True
logFileName = "uzg.log"

version = "2.7.0b3"
updateUrl = "http://www.rieter.net/uitzendinggemist/index.php?currentversion="
```

Most of the items are self explaining. But here are the highlights (remember: python is **capital sensitive** so don't change them):
| logLevel| Minimum level that gets logged. Choices are logging.DEBUG, logging.INFO, logging.ERROR, logging.CRITICAL|
|:--------|:--------------------------------------------------------------------------------------------------------|
| logDual | Log exceptions both in the XOT log and the XBMC log                                                     |
| logFilename| Duh!                                                                                                    |
| version | Current version                                                                                         |
| updateUrl | Url which is contacted for the update check. This url will be called with the currentVersion value and expects '0' if no updates are available or a version number if a version is available|

## ChannelLayout ##
A channel consists of a folder named after the channel, a channel script, an small icon, a largeicon and perhaps some background image. The names of the channelfolder and channelscript are linked: if the folder is called 'abc' the script should be named 'chn\_abc.py', if the folder is called 'sbs6' the script should be named 'chn\_sbs6.py'. The icons files can be given any name, so can the background images.

More configuration options for the channels can be found on the [ChannelScript](ChannelScript.md) Wiki Page.


## Skinning ##
The XOT Framework uses the [WindowXML](http://www.xboxmediacenter.com/wiki/index.php?title=WindowXML) features of XBMC. There are two main windows: the main program window (progwindow.xml) and the episode window (episodewindow.xml). Each window can be modified but some controls are required and thus cannot be removed. For more info on this, see the [Skinning](Skinning.md) page.

Because XOT uses the WindowXML framework, it also supports different skinfiles for different resolutions. More on that you can find on the [XBMC WindowXML](http://www.xboxmediacenter.com/wiki/index.php?title=WindowXML) page.

XOT Supports multiple skins which should all be placed in the _skins_ folder. Each skin folder should have the same name as their corresponding XBMC skin name.

How the XOT Framework determines which **.XML** files to use:
  1. Find the name of the currently used XBMC skin 

&lt;skinfolder&gt;

_1. Look for the file in the_XBMC\skin\

&lt;skinfolder&gt;

_1. Then look for that file in the_\skins\

&lt;skinfolder&gt;

_folder of XOT
  1. If it is found, that folder is used, else_Default_is used_

For the Icons, LargeIcons and Backgrounds of the channels, the XOT Frameworks looks up the location a bit different. How the XOT Framework determines which **.PNG** file to use:
  1. Look for the image in the XOT _\skins\_

&lt;skinfolder&gt;

\Media_folder
  1. Look for the image in the XOT_\channels\

&lt;channelname&gt;

\_folder_

So basically, the the Icons, LargeIcons and Backgrounds should be only specified in the _\channels\_

&lt;channelname&gt;

\_folder, however, if a skin wants to override them, then can be placing the same named file in the_\skins\

&lt;skinfolder&gt;

\Media_folder._






