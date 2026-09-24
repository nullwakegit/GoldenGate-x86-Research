# Timeline

A short record of milestones. Exact dates are marked as unknown when unavailable.

| Date | Milestone | Status / evidence |
|---|---|---|
| Unknown | Tahoe 26.3 installed on Ryzen 7 5700G | User reports it currently works; exact build not recorded |
| A few months ago (exact date unknown) | Tahoe 26.6 used on the same machine | User reports it worked well; build 25G72 was listed in the catalog, but whether it was the same installation is unconfirmed |
| 2026-09-23 | `gibMacOS` listed Tahoe 26.6 (25G72), Tahoe 26.6.2 (25G83), and Golden Gate 27.0 (26A428) | Catalog IDs: 140-71750, 140-93587, and 142-15488; based on output shared in the conversation |
| 2026-09-23 | Tahoe 26.6 (25G72, product 140-71750) download completed with `gibMacOS` | Output reported five files succeeded and none failed; SHA-256 verification is pending |
| 2026-09-23 | Golden Gate 27.0 (26A428, product 142-15488) download completed with `gibMacOS` | Output reported five files succeeded and none failed; not tested on the Ryzen; SHA-256 verification is pending |
| 2026-09-24 | Local SHA-256 hashes calculated for Tahoe 26.6 and Golden Gate 27.0 `InstallAssistant.pkg` files | Hashes recorded in `environment.md`; package signature checks remain pending |
| 2026-09-24 | Apple package signatures checked for both `InstallAssistant.pkg` files | `pkgutil --check-signature` reported `signed Apple Software`; details recorded in `environment.md` |
| 2026-09-24 | Installer sizes and free space checked before extraction | Each `InstallAssistant.pkg` is about 17 GB; data volume had 74 GiB available; nothing extracted or installed |
| 2026-09-23 | Project documentation started | Golden Gate has not yet been tested on the machine |

## Adding an entry

Record the date, action, result, and evidence (output, screenshot, or hash). If something comes from memory or remains unverified, label it clearly.
