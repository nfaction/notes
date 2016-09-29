# OS X Bootable USB Installers
## Make OS X USB Installer

```
All steps below MUST be done on a Mac with at least Mavericks installed(10.9)1. Identify USB (OS X Installer will wipe entire drive!!) df -h e.g. /dev/disk2s2    30048176  10556744  19491432    36%  1319591  243642935%   /Volumes/Install OS X Mavericks2. Download El Capitan from Apple App Store (This can also be done forYosemite)3. El Capitan downloads into /Applications4. Install to drive sudo /Applications/Install\ OS\ X\ El\Capitan.app/Contents/Resources/createinstallmedia --volume/Volumes/Install\ OS\ X\ Mavericks --applicationpath /Applications/Install\OS\ X\ El\ Capitan.app --nointeractione.g. IPC-MACHINE:Applications mattd$ sudo /Applications/Install\ OS\ X\ El\Capitan.app/Contents/Resources/createinstallmedia --volume/Volumes/Install\ OS\ X\ Mavericks --applicationpath /Applications/Install\OS\ X\ El\ Capitan.app --nointeraction Password: Erasing Disk: 0%... 10%... 20%... 30%...100%... Copying installer files to disk... Copy complete. Making disk bootable... Copying boot files... Copy complete. Done.5. Look for new volume name: df -he.g. /dev/disk2s2    30048176  12010000  18038176    40%  1501248  225477240%   /Volumes/Install OS X El Capitan6. Eject and Install.  Have fun!
```

## Make OS X ISO

### Sierra
<http://www.insanelymac.com/forum/topic/315967-how-to-create-a-bootable-sierra-iso-for-vmware/>

```
hdiutil attach /Applications/Install\ macOS\ Sierra.app/Contents/SharedSupport/InstallESD.dmg -noverify -nobrowse -mountpoint /Volumes/install_app
hdiutil create -o /tmp/Sierra.cdr -size 7316m -layout SPUD -fs HFS+J
hdiutil attach /tmp/Sierra.cdr.dmg -noverify -nobrowse -mountpoint /Volumes/install_build
asr restore -source /Volumes/install_app/BaseSystem.dmg -target /Volumes/install_build -noprompt -noverify -erase
rm /Volumes/OS\ X\ Base\ System/System/Installation/Packages
cp -rp /Volumes/install_app/Packages /Volumes/OS\ X\ Base\ System/System/Installation/
cp -rp /Volumes/install_app/BaseSystem.chunklist /Volumes/OS\ X\ Base\ System/BaseSystem.chunklist
cp -rp /Volumes/install_app/BaseSystem.dmg /Volumes/OS\ X\ Base\ System/BaseSystem.dmg
hdiutil detach /Volumes/install_app
hdiutil detach /Volumes/OS\ X\ Base\ System/
hdiutil convert /tmp/Sierra.cdr.dmg -format UDTO -o /tmp/Sierra.iso
mv /tmp/Sierra.iso.cdr ~/Desktop/Sierra.iso
```

### El Capitan
<http://www.insanelymac.com/forum/topic/308533-how-to-create-a-bootable-el-capitan-iso-fo-vmware/>

```
 #!/bin/bash
 
 # Mount the installer image
 hdiutil attach /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/SharedSupport/InstallESD.dmg -noverify -nobrowse -mountpoint /Volumes/install_app
 
 # Create the ElCapitan Blank ISO Image of 7316mb with a Single Partition - Apple Partition Map
 hdiutil create -o /tmp/ElCapitan.cdr -size 7316m -layout SPUD -fs HFS+J
 
 # Mount the ElCapitan Blank ISO Image
 hdiutil attach /tmp/ElCapitan.cdr.dmg -noverify -nobrowse -mountpoint /Volumes/install_build
 
 # Restore the Base System into the ElCapitan Blank ISO Image
 asr restore -source /Volumes/install_app/BaseSystem.dmg -target /Volumes/install_build -noprompt -noverify -erase
 
 # Remove Package link and replace with actual files
 rm /Volumes/OS\ X\ Base\ System/System/Installation/Packages
 cp -rp /Volumes/install_app/Packages /Volumes/OS\ X\ Base\ System/System/Installation/
 
 # Copy El Capitan installer dependencies
 cp -rp /Volumes/install_app/BaseSystem.chunklist /Volumes/OS\ X\ Base\ System/BaseSystem.chunklist
 cp -rp /Volumes/install_app/BaseSystem.dmg /Volumes/OS\ X\ Base\ System/BaseSystem.dmg
 
 # Unmount the installer image
 hdiutil detach /Volumes/install_app
 
 # Unmount the ElCapitan ISO Image
 hdiutil detach /Volumes/OS\ X\ Base\ System/
 
 # Convert the ElCapitan ISO Image to ISO/CD master (Optional)
 hdiutil convert /tmp/ElCapitan.cdr.dmg -format UDTO -o /tmp/ElCapitan.iso
 
 # Rename the ElCapitan ISO Image and move it to the desktop
 mv /tmp/ElCapitan.iso.cdr ~/Desktop/ElCapitan.iso
 ```
 
 ## Virtualization for OS X
 
*  <http://hintdesk.com/how-to-install-mac-os-x-sierra-10-12-on-virtualbox/>
*  <https://drive.google.com/drive/u/0/folders/0B52GrzXI5cXhYjduY0V0N0NENW8>