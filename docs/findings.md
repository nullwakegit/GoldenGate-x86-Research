# Findings

This page contains results supported by observations. Unverified hypotheses belong in the relevant experiment record.

## User-reported facts

- Tahoe 26.3 currently runs on the Ryzen 7 5700G with integrated graphics and 32 GB RAM.
- Tahoe 26.6 previously ran on the same machine.
- Golden Gate 27 has not yet been tested on that machine.

## Confirmed by the shared `gibMacOS` output

On 2026-09-23, the list showed Golden Gate 27.0 (26A428), Tahoe 26.6 (25G72), and Tahoe 26.6.2 (25G83), among other products. Tahoe 26.6 (25G72, product 140-71750) subsequently completed downloading: `gibMacOS` reported five files succeeded and none failed. This does not replace a local integrity/hash check. Golden Gate 27.0 (26A428, product 142-15488) also completed downloading; `gibMacOS` reported five files succeeded and none failed. It has not been tested on the Ryzen. The local `InstallAssistant.pkg` SHA-256 values have been recorded in `environment.md`. `pkgutil --check-signature` reports `signed Apple Software` for both packages, with an Apple certificate chain. Neither package has been installed. `file` identifies the Golden Gate `InstallAssistant.pkg` as a XAR archive with a SHA-1 checksum. `xar -tf` shows root entries `Bom`, `Payload`, `Scripts`, `PackageInfo`, and `SharedSupport.dmg`; `SharedSupport.dmg` is outside the `Payload`, so it was not listed by `pkgutil --payload-files`. Its listed size is 18,385,574,748 bytes (about 17.1 GiB); the 17 GB DMG was extracted from the XAR to a local temporary directory; `hdiutil verify` reports the disk image checksum is VALID, and its partition checks reported verified CRC32 values. It has been mounted read-only as `/Volumes/Shared Support`; no installer has been run. A read-only payload listing of the package shows an `Applications/Install macOS 27 Golden Gate.app` bundle. Searching the saved payload path list for `SharedSupport`, `InstallESD`, `BaseSystem`, `InstallInfo`, and `Packages` returned no matches. This does not establish that the package has no OS assets; `plutil -p InstallInfo.plist` returned an empty dictionary (`{}`). The separate MobileAsset plist identifies OS 27.0 / build 26A428, `PreRelease`, and supported device model `J180dAP`; its listed cryptex tags include `arm64e` system images but no `x86_64` tag. It also says `IsUniversal=true`, which is not sufficient to infer Intel/AMD compatibility. The plist reports 18,373,348,416 bytes downloaded and 19,227,554,816 bytes unarchived. These are metadata findings, not yet direct inspection of the asset payload; the actual file contents and architecture remain to be analyzed.

## Open questions

- Exact build of the current Tahoe 26.3 installation.
- Whether the Tahoe 26.6 and Golden Gate 27 downloads completed successfully.
- SHA-256 and verifiable source for each downloaded copy.
- Architectures present in Golden Gate components and whether it can boot on x86-64.
