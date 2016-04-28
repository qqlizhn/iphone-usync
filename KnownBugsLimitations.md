  * The uSync background crashes sporadically.  This is normal and a workaround is in place to allow the program to continue running despite the background having crashed.

  * Automatic mode (GNUPod) will not sync album art or videos.

  * If a sync is interrupted then a stale lockfile is left so you can't restart it.  This can be fixed by removing the word "Locked" from the sync\_lock file in the /Applications/uSync.app directory on the iPhone.

  * If the IP address of your iPhone or computer changes then the SSH fingerprint might change too which will prevent connecting.  Fix this by logging in manually and SSHing to your computer then back to your iPhone so you can make sure nothing is blocking the connection.

  * Podcasts synced in automatic mode (GNUPod) don't show up in the Podcasts section in the iPod app.  I'm currently playing with some code to make this happen.  It is supported in GNUPod but I couldn't make it work smart enough yet.

  * uSync crashes if I'm using 'Dock'.  libpurple apps are rather buggy.  uSync uses Erica Sadun's utilities (doAlert, doPrompt etc.) for interactivity and since they're libpurple apps they wont run while another libpurple app is running.  This means that if 'Dock' or another libpurple app is already running then uSync will crash since it can't display any dialogs.

  * Only one uSync "server" can be defined per location.

  * Currently it is not possible to choose which songs/podcasts to sync if more than one is available.  It is all or nothing.  This is primarily due to the fact that none of Erica Sadun's utilities are suitable to offer a user-selectable table of items.  As soon as something that fits this need comes available I will implement this.  This could also (and preferrably) be a achieved by writing a simple UIKit frontend to the uSync.sh script.  Since I'm not an Obj-C developer and don't have a toolchain this will have to be left to someone else if there's any interest.