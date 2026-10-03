# RaceMetry firmware

Public distribution of signed RaceMetry firmware and its browser OTA catalog.
Application source and private signing keys are not included.

The device independently authenticates each manifest using its provisioned
ECDSA P-256 public key before writing the inactive OTA slot. Complete-image
SHA-256 and boot validation remain mandatory. Firmware cannot be installed
while a recording, save or calibration is active.

`catalog.json` lists immutable manifest URLs. Firmware binaries and manifests
are served from `raw.githubusercontent.com` at canonical version tags to allow
browser CORS downloads from the device's local Wi-Fi page. Matching artifacts
are also attached to GitHub Releases. Published versions are immutable.

These initial releases are qualification candidates: physical OTA, rollback
and phone/network switching tests remain pending.

Supported target: T-Beam Supreme V3.0 / ESP32-S3 / M10S / SX1262 868 MHz,
`tbeam-supreme-v3-m10s-sx1262-868`, 8 MiB flash, two 3,342,336-byte OTA slots.
Configuration schema 1 and rollback protocol 1; no normal-update factory reset.

On the device web page: read device status, then use **Verifica aggiornamenti**
with Internet available on the phone. The package is cached on the phone. If
needed, switch back to Bikemetry Wi-Fi and press **Aggiorna**. Reboot only after
the device completes verification, then reconnect to read the final status.
