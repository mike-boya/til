# Default Screenshot Location

The default location for screenshots is the desktop. If you take a lot of screenshots,
you will want to send these to a dedicated folder to prevent from cluttering your
desktop. In order to change the default location, run the following commands:


      $ mkdir ~/screenshots
      $ defaults write com.apple.screencapture location ~/screenshots
      $ killall SystemUIServer

One additional item, I added the newly created directory to my favorites in Finder
to save me some time. To set this up, browse to the folder in Finder, then drag and
drop it into the favorites section of your sidebar.
