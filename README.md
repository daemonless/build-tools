# build-tools

Pinned FreeBSD build tools bundles for daemonless CI.

Each release is a tarball of FreeBSD `.pkg` files (with full dependency trees) for a specific FreeBSD version. Used by [daemonless/dbuild](https://github.com/daemonless/dbuild) to install build tools without depending on pkg.FreeBSD.org at build time.

## Usage

[daemonless/dbuild](https://github.com/daemonless/dbuild) automatically uses the latest release. No configuration needed.

To pin a specific release, pass `build_tools_ref` to the reusable workflow:

```yaml
jobs:
  build:
    uses: daemonless/dbuild/.github/workflows/daemonless-build.yaml@main
    with:
      image_name: myapp
      build_tools_ref: freebsd-15.0-20260511
    secrets: inherit
```

## Releasing

Runs monthly via schedule, or trigger manually via `workflow_dispatch`.

## Adding a new FreeBSD version

Update `FREEBSD_RELEASE` in `.github/workflows/build-tools.yaml` and trigger a build.
