# Cinder Launcher Downloads

Public profile catalog and launcher-owned configuration files for Cinder Launcher.

## Manifest URL used by Cinder Launcher

`https://raw.githubusercontent.com/purplux01/cinder-launcher-downloads/main/cinder-manifest.json`

Keep `cinder-manifest.json` in the repository root. Cinder Launcher 0.3.0 expects `schemaVersion: 1` and profile entries using `type: "vanilla"` or `type: "fabric"`.

## What belongs here

- `cinder-manifest.json`: the catalog Cinder reads for profile presets.
- `profiles/`: optional documentation/profile descriptors you own.
- `configs/`: your own launcher or instance configuration templates.
- `assets/`: artwork you created or have permission to distribute.
- `modpacks/`: documentation and links for packages you're permitted to share.
- `schema/`: JSON schema used to validate the manifest.

## Do not upload proprietary game files

Do not commit Minecraft client JARs, game assets, libraries, or other proprietary Minecraft files. Minecraft's usage rules restrict redistribution of game files. Cinder downloads the selected game components from Mojang's official version metadata and download URLs. Fabric metadata is fetched from Fabric's official metadata service. Modpack downloads should follow the package author's licensing and the mod platform's rules.

## Adding or changing profiles

Edit `cinder-manifest.json` and add a new object to `profiles`. Supported fields:

- `id`: stable unique identifier.
- `name`: text shown in the launcher's Hosted Profile list.
- `type`: `vanilla` or `fabric`.
- `minecraftVersion`: `latest-release`, `latest-snapshot`, or an exact version ID present in Mojang's manifest.
- `loaderVersionPolicy`: optional; use `latest-compatible` for Fabric profiles.

Commit the change to the `main` branch. The raw URL above then serves the updated JSON to Cinder. The launcher currently resolves Fabric's latest compatible stable loader itself; specifying a custom fixed loader version is not supported by this preview.

## Test the endpoint

Open the raw URL above in a private/incognito browser window. It should display JSON, not the repository's HTML page, and should not ask you to sign in.
