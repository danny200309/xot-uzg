# Changelog #
## Changelog v3.2.0b7 - 2010-01-26 (Needs at least XBMC revision [R17016](https://code.google.com/p/xot-uzg/source/detail?r=17016)) ##
  * Removed: Kanalenkiezer for the time being, because they start to link to HTML more and more
  * Fixed: Turbo Nick RTMP urls
  * Fixed: Freecaster.tv
  * Updated: SVT to handel AJAX calls beter ([Issue 151](https://code.google.com/p/xot-uzg/issues/detail?id=151))
  * Added: Confluence Skin
  * Fixed: added some code to make sure XOT updater does not suffer from a googelcode-page bug
  * Fixed: Bug with closing of progressbar
  * Added: Contextmenu Close support

## Changelog v3.2.0b6 - 2009-11-26 (Needs at least XBMC rev17016) ##
  * Fixed: Fine tuned SVT regex's
  * Fixed: SVT.se channel could not handle rtmpe (thanks to Stefan Nilsson)
  * Added: Viasat Sport (thanks to fldc @ XBMC.org)
  * Added: TV3, TV6 and TV8.se
  * Fixed: RTL channel more compatible with XBMC Win32/Linux (Thanks to Menno). Still long loading times
  * Fixed: Freecaster.tv channel
  * Fixed: Plugin broke with new XBMC version
  * Fixed: Loging broke with new XBMC version
  * Fixed: bug with logging of mediaitem
  * Added: MiniMeedia skin
  * Changed: Xbox Media Center into XBMC Media Center
  * Updated: Logo's
  * Updated: Build Scripts

## Changelog v3.2.0b5 - 2009-05-07 (Needs at least XBMC rev17016) ##
  * Added: TV3.se and TV6.se
  * Fixed: Freecaster.tv
  * Added: proxy support
  * Fixed: eq could not handle None objects
  * Fixed: plugin did not work because of eq bug.

## Changelog v3.2.0b4 - 2009-04-28  Needs at least XBMC revision [R17016](https://code.google.com/p/xot-uzg/source/detail?r=17016)  ##
  * Added: TV3.se and TV6.se
  * Fixed: RTL 4,5,7&8 channel
  * Removed: PCZapper SBS6
  * Added: Freecaster.tv
  * Fixed: SVT.se channel.
  * Fixed: 123Video now detects correct mediaserver
  * Fixed: De Lama's channel
  * Added: TurboNick
  * Fixed: MTV.nl Channel
  * Fixed: Southpark channel (partly)
  * Fixed: NOS channels
  * Added: Unicode support (fixed scrambling of special characters)
  * Added: Minor improvements to UI and added Events
  * Added: detection of duplicate GUIDs of channels. The duplicate is removed and error is logged
  * Added: Helpers library
  * Added: HtmlEntityHelper class.
  * Fixed: Default Skin scroll
  * Renamed: clistItem to MediaItem

## Changelog v3.2.0b3 - 2009-01-23  Needs at least XBMC revision [R17016](https://code.google.com/p/xot-uzg/source/detail?r=17016)  ##
  * Added: MediaStream skin (thanks to Poeier from tweakers.net)
  * Fixed: RTL channel
  * Added: better sorting of items (date still needs some tweaking)
  * Added: Mouseclick support (Requires Rev 17016)
  * Added: Z@PP Channel
  * Fixed: SVT Channel

## Changelog v3.2.0b2 - 2008-11-24 Needs at least XBMC revision [R14899](https://code.google.com/p/xot-uzg/source/detail?r=14899)  ##
  * Updated: SVT.se
  * Fixed: mediaUrl error in Plugin
  * Fixed: Environment always showed Win32 even on xbox. Now it imports win32 but displays XBOX
  * Fixed: Icon had bad pixels
  * Changed: entity-converter did not work if entities had capitals
  * Fixed: Regex for NET5/SBS6 and Veronica (Again)
  * Added: NOS Top 50
  * Fixed: RTL now loads the additional programms better
  * Fixed: Regex for NET5/SBS6 and Veronica
  * Added: Paging to NET5/SBS6 and Veronica

## Changelog v3.2.0b1 - 2008-09-29 Needs at least XBMC revision [R14899](https://code.google.com/p/xot-uzg/source/detail?r=14899)  ##
  * Added: Official southpark channel
  * Fixed: RTL Channel adjusted to new RTL Player
  * Added: new environment detecting
  * Added: 64bit support
  * Fixed: NOS Channel adjustments for new url layout (and future use of WMC)
  * Fixed: Plugin for multiple mediaurls

## Changelog v3.2.0a3 - 2008-09-04 Needs at least XBMC revision [R14899](https://code.google.com/p/xot-uzg/source/detail?r=14899)  ##
  * Fixed: Linux Logging
  * Fixed: Linux pal -> PAL in skin folder names

## Changelog v3.2.0a2 - 2008-09-02 Needs at least XBMC revision [R14899](https://code.google.com/p/xot-uzg/source/detail?r=14899)  ##
  * Fixed: path issues with Linux. os.path.join is used now everywhere.
  * Fixed: SBS6nl channel
  * Fixed: RTL457&8 channel
  * Added: Environment detection and OS dependend packages (idea taken from AMT)

## Changelog v3.2.0a1 - 2008-08-19 Needs at least XBMC revision [R14899](https://code.google.com/p/xot-uzg/source/detail?r=14899)  ##
  * Fixed: NOS channel needed fixing because of new check on the website.
  * Fixed: quickfix for unexplainable clearing of channellist
  * Changed: layout of script folder to support WindowXML rev14899
  * Fixed: MyVideo regex
  * Fixed: some more syntax issues
  * Changed: User Agent for URLLib is now XOT/3.0 (compatible; XBMC; U)
  * Removed: Unneeded imports
  * Fixed: RTL changed their layout
  * Fixed: Regex changed for Kanalenkiezer
  * Changed: Veronica channel needed multiple fixes (FLV detection)
  * Changed: Favorites now use ChannelGUID for identification
  * Added: GUID for each channel used for identification.
  * Added: bitrate selection of RTL streams
  * Updated: SVT.se image
  * Updated: Donations updated in readme.txt

## Changelog v3.1.0 - 2008-05-07 (Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)) ##
  * Added: Auto Channel Updater
  * Changed: update now has a verbose option to also show a message if no update was available
  * Fixed: www.uitzendinggemist.nl introduced a SecurityCode to obtain the mediaurl. For now it is fixed by loading an extra page that holds that code.
  * Fixed: Regex for results in NOS Zoeken fine-tuned
  * Fixed: Dumpert.nl MediaUrlRegex
  * Fixed: Pagecontrols where showing for channel description labels
  * Added: Official SBS6.nl channel. The previous one now has PCZapper in it's name and description
  * Added: NET5 from www.net5.nl
  * Added: Veronicatv.nl
  * Fixed: Cosmetic changes to contextmenu
  * Added: self.defaultPlayer option to channels
  * Changed: Prevent addition of duplicate items in Mainlist
  * Added: more debugging info if an AttributeError occurs after importing libraries. This should give more information on what went wrong.
  * Fixed: on some XBox systems the timeout of on Open action would occur immediately due to a problem with the threading.join() method. (Thanks to Arnova [tweakers.net])
  * Fixed: Caching of thumb would not return the default self.NoImage if an exception occured.
  * Changed: GuiController now ignores exceptions that occur when non essential controls are missing from the skin file (like the channelinfo controls and rating controls).
  * Fixed: Contextmenu had disappeared in some channels
  * Fixed: RTL XML Layout changed

## Changelog v3.0.1 - 2008-03-10 Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)  ##
  * Added: more download algorithms
  * Added: more support for quicksilverscreen.com
  * Added: people who donated
  * Fixed: Searchregex www.uitzendinggemist.nl was not correct
  * Added: Swedish television SVT.se
  * Added: BeautifulSoup support via common.DoSoupFindAll
  * Added: chn\_class.py now accepts lists/tuples for playback. They will be converted to playlists
  * Changed: maxVersion to 3.0.1
  * Added: MyVideos.nl
  * Added: new pagenavigation images
  * Added: favorites now go into Database file
  * Added: sqlite2 library
  * Changed: context menu now uses onClick and works with mouse
  * Fixed: Crash on detection of script/plugin from within XBMC for Linux
  * Fixed: Crash on mouse movement when mouse is not over a control in ProgWindow.
  * Fixed: UrlJoin used for url creation in CreatePageItem
  * Fixed: GuiController check self.PluginMode
  * Added: Page support in XOT Plugin (they show as folders)
  * Added: XBMC version and compile date in Directory Printer
  * Changed: scrolling through pagelist now also allows from top -> bottom jump
  * Fixed: UZG changed their layout. ParseMainList now parses multiple pages

## Changelog v3.0.0 - 2008-01-28 Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)  ##
  * Fixed: issue with getFocus() for GUI types that are XBMCGUI specific.
  * Changed: Item is now first pushed onto the history stack before fetching of new items, so the parent item can be called via the history stack (for descriptions for instance)
  * Changed: sort-order of Lama's channel
  * Added: Quicksilverscreen.com channel
  * Added: Ratings
  * Changed: Modified the www.uitzendinggemist.nl search channel to a 'specials' channel including search, popular items, newly added items, etc..etc..

## Changelog v3.0.0b2 - 2008-01-07 Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)  ##
  * Fixed: issue with getFocus() for GUI types that are XBMCGUI specific.
  * Fixed: Minor issue on NOS Page handling
  * Fixed: Progressbar dissappeared in NOS channel
  * Added: Favorites can now be every folder in each channel.
  * Changed: ContextMenu is moved from Channel to ChannelClass. In the Channel now has a self.contextMenuItems which is a list of ContextMenu.ContextMenuItems. Each item has a label, a callback function and an indication wether it should show on video/folder/completed items.
  * Added: Favorites
  * Added: Settings.xml
  * Added: contextmenu to 123video
  * Added: 123Videos.nl
  * Changed: chn\_nos - NOS now only retrieves recent items and displays an archive folder with older items

## Changelog v3.0.0b1 - 2007-12-23 Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)  ##
  * Fixed: Kanalenkiezer.nl is now working again
  * Changed: Dumpert.nl icons renamed
  * Changed: 'De Lama's' Channel changed to not retrieve 1000 items, but only 500. This should solve timeouts opening the channel.
  * Fixed: Text not appearing in textboxes
  * Added: Better handling of xbmcplugin interface.
  * Changed: Fixed some overlaps in skins.

## Changelog v3.0.0a1 - 2007-11-26 Needs at least XBMC revision [R10008](https://code.google.com/p/xot-uzg/source/detail?r=10008)  ##
  * Added: Caching of items. On 'back' items are retrieved from the cache! This reduces the URL lookups dramatically
  * Added: self.pluginMode, if in plugin-mode, this variable is True
  * Added: initPlugin method to Channel. This one can be used to do the initialisation of a channel. Remember to add the self.pluginMode = True to this part.
  * Added: item.Downloadable indicates whether an item is downloadable. Should be used in the future to determine if it can be downloaded or not.
  * Added: Plugin support (dates still missing in listing)
  * Added: Dumpert.nl channel
  * Changed: had to remove some UI related stuff from the channels, to make sure they would work as a plugin.
  * Changed: channels may NOT contain any reference to objects of the XOT-Script UI. If they do, make sure to not adres them when in script mode.
  * Fixed: Joox.net channel
  * Added: if mediaurl is not filled in updatevideo, the item is always marked als not complete
  * Fixed: date is now grey when item is not selected in progwindow
  * Changed: mplayer and dvdplayer can now be selected explicitly. Defaults to the default XBMC player.

## Changelog v2.7.0 - 2007-10-12 Needs at least XBMC revision [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683) ##
  * Added: Cachefolder cleanup
  * Added: New GTST episodes to RTL channel
  * Added: Channelnames in Programwindow
  * Added: Channeldescriptions in Programwindow
  * Added: Channeldescriptions to all channels
  * Added: item=complete checkmark
  * Fixed: RTL Error in Regex due to changes in XML layout
  * Changed: renamed self.onUpDownEnabled to self.onUpDownUpdateEnabled for better displaying its function
  * Added: Lama's channel
  * Added: self.CacheThumb to chn\_class.py to automate the caching of thumbs

## Changelog v2.7.0b6 - 2007-10-05 (Needs at least XBMC revision [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Fixed: RTL script updated for GTST (ParseMainList adds an extra item: GTST)
  * Fixed: RTL script updated. The XML layout changed a bit.
  * Added: an user agent to the uriopener (thanks to VincePirez @ xbmc forums)
  * Fixed: SBS Regex
  * Added: Date for programs in progwindow
  * Added: Option to disable sorting alphabetically and sort by date
  * Fixed: layout of Kanalenkiezer.nl changed. Had to adjust the regular expressions and urls.
  * Changed: no URL fetching on item selection. Only on click! (Done using the self.onUpDownEnabled = False).
  * Added: when self.onUpDownEnabled = False and ignore = False then only the data is shown and no update is done of the videoitem.

## Changelog v2.7.0b5 - 2007-09-01 (Needs at least XBMC revision [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Changed: no onupdown for TVLink until the issues are fixed. Now update via contextmenu
  * Added: onUpDownEnabled to Channel settings and onUpDown(ignoreDisabled=True/False)
  * Added: Controlgroup for onUpDown to controls.py
  * Changed: self.initialUri to self.mainListUri. self.intialUri still exists, but is set when the Episode window opens (ShowEpisodeWindow)
  * Added: Progressbar for filling lists larger than 50 items
  * Added: Canceling of URL opening even if no data is comming in
  * Removed: Talpa as it now is RTL8
  * Added: Locking mechanisme to prevent multiple background updates (very Experimental)


## Changelog v2.7.0b4 - 2007-08-06 (Needs at least XBMC revision [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Fixed: 

&lt;string&gt;

 error in XBMC log due to XOT logger
  * Added: Print directory of script on startup for debugging options
  * Fixed: KK channels where out of sync due to webpage layout!
  * Added: Locking for video update
  * Added: Don't break on not resolving www.rieter.net
  * Fixed: No more frenzy internet lookups: onUpDown now only starts after last onUp in 500ms
  * Changed: uriOpener now has private variables for methodes to prevent multithread  problems
  * Added: New backgrounds for RTL, SBS and Talpa
  * Added: ConvertURLEntity and ConvertHTMLEntity in common.py (replacing StripHTML)
  * Added: maxXotVerison to channels. If XOT updates older channels may lead to conflicts, so they won't be loaded then.
  * Added: TV-Link.co.uk support (needs more file type detection)
  * Fixed: Changing list position while loading first item would lead to wrongly display item info on the newly selected one.
  * Added: Default compare value in progwindow channel comparison
  * Added: UriOpener.Header now also returns the real url after redirection

## Changelog v2.7.0b3 2007-07-28 (Requires at least XBMC [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##

  * Added: Code.google.com page: http://code.google.com/p/xot-uzg/
  * Changed: Uitzendinggemist.v2 will be called XOT:Uzg (XBMC Online TV: Uitzendinggemst)
  * Changed: UZG is now based on seperate framework called: XOT (XBMC Online TV)
  * Added: Custom sorting of channels using SortOrder property
  * Changed: Chn\_class.py is now completely UZG free
  * Changed: Media files that do not explicitly belong to UZG are renamed from uzg_to xot_
  * Changed: Progwindow Skin
  * Fixed: Visibility on Panel now works
  * Added: Checking if image is present in SkinFolder. If it is present, that one is used, else the file in the channel folder is used
  * Changed: Media of channels now in channelfolder OR in skinfolder. The latter overwrites the former (skinfolder is the most important location).
  * Changed: Each channel has its own folder now: chn\_name.py has to be located \name\chn\_name.py
  * Changed: Moved chn\_class to libs.
  * Added: New skin for progwindow
  * Added: Control groups for up/down and exit/back
  * Changed: Graphics for channels
  * Added: Possibility to have both a list of channels and buttons. Nr of buttons must be equal to number of channels
  * Changed: Register items to 'channelSelect -> channelRegister'
  * Changed: buttons are now registered from within the channelClass
  * Added: Dynamically load channels
  * Changed: Contextmenu and progwindow skin-name in config.sys
  * Changed: More UZG-name related stuff into the config.py
  * Added: appName to config.py
  * Changed: UpdateUrl now in config.py
  * Changed: UzgLog to logFile (for general purpose)

## Changelog v2.7.0b2 2007-07-14 (Requires at least XBMC [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Removed: Some unneccessary imports
  * Added: UZG Logger class, not based on Python logging
  * Added: option to log exceptions in both UZG and XBMC log
  * Added: GUID for identification of cListItems
  * Added: Uriopener checks if filenames are in correct xfat format now
  * Fixed: Some bugs in Uriopener
  * Changed: Joox regex
  * Added: .flv detection to SBS6/PCZapper script

## Changelog v2.7.0b1 2007-07-02 (Requires at least XBMC [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Added: registration of all channels in their own chn\_name.py
  * Removed: PMIII skin. Now defaults to Default
  * Added: SBS6 support (from pczapper.tv)
  * Added: Progressbar information while opening
  * Added: complete contextmenu support (used AMT for inspiration but changed a lot). Menu is triggered by the Info Key/Button
  * Changed: renamed skin xml files to uzg-windowname.xml ("uzg-" added)
  * Added: ClearityMod skin
  * Fixed: MC360 skin
  * Added: config.py with all config stuff
  * Added: controls.py with all control and window ID's
  * Changed: Joox download enabled. Defaults to Cache Dir and uses item name as filename.
  * Changed: moved first load of www.uitzendinggemist.nl from default.py to chn\_nos.py and added cookie check to chn\_nos.py.
  * Fixed: integer instead of float value to progressbar dialog (float is decrepated)
  * Fixed: Minor bug playing KK streams
  * Changed: logging now happens in the 'uzg.log' file in the script folder of UZG. The logfile from the previous session is named 'uzg.old.log'.
  * Added: MultiLine Logger Class with Exception Handling
  * Changed: NOS Search now accepts multiple characters.

## Changelog v2.6.x 2007-06-20 (Requires at least XBMC [R8683](https://code.google.com/p/xot-uzg/source/detail?r=8683)) ##
  * Added: Joox Support
  * Added: Version Checking
  * Changed: UriOpener now has False as default. Only True on data retrieval
  * Fixed: Skin list scrolling
  * Fixed: uriopener did not open file if filesize was smaller than chucksize
  * Changed: cleanup of uriopen method. Also adding more debuginfo
  * Changed: ListItem methodes to comply with XBMC [R9198](https://code.google.com/p/xot-uzg/source/detail?r=9198)
  * Fixed: wrong tag in skin XML-Files
  * Fixed: re-initialisation of episode window after video playback
  * Fixed: MC360 skin
  * Changed: New Skinlayout, first draft
  * Fixed: Initialisation of Talpa-window continued even when login failed.
  * Added: The "Concept" skin.
  * Fixed: Errors due to very large amounts of URL's queueing up when scrolling an episode list fast.
  * Added: Talpa.tv Uitzendinggemist Support(READ 4.a below)

## Changelog v2.5.x 2007-05-16 (Requires WindowXML compatible XBMC) ##
  * Fixed: Problem with image-links in Default skin. Prevented correct display of images when the default skin was selected.
  * Added: PMIII skin.
  * Fixed: RTL 4,5&7 streams were not working due to server changes at RTL.
  * Fixed: Pixel column at left side of button removed.
  * Added: initial MC360 skin support (Still needs testing)
  * Changed: More NOS Uitzendinggemist history. All episodes present on the site should now be visible.
  * Fixed: cleaning of URL with &amp; insided the url.
  * Added: common.py has ID's for the used controls defined in channelwindow.xml.
  * Added: windowxml skinning support (See further down for more notes).
  * Changed: icons for channels/episodes
  * Changed: more robust checking for streams in Kanalenkiezer. Html is now filtered out before playback (had to check HTTP first) to prevent problems with mplayer.
  * Changed: location of constants changed to the channel-libary files.
  * Changed: all constants in CAPITALS, variable in camelCase and methodes in PascalCase

## Changelog v2.4.x 2007-04-24 ##
  * Changed: to make things a bit more easy to maintain I changed from a single default.py to multiple files.
  * Added: seperate python scripts for libraries (libs), channels and a default.py.
  * Changed: each channel has it's own python file with instructions.
  * Fixed: on some systems the Cache dir was not present which prevented the script from running! Checking this now on startup.
  * Added: BETA support for www.kanalenkiezer.nl
  * Changed: search algorithm for www.uitzendinggemist.nl

## Changelog v2.3.x 2007-04-09 ##
  * Fixed: lookup string was wrong due to missing Q, X and Y.
  * Fixed: no episodes were displayed if no date was found for episodes.
  * Added: Searching for NED1,2&3. Only one symbol can be used to search. Others will be neglected.

## Changelog v2.2.x 2007-04-09 ##
  * Added: Progressbar support while loading an URL

## Changelog v2.1.x 2007-04-03 ##
  * Fixed: scaling bug when using HD resolutions
  * Added: parsing of ASX/ASF for compatibility with older XBMC versions
  * Added: first support for RTL 4,5 & 7 (please use the XBMC forum link to let me know if there are bugs)
  * Added: icons for folders/video-files

## Changelog v2.0.x 2007-03-30 ##
  * Added: animations
  * Changed: tabs instead of spaces for indentation
  * Added: readme.txt
  * Fixed: now again working with www.uitzendinggemist.nl
  * Fixed: working ASF streams
  * Added: support for multiple episodes of a programm
  * Changed: split window-class into to parts: program-window and episode-window
  * Added: new background
  * Changed: layout
  * Fixed: display most recent programms, instead of the first in alphabetical ranking