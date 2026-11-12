# Slendo Cord updates

This public repository hosts only the update payload used by SlendoCord.exe. The application source repository remains private.

The launcher checks `latest.txt` whenever it starts. If the version differs from the installed payload, it downloads `payload.zip`, checks the SHA-256 hash, installs the app files into `%LOCALAPPDATA%\Slendo Cord`, and then starts the app. Updates apply when the user next opens SlendoCord.exe; a running app is not interrupted for routine updates.

## Publishing an update

1. Build a new `payload.zip` from the app's production bundle, Node.js runtime, and dependencies.
2. Replace `payload.zip` in this repository.
3. Update `latest.txt` to `version|sha256`, using a new unique version and the lowercase SHA-256 hash of the exact ZIP file.
4. Commit and push both files together.

Do not upload `.env` files, account tokens, passwords, or invite codes. The update ZIP does not contain the launcher or its invite codes.
