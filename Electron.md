# Electron

## Apps öffnen sich nicht unter Wayland

- Variable `ELECTRON_OZONE_PLATFORM_HINT=auto` in `/etc/environment` setzen.

- Flatpak Programme brauchen die Berechtigung für `socket=wayland`. Am besten via Flatseal erteilen.