# Apple OSX Tips and Tricks
## Keyboard Shortcuts

<https://github.com/eczarny/spectacle#keyboard-shortcuts>

## Open With default option

1. Select a file.
1. Get info (right click or [CMD] + [I]).
1. Select your text editor under the Open with panel.
1. Click Change all.

<http://superuser.com/questions/578552/osx-stop-xcode-from-opening-ruby-files>

## Window Management

* Spectacle
* BetterTouchTool
	* <https://www.boastr.net/>
* SizeUp
	* <http://www.irradiatedsoftware.com/sizeup/>

### Lock Screen

Ctrl + Shift + Eject

## Tools

Colordiff:
<https://gist.github.com/dansimau/3104183>

Homebrew: <http://apple.stackexchange.com/questions/69223/how-to-replace-mac-os-x-utilities-with-gnu-core-utilities>

## Applications

<http://www.danrodney.com/mac/recommendedprograms.html>

## Hardware

Mac Temperature via Terminal:
<https://www.reddit.com/r/osx/comments/3ehvcc/can_one_check_macs_temperature_via_terminal_os/>

Bluetooth will not turn off:

```
sudo kextunload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport
sudo kextload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport
```

<http://apple.stackexchange.com/questions/110229/bluetooth-corruption-on-2013-macbook-pro>

## Remote Access

Enable VNC remotely:

```
# Turn ON
sudo  /System/Library/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart -activate -configure -access -on -clientopts -setvnclegacy -vnclegacy yes -clientopts -setvncpw -vncpw mypasswd -restart -agent -privs -all

# Turn OFF
sudo /System/Library/CoreServices/RemoteManagement/ARDAgent.app/Contents/Resources/kickstart -deactivate -configure -access -off
```

<http://apple.stackexchange.com/questions/30238/how-to-enable-os-x-screen-sharing-vnc-through-ssh>

## Encryption

* <http://gizmodo.com/how-to-easily-encrypt-files-on-mac-1785467654>

## Time Machine

* Manually delete old time machine backups
	* CLI

		```
		sudo tmutil delete /Volumes/drive_name/Backups.backupdb/old_mac_name
		
		OR
		
		sudo tmutil delete /Volumes/drive_name/Backups.backupdb/mac_name/YYYY-MM-DD-hhmmss
		```
		
	* <http://apple.stackexchange.com/questions/39287/how-can-i-manually-delete-old-backups-to-free-space-for-time-machine/55646>

## Mount HFS+ in Ubuntu

* <http://askubuntu.com/questions/332315/how-to-read-and-write-hfs-journaled-external-hdd-in-ubuntu-without-access-to-os>
* <http://superuser.com/q/84446/152045>

	```
	First, make sure that you have hfsprogs installed. Example installation command:
	
	sudo apt-get install hfsprogs
	
	Next, mount or remount the HFS+ drive; commands need to be as follows:
	
	sudo mount -t hfsplus -o force,rw /dev/sdXY /media/mntpoint
	
	or
	
	sudo mount -t hfsplus -o remount,force,rw /mount/point
	...
	
	Finally, if the drive was improperly unmounted or has otherwise become partially corrupted run fsck.hfsplus ... as such:
	
	sudo fsck.hfsplus -f /dev/sdXY
	```
	
## Troubleshooting

* Busted clipboard: <http://apple.stackexchange.com/questions/31866/copy-and-cut-sometimes-dont-work>

	```
	launchctl list | grep com.apple.pboard
	
	launchctl stop com.apple.pboard
	launchctl start com.apple.pboard
	```
	
* DNS issues, or outdated cache

	Any version of macOS after 10.9.x for the exception of macOS 10.10.1 - 10.10.3 inclusive will use the same two commands to flush the DNS cache which is:

	```
	sudo dscacheutil -flushcache
	sudo killall -HUP mDNSResponder 
	```

	For macOS 10.10.1 - 10.10.3 you can reset the DNS cache by running:

	```
	sudo discoveryutil mdnsflushcache
	sudo discoveryutil udnsflushcaches
	```

	In macOS 10.10 Yosemite, Apple replaced the aging mDNSResponder with discoveryd but many of Apple's customers (including Rackspace) complained to Apple about the many serious bugs discoveryd contained. This was one of the primary reasons it took us almost 3 months before we allowed Rackers to update to macOS 10.10 from macOS 10.9.

	Apple replaced discoveryd and went back to the aging but trusty mDNSResponder in macOS 10.10.4 which is why the syntax changed.
