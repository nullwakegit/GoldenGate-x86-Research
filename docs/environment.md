# Reference environment

## Hardware

| Field | Information |
|---|---|
| CPU | AMD Ryzen 7 5700G |
| GPU | Radeon integrated graphics in the Ryzen 7 5700G |
| RAM | 32 GB |
| Motherboard / BIOS | Not yet collected |
| SMBIOS | Not yet collected; do not publish serial numbers |
| OpenCore and configuration | Not yet collected |
| Storage | Not yet collected |

## macOS versions

| OS | Build | Status on this machine | Source / notes |
|---|---|---|---|
| Tahoe 26.3 | Not yet recorded | Currently runs | Existing installation; record the exact build when checked |
| Tahoe 26.6 | 25G72 | Download completed; previously ran on this machine | Product 140-71750; `gibMacOS` reported all listed files succeeded and none failed on 2026-09-23 |
| Tahoe 26.6.2 | 25G83 | No test recorded | Product 140-93587 listed by `gibMacOS` |
| Golden Gate 27.0 | 26A428 | Not tested | Product 142-15488 listed by `gibMacOS`; whether the download completed is unconfirmed |

The `gibMacOS` list shared in the conversation also included Tahoe 26.7 (25G229). There is no record that it was downloaded or tested, so it is not part of the baseline yet.

## Record for each image

Tahoe 26.6 (25G72, product 140-71750) completed downloading on 2026-09-23. `gibMacOS` reported success for `InstallInfo.plist`, `UpdateBrain.zip`, `InstallAssistant.pkg`, `MajorOSInfo.pkg`, and `com_apple_MobileAsset_MacSoftwareUpdate.plist`, with no failed files. The local download folder is outside this public repository. SHA-256 verification is still pending.

When a download is confirmed, complete a record like this (do not upload the file):

```text
Product/build:
Catalog ID or source URL:
Download date (UTC):
Local filename and size:
SHA-256:
Verification status:
Local location (optional; do not publish private paths):
```

Calculate the hash locally, for example on macOS/Linux with `shasum -a 256 filename` or in Windows PowerShell with `Get-FileHash filename -Algorithm SHA256`. Do not share private links or account details.
