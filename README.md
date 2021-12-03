# autolvm
*Little udev-triggered automatic volume expansion for VMs*

This script and udev rule 'listen' for new attached block devices on a system and automatically add them to an LVM volume group or specific logical volume per the user's preference.

## Installation

The `autolv_installer.bsx` deploys the changes/script and provides the initial user configuration. (see release notes for installation one-liner)
A default configuration for Turnkey Linux targeting the turnkey volume group and root logical volume is provided, or you can select an existing volume 
group or define a new one, then optionally, you can specify a target logical volume.

## Files Installed

`/etc/udev/rules.d/10-autolvm.rules`  
`/usr/sbin/autolvm`  

## Usage

Once installed and configured, no action is required from the user. `autolvm` can be run to gather information or reconfigure the automatically expanded target at any time.

### Options

`autolvm [ --help | -h | -? ]`  Provides usage and examples  
`autolvm --list`  Displays the current volume group (and optionally logical volume) target  
`autolvm [ VG_name ] [ LV_name ]` Reconfigures the target(s) to the arguments provided  

With no arguments, `--list` will display the current selection(s) and offer reconfiguration. 

## Installation Build

From the build_install folder:

`chmod +x build && build`  This will produce `autolv_installer.bsx` in the build_install folder.
