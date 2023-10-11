# WIP Gnome 45 - quick&dirty

## gnome-vrr
Arch PKGBUILD files for Mutter & GNOME Control Center with [Dor Askayo's Wayland VRR MR](https://gitlab.gnome.org/GNOME/mutter/-/merge_requests/1154) applied.
Adopted from [KyleGospo (Fedora)](https://github.com/KyleGospo/gnome-vrr) and [AUR: mutter-vrr](https://aur.archlinux.org/packages/mutter-vrr) + [AUR: gnome-console-center_vrr](https://aur.archlinux.org/packages/gnome-control-center-vrr)

## How to install
git clone or download this repo.
In both folders run

    makepkg -si

or

    makepkg --nocheck -si
    
You possibly have to use nocheck or comment out the check sections.

In a clean VM both packages and their tests are succesful.

Personally I did not switch to Gnome 45 yet and some patches from Fedora are not used, like

    0001-keyboard-Use-new-gnome-desktop-api-for-getting-defau.patch


## New variable needed
    gsettings set org.gnome.mutter experimental-features "['variable-refresh-rate']"
Should be apllied automatically through patches.

## Mouse Cursor fix
1. Disable the use hardware cursor – set the MUTTER_DEBUG_DISABLE_HW_CURSORS=1 environment variable.
2. Disable the use of the atomic KMS API – set the MUTTER_DEBUG_FORCE_KMS_MODE=simple environment variable.
