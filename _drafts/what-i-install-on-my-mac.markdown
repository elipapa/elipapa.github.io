---
layout: post
title: "What I install on my mac"
date: 2013-03-13 16:09
comments: true
categories: 
---

Until I am invited to give a setup interview, I will simply list it in this blog post:

- mac (bigger screen over portability, you can always get an ipad with a keyboard to travel)
- homebrew
- chrome
- sublime text (i did try emacs and textmate for a long time, but I just need to type, not endlessly configure my setup or hope for a new version of the software that includes the changes i need)


## web development
To serve static files Pow is great and the companion app anvil is pretty great.


To setup Mac OS X for bioinformatics and such:

#To back up and reinstall straight
(should all of this go somewhere online on the cloud ?)
- Address book
- iCal
- ssh folder
- MIT vpn configuration file


#plain text writing and notes
http://www.iawriter.com/mac/screenshots
http://donaldjenkins.net/2010/09/choosing-the-right-dropbox-enabled-text-editor-for-the-mac-ipad-and-iphone-writeroom-ia-writer-and-droptext/
http://antiorario.it/en/orme/2011/05/15/my-writing-tools
http://www.the-soulmen.com/
http://appleink.co.uk/2011/06/16/iawriter-and-notational-velocity/

#dropbox syncs
http://mac.appstorm.net/roundups/internet-roundup/12-popular-mac-apps-you-can-sync-via-dropbox-instructions/
encrypt dropbox folder

## backup to spiderOak
backed up:
- .ssh folder
- keychains
- CVs and resumes
- website


=> textmate license



#Bioinfo
- backup all the data and analysis to beagle's home dir
- move document folder under dropbox ?

#Terminal
IR_black for terminal http://blog.toddwerth.com/entries/show/6
need to clone from github: https://github.com/ciaran/terminalcolours

Use Alt/Option as Meta Key under terminal emulators
For Terminal.app, starting from Snow Leopard: Go to Preferences > Settings > Keyboard > Use option as meta key.
For iTerm: Go to Manage Profiles > Keyboard profiles > (your profile) > Option Key as…

# Time machine
exclude from TimeMachine: applications, movies, downloads, /opt if macports, /usr/local if teX brew, Transmission downloads, Developer Tools, external disks

#birthdays automator
http://code.google.com/p/icalbirthdays/downloads/list

!! skip macports, try homebrew, use mactex for latex

# python   homebrew
http://www.insomnihack.com/?p=442

#Emacs
## install
homebrew installs from source HEAD
need to change the link in /usr/local/bin
instead of a symbolic link to emacs.app, rather build a shell alias. 

This has the advantage that you can pass the normal emacs command line parameters. For some reason symlinking does not work reliably.

set $EDITOR=emacsclient and give it the alias `e` so that it's easy to call it.

## theming
it's done natively with load-theme in emacs24

## packages
using el-get as a package manager for flexibility



# Repos
- Dropbox (and the org files)
- .emacs directory
- .myrc.d directory
- lapofeli scripts


# quicklooks
BetterZipQL.qlgenerator/
Brainsight.qlgenerator/ https://www.rogue-research.com/downloads.html
EPSQLPlugIn.qlgenerator/
Folder.qlgenerator/
QLEnscript.qlgenerator/  http://code.google.com/p/ddribin/downloads/list?q=label:QLEnscript
QLStephen.qlgenerator/  http://whomwah.github.com/qlstephen/
iWork.qlgenerator/
illust.qlgenerator/



# notational velocity data 
1. install it
2. change the directory
2b. decide on DB (encryption,exportable but not editable) vs plain text
3. sync with simplenote

4. install a second instance of it to browse another folder (repeating step 1-3)

- place the repo not in the same folder as the default path ~/Library/Application Support/Notational Data. 
This way you can install a different version of notational velocity and not have it write over the directory. It can be useful if I want to have a NV searching on the org files for eg...

can be synced with IAwriter and the like (on ipad as well)

encrypt with encFS?
sync with dropbox


#libraries
apple development pack (Xcode)

#apps
transmission
mendeley
notational velocity
adobe CS suite (get new one)
pages   keynote (  numbers?)
thunderbird (unless Mail.app works better in leopard)
chrome   firefox   camino
iphoto
quicksilver (or launchbar?)
Dropbox
Cyberduck
formulatePro
Growl
RipIt (Eliseo Papa // 6E1D-ECB1-F2AD-22FA-3E3E)
TinyAlarm
Disk Inventory X
iChm
weka
skype

Virtualbox

Tftpserver
Carbon copy cloner
ScreenFlow (?if snowleopard does not have it already)

Bibdesk   Skim (with latex)

# utilities
Monolingual http://monolingual.sourceforge.net/ - to clean off language packs
Prey http://preyproject.com/download - to localize mac if stolen



## Quick look

I find extremely useful to look at plain text files in quick look. [QLStephen](http://whomwah.github.io/qlstephen/) takes care of that. Simply `mkdir ~/Library/QuickLook/` and copy the downloaded plugin in there. Then run `qlmanage -r` to restart the daemon. To add copy and paste functionality one can type in the terminal:

	defaults write com.apple.finder QLEnableTextSelection -bool true; killall Finder

## Windows management

There are [many](http://apple.stackexchange.com/questions/9659/what-window-management-options-exist-for-os-x) alternatives available but after some testing I prefer using. I wanted simple (or at least configurable) shortcuts (sorry Spectactle.app) and the ability to resize to two thirds of the screen. Multiple monitors support is also nice. Lastly, free is best (otherwise my choice would probably be [Moom]() for the graphical interface to resizing).
While [ShiftIt]() does all of this, it requires X11 installed. So I have tried [Slate]() as a replacement. It is *much* more configurable, which can be an easy productivity trap. Luckily the [default config](https://github.com/jigish/slate/blob/master/Slate/default.slate) has pretty reasonable shortcuts configured. Any modification should really start from the default file, which should be copied first in the home dir:

	cp Slate.app/Contents/Resources/default.slate ~/.slate


