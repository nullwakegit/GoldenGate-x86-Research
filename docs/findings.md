# Findings

This page contains results supported by observations. Unverified hypotheses belong in the relevant experiment record.

## User-reported facts

- Tahoe 26.3 currently runs on the Ryzen 7 5700G with integrated graphics and 32 GB RAM.
- Tahoe 26.6 previously ran on the same machine.
- Golden Gate 27 has not yet been tested on that machine.

## Confirmed by the shared `gibMacOS` output

On 2026-09-23, the list showed Golden Gate 27.0 (26A428), Tahoe 26.6 (25G72), and Tahoe 26.6.2 (25G83), among other products. Tahoe 26.6 (25G72, product 140-71750) subsequently completed downloading: `gibMacOS` reported five files succeeded and none failed. This does not replace a local integrity/hash check. Golden Gate 27.0 (26A428, product 142-15488) also completed downloading; `gibMacOS` reported five files succeeded and none failed. It has not been tested on the Ryzen. The local `InstallAssistant.pkg` SHA-256 values have been recorded in `environment.md`. `pkgutil --check-signature` reports `signed Apple Software` for both packages, with an Apple certificate chain. Neither package has been installed. A read-only payload listing of the Golden Gate package shows an `Applications/Install macOS 27 Golden Gate.app` bundle. Searching the saved payload path list for `SharedSupport`, `InstallESD`, `BaseSystem`, `InstallInfo`, and `Packages` returned no matches. This does not establish that the package has no OS assets; `plutil -p InstallInfo.plist` returned an empty dictionary (`{}`). Other separately downloaded metadata has not yet been inspected, and the main OS image location remains unknown.

## Open questions

- Exact build of the current Tahoe 26.3 installation.
- Whether the Tahoe 26.6 and Golden Gate 27 downloads completed successfully.
- SHA-256 and verifiable source for each downloaded copy.
- Architectures present in Golden Gate components and whether it can boot on x86-64.
