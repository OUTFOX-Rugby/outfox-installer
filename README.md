# OutFox Installer

One-click hosting for the unified OutFox installer (game + controller service + drivers).

**Client link:** https://outfox-rugby.github.io/outfox-installer/

Visiting that URL downloads `outfox-setup.zip` from the latest GitHub Release.
Clients extract it and run `Install-OutFox.bat`.

## Publishing a new installer

The installer zip is **not** committed to this repo — it is hosted as a GitHub Release asset
(the file is ~72 MB and grows with the game build, so a Release keeps the repo lean).

1. Build the bundle (produces `dist/outfox-setup.zip` + `dist/SHA256SUMS`) from the OUT-68 worktree:

   ```pwsh
   pwsh ./install/Build-OutfoxBundle.ps1
   ```

2. Publish a release with the zip attached:

   ```sh
   gh release create vX.Y.Z dist/outfox-setup.zip \
     --repo OUTFOX-Rugby/outfox-installer \
     --title "OutFox Installer vX.Y.Z" \
     --notes "Unified OutFox installer: game + controller service + drivers."
   ```

3. The site links to `releases/latest/download/outfox-setup.zip`, so as long as the asset keeps
   that filename and the release is the newest non-prerelease, the client link never changes —
   no site edit is needed for routine updates.

GitHub Pages redeploys site changes within ~1 minute.
