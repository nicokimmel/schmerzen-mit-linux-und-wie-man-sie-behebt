# Gnome startet manchmal X11 statt Wayland

# Lösungen

- Kernel-Flag `nvidia_drm.modeset=1"` in `/etc/default/grub` setzen. Danach `grub-mkconfig -o /boot/grub/grub.cfg`.

- Module `MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)` in `/etc/mkinitcpio.conf` setzen. Danach `mkinitcpio -P`

- GDM udev Regel mit `ln -s /dev/null /etc/udev/rules.d/61-gdm.rules` löschen.

- Variable `WaylandEnable=false` in `/etc/gdm/custom.conf` auskommentieren oder löschen.

- Variable `MUTTER_DEBUG_KMS_THREAD_TYPE=user` in `/etc/environment` setzen.