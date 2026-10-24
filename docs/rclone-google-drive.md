# Google Drive OAuth for personal rclone use

## Scope

This document covers an individually operated rclone Google Drive remote. Hecate currently supplies static app information and a privacy policy; it is **not** an OAuth broker, credential vault, Google Drive proxy, or MCP service.

## Recommended setup

1. Enable the Google Drive API in a personal Google Cloud project.
2. Configure Google Auth Platform with an **External** audience and a **Desktop app** OAuth client.
3. Select only the scopes needed for the actual rclone remote. File management requires `drive`; the `drive.file` scope does not show previously existing arbitrary files. Follow rclone's official client-ID instructions for any additional scopes it requests.
4. For first-time testing, add the account as a test user and complete rclone authorization.
5. An External app in **Testing** normally issues refresh tokens that expire after seven days for Drive scopes. For a persistent personal mount, publish the OAuth consent screen. **Publishing is not the same as obtaining Google's verification.** Personal-use exceptions may allow the app to remain unverified, with consent warnings and user caps.
6. If Google requires a public home page and privacy policy for publishing, publish the static pages in this repository and register the **actual deployed URLs**. Do not register a speculative or unverified URL.
7. Treat rclone `root_folder_id` as a working-view boundary, **not** an OAuth authorization restriction.

## Site deployment

GitHub Pages: Repository **Settings → Pages → Deploy from a branch → main → /(root)**, after merging the reviewed site files. The expected project URL is `https://junhyeok-choe.github.io/hecate/`; confirm the published URL is live before entering it in Google Cloud. The privacy URL is `https://junhyeok-choe.github.io/hecate/privacy.html`. Google may require domain verification or a separately controlled domain for OAuth verification.

## Secrets

- Never commit OAuth client secrets, tokens, `rclone.conf`, refresh tokens, API keys, or raw Drive data.
- Google Cloud credentials and local rclone tokens remain on operator-managed devices, not on GitHub Pages.
- Do not expose an rclone remote-control API or MCP service to the internet without authentication, authorization, operation constraints, and audit logging.
- A future remote connector needs its own policy and an updated privacy statement before deployment.

## References

- [rclone: Google Drive client ID](https://rclone.org/drive/#making-your-own-client-id)
- [Google OAuth: app state](https://developers.google.com/identity/protocols/oauth2/production-readiness/overview)
- [Google OAuth: token lifecycle](https://developers.google.com/identity/protocols/oauth2)
- [Google OAuth: personal use exception](https://support.google.com/cloud/answer/13464323)
- [GitHub Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
