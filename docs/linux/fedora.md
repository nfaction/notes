# Fedora

## Installation

* <https://fedoraproject.org/wiki/How_to_create_and_use_Live_USB>

### Mac OS X USB Maker

1. Download a Fedora image, choose a USB stick that does not contain any data you need, and connect it
1. Open a terminal
1. Run `diskutil list`. This will list all disks connected to the system, as `/dev/rdisk1`, `/dev/rdisk2` and so on. Identify - very carefully! - which one corresponds to the USB stick you wish to use. Hereafter, we'll assume it was `/dev/rdisk2` - modify the commands as appropriate for your stick.
1. Run `diskutil unmountDisk /dev/rdisk2
1. Type `dd if=`, then drag and drop the Fedora image file to the terminal window - this should result in its filesystem location being appended to the command. Now complete the command with `of=/dev/rdisk2 bs=1m`, but don't hit Enter yet. You should wind up with something like `sudo dd if=/Volumes/Images/Fedora-Live-Desktop-x86_64-20-1.iso of=/dev/rdisk2 bs=1m`
1. Double-check you have the correct disk number and you're really, really sure you don't need any of the data on the USB stick!
1. Hit Enter
1. Wait for the operation to complete, then reboot your computer, and hold down the left Alt/Option key to access the boot menu - you should see a Fedora logo. Click this to boot.

## Upgrade

<https://fedoraproject.org/wiki/DNF_system_upgrade>

## Containerization

### Nspawn

<https://rich0gentoo.wordpress.com/2014/07/14/quick-systemd-nspawn-guide/>


## Random Notes

```
Fedora kvm/qemu
Kölker runs ZFS, I roll LVM. We argue about it ;)

And then I have a VM on there for systemd nspawn containers
I mean I could probably do cent os also, just fedora is newer

It's stable outright but I for example just have minimal fedora with zfs drop my nspawn containers for everything else on the zfs filesystem
Not tons can go wrong there
With that setup even if fedora shits the bed you reinstall it and zfs.. import you zfs file system and you are back up and running

For my use cases nspawn is totes and easier to use

Definitely depends. If you run systemd in the container also, nspawn is totes, and is easier to configure for sure cause you can just console in to it
Instead of the docker process container + disk container strategy

socket activated containers
i'm still looking for a good reason to make that a thing
keep this in mind as you build things

fedora 24 w/ ZFS

so i did a minimal manual install, i also do ZFS boot too since i'm a masocist
so i have multiple dnf installed boot envs for it

when i want to upgrade i just snap it and dnf upgrade
```