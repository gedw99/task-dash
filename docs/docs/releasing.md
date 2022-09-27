---
slug: /releasing/
sidebar_position: 7
---

# Releasing

The release process of Task is done with the help of
[GoReleaser][goreleaser]. You can test the release process locally by calling
the `test-release` task of the Taskfile.

[GitHub Actions](https://github.com/go-task/task/actions) should release
artifacts automatically when a new Git tag is pushed to master
(raw executables and DEB and RPM packages).

Since v3.15.0, raw executables can also be reproduced and verified locally by
checking out a specific tag and calling `goreleaser build`, using the Go version
defined in the above GitHub Actions.

# Homebrew

To release a new version on the [Homebrew tap][homebrewtap] edit the
[Formula/go-task.rb][gotaskrb] file, updating with the new version, download
URL and sha256.

# Snapcraft

The exception is the publishing of a new version of the
[snap package][snappackage]. This current require two steps after publishing
the binaries:

* Updating the current version on [snapcraft.yaml][snapcraftyaml].
* Moving both `amd64`, `armhf` and `arm64` new artifacts to the stable channel on
the [Snapcraft dashboard][snapcraftdashboard].

# Scoop

Scoop is a command-line package manager for the Windows operating system.
Scoop package manifests are maintained by the community.
Scoop owners usually take care of updating versions there by editing [this file](https://github.com/lukesampson/scoop-extras/blob/master/bucket/task.json).
If you think its Task version is outdated, open an issue to let us know.

# Nix

Nix is a community owned installation method. Nix package maintainers usually take care
of updating versions there by editing
[this file](https://github.com/NixOS/nixpkgs/blob/nixos-unstable/pkgs/development/tools/go-task/default.nix).
If you think its Task version is outdated, open an issue to let us know.

[goreleaser]: https://goreleaser.com/
[homebrewtap]: https://github.com/go-task/homebrew-tap
[gotaskrb]: https://github.com/go-task/homebrew-tap/blob/master/Formula/go-task.rb
[snappackage]: https://github.com/go-task/snap
[snapcraftyaml]: https://github.com/go-task/snap/blob/master/snap/snapcraft.yaml#L2
[snapcraftdashboard]: https://snapcraft.io/task/releases
