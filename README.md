# Hecate

Application integration boundary for personally operated tools.

## Current scope

Hecate currently hosts informational documentation for a **personal rclone integration with Google Drive**. Authentication and Drive file operations are performed by the locally installed rclone client, not by this website.

- [Application home](index.html)
- [Privacy policy](privacy.html)
- [Personal rclone OAuth setup](docs/rclone-google-drive.md)

This repository does **not** currently implement a Google Drive proxy, OAuth token broker, remotely accessible MCP server, or hosted data-processing service. Future functionality requires separate review and documentation.

## GitHub Pages

Publish the static site from `main` / `/(root)` in repository **Settings → Pages** after merging the site changes. The expected site URL is `https://junhyeok-choe.github.io/hecate/`, but verify deployment before using the link in Google Auth Platform.

## Security

Do not commit OAuth client secrets, refresh tokens, `rclone.conf`, personal Drive data, or other credentials. rclone's folder-root setting is not an OAuth access restriction.
