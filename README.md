# GoldenGate-x86-Research

Documenting an investigation into whether **macOS 27 “Golden Gate”** can boot or run parts of its system on **unsupported x86-64 hardware**, using an AMD Ryzen 7 5700G as the reference machine.

> This is an independent experimental project. It is not affiliated with Apple or OpenCore. It does not distribute macOS or operating system images.

## Goal

Determine, through reproducible experiments, which Golden Gate components retain x86-64 compatibility and how far the system can boot on unsupported hardware. We will distinguish architecture and boot issues from driver support and graphics acceleration.

Failed attempts will be documented too. A negative result is useful when the configuration, changes, and observed error are recorded.

## Current status

- **Tahoe 26.3:** currently runs on the reference machine.
- **Tahoe 26.6:** previously ran on the same machine.
- **Golden Gate 27:** has not yet been tested on the Ryzen system.
- **Golden Gate 27.0 (build 26A428):** appeared in the `gibMacOS` product list. Confirm in the timeline whether the download completed, and record its hash before analyzing files.
- **Tahoe 26.6 (build 25G72):** appeared in the same product list. The earlier conversation said its download was started; the final status still needs confirmation.

Known details and open questions are tracked in [docs/environment.md](docs/environment.md) and [docs/timeline.md](docs/timeline.md).

## Reference hardware

| Component | Known information |
|---|---|
| CPU | AMD Ryzen 7 5700G |
| Graphics | Radeon integrated graphics in the Ryzen 7 5700G |
| Memory | 32 GB RAM |
| Currently working OS | macOS Tahoe 26.3 |
| Previously tested OS | macOS Tahoe 26.6 |

Unknown details (motherboard, SMBIOS, OpenCore configuration, storage, and peripherals) will be added when collected. Serial numbers and private identifiers must not be published.

## Research plan

1. Record the environment and keep backups; do not experiment on the working installation.
2. Verify the source, version/build, and SHA-256 of each download. Keep installers and images locally.
3. Inspect and compare Tahoe 26.3/26.6 and Golden Gate 27 components (for example, binary architectures and the presence of x86-64 components).
4. State a testable hypothesis before each change.
5. Change one thing at a time, keep a record, and document the result, including failures.
6. Publish reproducible methods and findings, distinguishing observations from hypotheses.

## Repository layout

```text
README.md
.gitignore
docs/
  environment.md
  timeline.md
  findings.md
  experiments/
    TEMPLATE.md
```

## Privacy and large files

This repository stores documentation, small scripts, and hashes. **Do not upload** RAW images, DMGs, PKGs, installers, firmware, or other macOS files. Keep them locally. `.gitignore` excludes common formats, but review `git status` before every commit. Do not publish personal data, serial numbers, UUIDs, tokens, or EFI files containing private identifiers.

## Keeping the research log

- Add new events to `docs/timeline.md`.
- Record verifiable conclusions in `docs/findings.md`.
- Copy `docs/experiments/TEMPLATE.md` for each test and use names such as `001-tahoe-26-6-baseline.md`.
- Label `Observation`, `Hypothesis`, and `Conclusion` clearly; do not present assumptions as facts.

## License

No license has been selected yet. Until one is added, no general permission is granted to reuse this repository's content.
