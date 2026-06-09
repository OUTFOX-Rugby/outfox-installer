# Outfox Controller Updater

One-click hosting for the Outfox controller self-heal installer.

**Client link:** https://outfox-rugby.github.io/outfox-updater/

Visiting that URL automatically downloads `Outfox Installer.bat`, which force-binds
and self-heals the 7 wired Xbox controllers (WinUSB + watchdog scheduled tasks).

## Updating the installer

To ship a new version, replace the `.bat` and push — the link never changes:

```sh
cp "../DriverGuardian/dist/Outfox Installer.bat" Outfox-Installer.bat
git commit -am "Update installer"
git push
```

GitHub Pages redeploys within ~1 minute. Clients always get the latest file from the same URL.
