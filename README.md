# build-tools

Pinned FreeBSD build tools bundles for daemonless CI.

Each release is a tarball of FreeBSD `.pkg` files (with full dependency trees) for a specific FreeBSD version. Used by [daemonless/dbuild](https://github.com/daemonless/dbuild) to install build tools without depending on pkg.FreeBSD.org at build time.

## Usage

In `daemonless-build.yaml`:

```yaml
env:
  BUILD_TOOLS_REF: freebsd-15.0-20260502
```

## Releasing

Runs monthly via schedule, or trigger manually via `workflow_dispatch`.

To update `BUILD_TOOLS_REF` in dbuild after a new release:
1. Check the new release tag in this repo
2. Update `BUILD_TOOLS_REF` in `daemonless/dbuild/.github/workflows/daemonless-build.yaml`

## Adding a new FreeBSD version

Update `FREEBSD_RELEASE` in `.github/workflows/build-tools.yaml` and trigger a build.
