# Hecate

Documentation for application integrations.

## Google Drive

Hecate documents a personal Google Drive connection through [rclone](https://rclone.org/drive/).

- [Website](https://junhyeok-choe.github.io/hecate/)
- [Privacy policy](https://junhyeok-choe.github.io/hecate/privacy.html)
- [rclone setup](docs/rclone-google-drive.md)

## Website deployment

GitHub Pages uses Jekyll and the [Pages workflow](.github/workflows/pages.yml). The repository's Pages source is **GitHub Actions**.

## Security

Keep OAuth credentials, `rclone.conf`, and file data out of the repository. The rclone root folder setting does not restrict OAuth permissions.
