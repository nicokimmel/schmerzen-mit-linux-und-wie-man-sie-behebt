# Gnome

## Gnome startet manchmal X11 statt Wayland

- Kernel-Flag `nvidia_drm.modeset=1` in `/etc/default/grub` setzen. Danach `grub-mkconfig -o /boot/grub/grub.cfg`.

- Module `MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)` in `/etc/mkinitcpio.conf` setzen. Danach `mkinitcpio -P`

- GDM udev Regel mit `ln -s /dev/null /etc/udev/rules.d/61-gdm.rules` löschen.

- Variable `WaylandEnable=false` in `/etc/gdm/custom.conf` auskommentieren oder löschen.

- Variable `MUTTER_DEBUG_KMS_THREAD_TYPE=user` in `/etc/environment` setzen.

## Theme in manchen Fenstern passt icht zum Rest

- In den Gnome "Erweiterungen" `User Themes` aktivieren. Dann in `gnome-tweaks` [adw-gtk3](https://github.com/lassekongo83/adw-gtk3) als Theme für veraltete Programme einstellen. Flatpak nicht vergessen.

## VSCode öffnet sich statt Wechseldatenträger

- Datei `~/.config/mimeapps.list` editieren und `inode/directory=org.gnome.Nautilus.desktop` einfügen.

## Picture-in-Picture bleibt nicht im Vordergrund

- Gnome Erweiterung "PiP on top" installieren
