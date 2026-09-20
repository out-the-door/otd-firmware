# Out the Door — firmware releases

Signed over-the-air firmware images for Out the Door boards. **Binaries only**;
the source lives in the private `out-the-door/out-the-door` repo.

- `manifest.json` — what boards fetch (Sundays, 4 AM local): version, download
  URL, size, SHA-256, and an ECDSA P-256 signature over that digest.
- `bin/otd-<version>.bin` — the images.
- `releases/<version>.json` — a copy of each manifest, to roll the pointer back
  by hand if a release must be pulled.

Boards verify the signature against the public key baked into their firmware
before switching boot slots, so only images signed with the release key are
ever installed. Published by `tools/ota_release.py` in the source repo.
