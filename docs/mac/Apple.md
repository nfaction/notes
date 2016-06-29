# Apple OSX Tips and Tricks
## Keyboard Shortcuts

<https://github.com/eczarny/spectacle#keyboard-shortcuts>

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

