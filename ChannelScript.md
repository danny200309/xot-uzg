# Introduction #

A channel consists of a number of files in a folder. That folder must reside in the Channels folder of the XOT Script. This is an example of the layout:

```
+ Channels
  |    |
  |    + channel1
  |    |    + chn_channel1.py
  |    |    + channel1icon.png
  |    |    + channel1largeicon.png
  |    |    + channel1background.png
  |    |    + channel1background16x9.png
```

**Please notice the channelname (channel1) and the channelscript filename (chn\_channel1.py)**. This is no coincidence! If the folder is named 

&lt;channel&gt;

 the channelscript should be called 

<chn\_channel>

.py!

The channel is completely managed from the 

<chn\_channel>

.py (from now on I will call it chn\_name.py).

# Channel Script #

Let's first have a quick look into the first lines of a chn\_name.py:

```
#===============================================================================
# Import the default modules
#===============================================================================
from cgi import log
import xbmc, xbmcgui 
import sys, os
#===============================================================================
# Make global object available
#===============================================================================
import common
import config
import controls
import contextmenu
import chn_class

logFile = sys.modules['__main__'].globalLogFile
uriHandler = sys.modules['__main__'].globalUriHandler

#===============================================================================
# register the channels
#===============================================================================
register = sys.modules['progwindow']
register.channelRegister.append('chn_name.Channel("xot-channelwindow.xml", config.rootDir, config.skinFolder, channelCode="channelName")')

#===============================================================================
# main Channel Class
#===============================================================================
class Channel(chn_class.Channel):
    #===============================================================================
    # define class variables
    #===============================================================================
    def InitialiseVariables(self):
```
Let's look at some parts:

  1. The first part (_Import the default modules_) is of no interest to us, it is just needed for the working of the script. **Don't edit this part!**
  1. The second part (_Make global object available_) is essential to the chn\_name.py, but not to the user. This part just contains some imports of XOT modules and a mapping to the logFile and uriHandler. **Don't edit this part!**
  1. Then there is the third part: _register the channels_. Now this part is very essential and you can, no you MUST, **edit** it!. It contains the registration of the channel within the XOT Framework! The `register = sys.modules['progwindow']` should always remain, but the second line can be edited. It should look like this: `register.channelRegister.append('chn_name.Channel("xot-channelwindow.xml", config.rootDir, config.skinFolder, channelCode="channelName")')` where `chn_name` is the name of the channelscript file, `xot-channelwindow.xml` the WindowXML file to use with this channel, the `config.rootDir, config.skinFolder` should not be changed and the last part, `channelCode="channelName"` can be used to name your channel (mostly for coding).
  1. The fouth part: _main Channel Class_ is the main channelClass that holds all your code. As you can see (asuming some Python knowledge), it inherits from the `chn_class.Channel`, hence the import `import chn_class`.

The inheritance named under part 4 makes the XOT work with very little coding. The channel only needs the barely necessary methodes to function. All other methodes will be inherited from the `chn_class.py`.

# Channel Script Methodes #

These are the main methodes that are available to you in the chn\_name.py:
```
def InitialiseVariables(self):
def onActionFromContextMenu(self):
def ParseMainList(self):
def CreateEpisodeItem(self, resultSet):
def PreProcessFolderList(self, data):
def CreateFolderItem(self, resultSet):
def CreateVideoItem(self, resultSet):
def UpdateVideoItem(self, item):
def LogOn(self, *args):
```

Let's walk through a normal episode lookup in an XOT script to see how each methode is used:
  1. We start the XOT Script
  1. Channels are registered as was discussed in the previous section
  1. The channels are each initialised and the InitialiseVariables methode is called for each channel.
  1. The _Programm Window_ is displayed.
  1. Here we select a channel from the channel list
  1. Now the_ParseMainList_Methode is used to retrieve the main list of TV Programs
  1. ParseMainList will open the _self.mainListUrl_ and start parsing it using the _self.episodeItemRegex_ Regular Expression.
  1. The returned results will then each be passed on to the_CreateEpisodeItem_methode, which will convert it to a real ListItem and return it.
  1. The listItems are kept in a list which is then displayed on the _Program Window_
  1. Now we select a program
  1. This selection triggers the _Channel Window_ to popup for that specific channel and the URL for the selected program is passed on to the ChannelWindow.
  1. In order to fill the _Channel Window_ with episodes for the programm the url will be opened. The RAW HTML/XML data will then be passed into the_PreProcessFolderList_methode which allows pre-processing. This could be used to retrieve common data (e.g. Category name) that cannot be retrieved from each episode item itself. The methode returns the RAW (or changed) data and a list of Pre-Process item.
  1. That data is then parsed using the _self.folderItemRegex_ and _self.videoItemRegex_ regular expression.
  1. Each resulting match will then be converted to either a FolderItem or an VideoItem using the_CreateFolderItem_and_CreateVideoItem_methode.
  1. The resulting list of Folder and Videos is then displayed in the EpisodeList.
Now 2 things can happen:
  1. When we select a folder from the list, the corresponding URL (which is stored in the listitem) will be fed into the_PreProcessFolderList_method and will continue on just like the example above.
  1. When we select or focus an video item, XOT will check if the item is complete. That is, if all information is available. If not, then the UpdateVideoItem will be used the retrieve the missing data. E.g.1: It could be that the MediaUrl (obtained by the _self.mediaUrlRegex_) can not be obtained immediately, but we need to open an extra url to get it. Now we don't want to open each item's URL to retrieve the corresponding MediaUrl. Therefor we only do this when the item is focussed or selected. E.g.2: same goes for Episode summaries. It could be that they need to be retrieved from a different URL. So that will only be done when the item is focussed or selected. When all information is availabe, but above all the MediaUrl, the episode playback will start.

Now that you know how things basically go, let's look into each of these important methodes in a chronological order:

## def InitialiseVariables(self) ##
_returns nothing_

This methode defines, as it names already indicates, the initial variables. It should be present in each script and contains some very important variables. Below you see a typical IntialiseVariables section. The table under the example explains the different variables. Notice the `chn_class.Channel.InitialiseVariables(self)` call in the first line of code. This calls the IntialiseVariables of the main Channel class and thus initializes all the variables with their default values.

```
#===============================================================================
# define class variables
#===============================================================================
def InitialiseVariables(self):
    """
    Used for the initialisation of user defined parameters. All should be 
    present, but can be adjusted
    """
    # call base function first to ensure all variables are there
    chn_class.Channel.InitialiseVariables(self)
        
    self.contextMenuEnabled = False
    self.icon = ""
    self.iconLarge = ""
    self.noImage = ""
    self.backgroundImage = ""  # if not specified, the one defined in the skin is used
    self.backgroundImage16x9 = ""  # if not specified, the one defined in the skin is used
    self.channelName = "Channel Class"
    self.moduleName = "chn_class.py"
    self.maxXotVersion = "1.0.0"
    self.sortOrder = 255 #max 255 channels
    self.buttonID = 0
        
    self.mainListUri = ""
    self.baseUrl = ""
    self.playerUrl = ""
        
    self.passWord = ""
    self.userName = ""
    self.logonUrl = ""
    self.requiresLogon = False
        
    self.episodeItemRegex = '' # used for the ParseMainList
    self.episodeSort = True
    self.videoItemRegex = ''   # used for the CreateVideoItem 
    self.folderItemRegex = ''  # used for the CreateFolderItem
    self.mediaUrlRegex = ''    # used for the UpdateVideoItem
        
    #========================================================================== 
    # non standard items
        
    return True
```

| **Variable** | **Description** | **Required** | **Values** | **Default** |
|:-------------|:----------------|:-------------|:-----------|:------------|
| **UI Related** |                 |              |            |             |
| self.contextMenuEnabled | Should a contextmenu be available? | True/False   | No         | False       |
| self.icon    | ChannelIcon Filename | Yes          | "Filename.png" | ""          |
| self.iconLarge | LargeChannelIcon Filename | Yes          | "FileNameLarge.png" | ""          |
| self.noImage | Image shown on Episode window when no episode is selected. | No           | "Filename.png | ""          |
| self.backgroundImage | Background image for 4x3 Aspect Ratio. | No           | "Filename.png" | Default Skin Background |
| self.backgroundImage16x9 | Background image for 16x9 Aspect Ratio. | No           | "Filename.png" | Default Skin Background |
| **Code Related** |                 |              |            |             |
| self.channelName | Name of the channel | Yes          | "ChannelName" | ""          |
| self.moduleName | Filename of the module | Yes          | "chn\_name1.py" | ""          |
| self.maxXotVersion | Maximum version of the XOT framework for which this channel will work. If the XOT Framework version is higher than self.maxXotVersion the channel will not be loaded. | Yes          | x.x.x      | 0.0.0       |
| self.sortOrder | Sort Order in main channel window. | No           | 0-255      | 255         |
| self.buttonID | Button ID if the channel should be linked with a button. **CAUTION** Either all channels should have buttons or none. See the [Wiki Buttons](Button.md) Page. | No           | 0-255      | 0           |
| **Url Related** |                 |              |            |             |
| self.mainListUri | The initial URL that is used to parse the mainlist of programms | Yes          | URL        | ""          |
| self.baseUrl | Could be used to simplify the building of URL's instead of typing the complete URL. | No           | URL        | ""          |
| self.playerUrl | Could be used to simplify the building of URL's for playback instead of typing the complete URL. | No           | URL        | ""          |
| **Logon Related** |                 |              |            |             |
|  self.requiresLogon | Whether or not a logon is required. See the Logon Methode. | Ye s         | True/False | False       |
| self.passWord | Password for the Logon (required if self.requiresLogon = True) | No           | "password" | ""          |
| self.userName | Username for the Logon (required if self.requiresLogon = True) | No           | "username" | ""          |
| self.logonUrl | Url for the logon (required if self.requiresLogon = True) | No           | URL        | ""          |
| **Parsing Related** |                 |              |            |             |
| self.episodeSort | Whether or not to sort the _video_ (not folder) items by name | Yes          | True/False | True        |
| self.episodeItemRegex | Regular Expression used for the parsing of MainList Items | Yes          | _Valid Regex_ | ""          |
| self.videoItemRegex | Regular Expression used for the parsing of Video Items | Yes          | _Valid Regex_ | ""          |
| self.folderItemRegex | Regular Expression used for the parsing of Folder Items | Yes          | _Valid Regex_ | ""          |
| self.mediaUrlRegex | Regular Expression used for the parsing of MediaUrl's of Video Items | Yes          | _Valid Regex_ | ""          |

All these parameters are used throughout the complete script. So they need to be correct and complete. Now let's go to the next step.

## def ParseMainList(self) ##
_returns a list of CListItems (in the common.py) to the progwindow.py. The list holds all the programs found in the channel._

In the most simple case, you don't even need to redefine this function. The base ParseMainList from the chn\_class.py parses the_self.mainListUri_using the _episodeItemRegex_ regular expression (although the name would expect it to parse episodes!). For each match the_self.CreateEpisodeItem_methode is called which converts the result in a correct CListItem. Eventually, after each match has been processed by the_self.CreateEpisodeItem,_the complete list is sorted and returned to the_progwindow.py._     In the simple case, the definition of the _episodeItemRegex_ alone should be sufficient.

In a more complex situation, you might need to redefine the ParseMainList method. You don't even have to use the regular expression. The only import thing is that it returns a list of CListItems filled with the programs in the selected channel.

to be continued








