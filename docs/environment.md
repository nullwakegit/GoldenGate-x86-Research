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
| Golden Gate 27.0 | 26A428 | Download completed; not tested on the Ryzen | Product 142-15488; `gibMacOS` reported all listed files succeeded and none failed on 2026-09-23 |

The `gibMacOS` list shared in the conversation also included Tahoe 26.7 (25G229). There is no record that it was downloaded or tested, so it is not part of the baseline yet.

## Record for each image

Tahoe 26.6 (25G72, product 140-71750) completed downloading on 2026-09-23. `gibMacOS` reported success for `InstallInfo.plist`, `UpdateBrain.zip`, `InstallAssistant.pkg`, `MajorOSInfo.pkg`, and `com_apple_MobileAsset_MacSoftwareUpdate.plist`, with no failed files.

Golden Gate 27.0 (26A428, product 142-15488) also completed downloading on 2026-09-23. `gibMacOS` reported success for the same five file names and no failed files. The local download folders are outside this public repository. SHA-256 hashes calculated locally for the `InstallAssistant.pkg` files:

| Product | Approx. file size | SHA-256 (`InstallAssistant.pkg`) |
|---|---|
| Tahoe 26.6 (25G72) | About 17 GB (`ls -lh`) | `d9ce954992b47d8350ec9ef913ad355035cdba04f511e695b52239fe48af5942` |
| Golden Gate 27.0 (26A428) | About 17 GB (`ls -lh`) | `e74aa9c2b31d0d764050874aabc4e761e12ef21e615dababf1bb2527a44cf7f8` |

These hashes identify the local files and help compare copies; they do not independently prove authenticity.

`pkgutil --check-signature` reported `Status: signed Apple Software` for both `InstallAssistant.pkg` files. Both outputs showed the Apple Software Update → Apple Software Update Certification Authority → Apple Root CA certificate chain. No package has been installed. `ls -lh` showed each `InstallAssistant.pkg` at about 17 GB. Available space was 74 GiB; package extraction has not started. `file` identifies the Golden Gate `InstallAssistant.pkg` as a XAR archive with a SHA-1 checksum. A read-only `pkgutil --payload-files` listing of the Golden Gate package begins with `./Applications/Install macOS 27 Golden Gate.app` and its app bundles/resources. Searching the complete saved path listing for `SharedSupport`, `InstallESD`, `BaseSystem`, `InstallInfo`, or `Packages` returned no matches. This only describes names in the package payload list; the separate downloaded metadata/assets have not yet been inspected. `plutil -p InstallInfo.plist` returned an empty dictionary (`{}`). The separate `com_apple_MobileAsset_MacSoftwareUpdate.plist` identifies OS 27.0 / build 26A428, train `Fizz`, and marks the asset `PreRelease`. It reports a 18,373,348,416-byte download and 19,227,554,816-byte unarchived size, `IsUniversal=true`, and `SupportedDeviceModels` containing `J180dAP`. Its listed cryptex tags include `BaseSystem-arm64e`, `cryptex-system-arm64e`, and `cryptex-system-arm64e.x1`, plus `cryptex-app` and `cryptex-system-rosetta`; no x86_64 tag appears in this metadata. `IsUniversal` is not by itself proof of Intel/AMD support. These metadata observations need confirmation against the actual asset contents.

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
