# Google Drive OAuth with rclone

Personal Google Drive access from a local rclone client.

## Setup

1. Enable the **Google Drive API** in Google Cloud.
2. In **Google Auth Platform**, configure an **External** audience and create an OAuth client of type **Desktop app**.
3. Choose the OAuth scopes required by the rclone remote. File management uses `drive`; `drive.file` does not grant access to every existing file.
4. Add your Google account as a test user while the app is in **Testing**, then enter the client ID and secret in `rclone config`.
5. For ongoing use, change the app's audience status to **In production**. Testing-mode refresh tokens for Drive scopes generally expire after seven days. Publishing an app is distinct from Google's verification process.
6. If publishing requires public app links, register the [homepage](https://junhyeok-choe.github.io/hecate/) and [privacy policy](https://junhyeok-choe.github.io/hecate/privacy.html) in **Branding**.

## Permissions

The `drive` scope grants broad access to the account's accessible Drive files. The rclone `root_folder_id` setting limits the remote's visible root but does not change the OAuth permission.

## Website

The site is built with Jekyll and deployed through [GitHub Actions](../.github/workflows/pages.yml). In **Settings → Pages**, use **GitHub Actions** as the deployment source.

## Credentials

Keep the client secret, OAuth tokens, and `rclone.conf` off GitHub. Use locally managed storage for credentials and caches.

## References

- [rclone: Google Drive client ID](https://rclone.org/drive/#making-your-own-client-id)
- [Google OAuth 2.0](https://developers.google.com/identity/protocols/oauth2)
- [Google OAuth verification exemptions](https://support.google.com/cloud/answer/13464323)
