# netctl-auto-gnome #
This is a Gnome 3 shell extension for [netctl-auto](https://wiki.archlinux.org/index.php/Netctl), the network profile manager for Arch Linux.

This extension was originally the work of Tjaart van der Walt (tjaartvdwalt, netctl-gnome-shell-extension). He has transferred this work to me in order to bring it up to current Gnome shell standards and provide netctl-auto support; I thank him for his past pains.

## Features ##
* Lists all possible wireless network profiles
* Allows selection of active profile at will
* Indicates which profiles are active/unused/disabled
* Provides enable-all/disable-all toggles to turn wifi on/off

**Profile activated**

![screenshot](https://github.com/nigeil/netctl-auto-gnome/blob/master/screenshots/netctl-auto-gnome-screenshot.png?raw=true)

## Dependencies ##
* netctl
* wpa\_actiond (for netctl-auto support)

## Known issues ##
* Need feedback when switching profiles fails.
* Perhaps there is a better mechanism for turning wifi on/off

## Git Hooks ##
* pre-commit
> Reject whitespace errors, and auto-generate zip file ready to upload to the Developer Dashboard.

* Adding git-hooks (through bash)
```bash
for hook in $(git rev-parse --show-toplevel)/*.hook; do
	(cd "$(git rev-parse --show-toplevel)"
		&& ln -s "../../$(basename ${hook})" ".git/hooks/$(basename ${hook%.hook})");
done
```
