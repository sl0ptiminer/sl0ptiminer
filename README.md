<p align="center"><img src="banner.png" width="1280" alt="Sl0ptiminer. Optimized for your mining pleasure."></p>

**Current version 0.8.3**, released 2026-11-22. [What changed](https://sl0ptiminer.com/releases/#v0-8-3)

Sl0ptiminer is a cryptocurrency miner. It mines Hoohash for Hoosat (HTN), on x86-64 processors, 64-bit ARM processors and NVIDIA graphics cards. Systems: Linux, macOS and HiveOS. This repository holds its signed release packages, the same files as on the official site, https://sl0ptiminer.com. Use it if the site cannot be reached. Sl0ptiminer is closed source and paid for by a [developer fee](https://sl0ptiminer.com/wiki/fee/).

## Packages

| System | Needs | Package | Guide |
|---|---|---|---|
| Linux | x86-64 with AVX2, FMA and BMI2 · glibc 2.31 or newer · also mines on NVIDIA cards | [`sloptiminer-0.8.3-linux-x86_64-gnu.tar.gz`](https://github.com/sl0ptiminer/sl0ptiminer/releases/download/v0.8.3/sloptiminer-0.8.3-linux-x86_64-gnu.tar.gz) · 5.1 MB | [Linux guide](https://sl0ptiminer.com/guides/linux/) |
| Linux, older systems | x86-64 with AVX2, FMA and BMI2 · any Linux · CPU only | Comes in a following release | [Linux guide](https://sl0ptiminer.com/guides/linux/) |
| Linux on ARM | 64-bit ARM · glibc 2.31 or newer · also mines on NVIDIA cards | [`sloptiminer-0.8.3-linux-aarch64-gnu.tar.gz`](https://github.com/sl0ptiminer/sl0ptiminer/releases/download/v0.8.3/sloptiminer-0.8.3-linux-aarch64-gnu.tar.gz) · 4.9 MB | [Linux guide](https://sl0ptiminer.com/guides/linux/) |
| Linux on ARM, older systems | 64-bit ARM · any Linux · CPU only | [`sloptiminer-0.8.3-linux-aarch64.tar.gz`](https://github.com/sl0ptiminer/sl0ptiminer/releases/download/v0.8.3/sloptiminer-0.8.3-linux-aarch64.tar.gz) · 4.9 MB | [Linux guide](https://sl0ptiminer.com/guides/linux/) |
| macOS | Macs with Apple silicon · CPU only | Comes in a following release | [macOS page](https://sl0ptiminer.com/guides/mac/) |
| HiveOS | custom miner package | [`sl0ptiminer-0.8.3.tar.gz`](https://github.com/sl0ptiminer/sl0ptiminer/releases/download/v0.8.3/sl0ptiminer-0.8.3.tar.gz) · 5.1 MB | [HiveOS guide](https://sl0ptiminer.com/guides/hiveos/) |

Not available: [mmpOS](https://sl0ptiminer.com/guides/mmpos/), [RaveOS](https://sl0ptiminer.com/guides/raveos/), [Windows](https://sl0ptiminer.com/guides/windows/) and [SimpleMining OS](https://sl0ptiminer.com/guides/simplemining/).

Every [release](https://github.com/sl0ptiminer/sl0ptiminer/releases) carries `SHA256SUMS` and `SHA256SUMS.minisig` next to its packages.

## Install

Read the [licence](https://sl0ptiminer.com/licence/) before you install: every package carries it as `LICENSE.txt`. On Linux, one command installs Sl0ptiminer and later updates it. The [Linux guide](https://sl0ptiminer.com/guides/linux/) has the same steps by hand, and each mining system has its own [guide](https://sl0ptiminer.com/guides/).

```
curl -fsSL https://sl0ptiminer.com/install.sh | sh
```

Then start mining with the algorithm, your pool and your address. [Start mining with Sl0ptiminer](https://sl0ptiminer.com/wiki/quick-start/) goes through it.

```
./sloptiminer mine -a ALGORITHM -o HOST:PORT -u YOUR_ADDRESS.rig1
```

## Verify a download

1. **Get the three files** from the same release folder: the package, `SHA256SUMS` and `SHA256SUMS.minisig`. The [download page](https://sl0ptiminer.com/download/) links them.
2. **Check the signature** with [minisign](https://jedisct1.github.io/minisign/). This proves the list was signed with the Sl0ptiminer release key.

   ```
   minisign -Vm SHA256SUMS -P RWQ/WbRNa0qAYKdPxfZD1yo1E0fQ7UDCqHt7BEga1v66ufUi3b8JWVOs
   ```

   minisign must answer "Signature and comment signature verified". Anything else: stop and do not run the file.
3. **Check your file against the list.**

   ```
   sha256sum --ignore-missing -c SHA256SUMS
   ```

   The line for your package must end with "OK".

## Help

- [Start mining with Sl0ptiminer](https://sl0ptiminer.com/wiki/quick-start/)
- [Frequently asked questions](https://sl0ptiminer.com/wiki/faq/)
- [Troubleshooting](https://sl0ptiminer.com/wiki/troubleshooting/)

Issues are not used here. To report a security problem, see [Security and verification](https://sl0ptiminer.com/wiki/verify/#report).
