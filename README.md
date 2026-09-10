# yq-go for Debian

[![Release](https://img.shields.io/github/v/release/latest-debs/yq-go-debian)](https://github.com/latest-debs/yq-go-debian/releases)
[![Build](https://github.com/latest-debs/yq-go-debian/actions/workflows/release.yml/badge.svg)](../../actions)

Packaged here as **yq-go** because Debian's archive already ships an unrelated,
older tool under the plain name `yq` (the Python-based
[kislyuk/yq](https://github.com/kislyuk/yq)) — using the same name would
collide with it for anyone with both repositories enabled.

Want your own project packaged and maintained this way? See the
[latest-debs packaging service](https://github.com/latest-debs/apt-repo/blob/main/SERVICE.md).

## Install

Via the latest-debs apt repository:

```sh
sudo apt install extrepo  # if not already installed
sudo extrepo enable latest-debs
sudo apt update
sudo apt install yq-go
```

Or download a `.deb` from the [Releases](https://github.com/latest-debs/yq-go-debian/releases) page:

```sh
sudo apt install ./yq-go_*.deb
```

## Verify

```sh
apt-cache policy yq-go
yq-go --version
```

## Supported distributions & architectures

- Debian Bookworm (12), Trixie (13), Forky (14/testing), Sid (unstable)
- amd64, arm64, armhf, i386 (bookworm/trixie) — actual per-release availability depends on what upstream publishes

## Building

Run the [Build yq-go for Debian](../../actions) workflow on GitHub with the
desired upstream version. Packaging is driven by
[debian-multiarch-builder](https://github.com/ranjithrajv/debian-multiarch-builder).

## Collaborate with us

latest-debs is a community effort. If you rely on this package and want to
help keep it fresh, watching for a new upstream release or fixing a build
hiccup, we'd love your help. Open an issue on this repo, or email
**latest-debs@users.noreply.github.com** to get involved.

## Disclaimer

Unofficial, volunteer-run packaging — **best-effort, no SLA**.

- **Update cadence:** publishing a release normally triggers an immediate
  apt-repo rebuild via webhook; the ~6h scheduled run is the fallback. GitHub
  outages, a missing trigger token, rate limits, or upstream archive changes
  can delay or skip an update; there is no freshness guarantee.
- **Draft releases:** every build is published as a *draft* that a maintainer
  reviews before promoting, so a new version can lag its build.

For issues with yq-go itself, see
[mikefarah/yq](https://github.com/mikefarah/yq).

## License

Packaging scripts in this repo are MIT-licensed. The packaged binaries
remain under their upstream license (`MIT` — see
[mikefarah/yq](https://github.com/mikefarah/yq)).
