# Changelog


## v1 (active)

The v1 release supports Cisco IOS-XR release versions 7.7.1 and 7.8.1.

### v1.1.8 (2023-03-08)

- Add a check in the `host-check` script to verify if the host has required cgroup mounts.


### v1.1.7 (2023-02-24)

- `launch-xrd` to output a message asking the user to specify the platform when specifying dry-run on a non-loaded image, instead of trying to pull the image.


### v1.1.6 (2023-02-22)

- Add checks for correct socket kernel parameters to `host-check`.


### v1.1.5 (2023-02-13)

- When specifying `IMG` in the `launch-xrd` script, users can now pass an image to be pulled from a repo.
- `launch-xrd` script will now give better error messages when an unrecognized image is passed.


### v1.1.4 (2023-02-02)

Updates for xr-compose handling of MTUs.
- Set the MTU of generated networks to 9000 to handle any XR MTU (up to the XR maximum of 9000).
- Pass through driver_opts from the networks in the input yaml to the output.


### v1.1.3 (2023-01-26)

- `xr-compose` script will now respect the privilege status of a container in the input file.


### v1.1.2 (2023-01-06)

- In the `launch-xrd` script the mechanism for passing extra args to the container manager has been updated. Args after '--' separator will be passed to the container manager as well. To clarify, this is in addition to the existing mechanism of unrecognised arguments (before the '--' separator) being passed to the container manager. This will facilitate passing args common to the script and the container manager.


### v1.1.1 (2022-12-05)

- In the `launch-xrd` script the mechanism for passing extra args to the container manager has changed. The `--args` argument is no longer required - every unrecognised argument will be passed to the container manager. The container image must now be passed as the last argument to the script. The `--args` method is still supported for backwards compatibility, but will be removed in the future.


### v1.1.0 (2022-12-02)

Changes corresponding to the release of XR version 7.8.1.

- Add `--boot-log-level` arg in `launch-xrd` (supported in XR 7.8.1 onwards)
- Stop passing host `/sys/fs/cgroup` mount through to the container
- Update cgroup check in `host-check` and remove corresponding "Systemd mounts" check (no longer required for XR 7.8.1 onwards)
- Remove hard requirement for cgroups v1 in `host-check` (cgroups v2 supported for lab use)


### v1.0.4 (2022-11-30)

- Indicate when a command times out in the `host-check` script.


### v1.0.3 (2022-10-26)

- To check if AppArmor is enabled, `host-check` script now looks at `"/sys/kernel/security/apparmor/profiles"` instead of `"/sys/module/apparmor/parameters/enabled"`.
- `host-check` now gives a warning if AppArmor is enabled.


### v1.0.2 (2022-09-21)

- Do not run 'extra checks' in `host-check` by default.
- Make igb_uio a supported PCI driver, only failing `host-check` if no interface driver is loaded.
- Only check if IOMMU is enabled if vfio-pci is being used, and handle the case where the vfio-pci 'no IOMMU' mode is unconfigurable.


### v1.0.1 (2022-09-07)

- Emit a warning in `host-check` when 2M hugepages are used, as this is not a
supported deployment use case.


### v1.0.0 (2022-07-15)

First release.

- Scripts: `host-check`, `launch-xrd`, `xr-compose`, `apply-bugfixes`
- Templates: MacVLAN launch-xrd example, xr-compose template
- Sample xr-compose topologies: 'simple-bgp', 'bgp-ospf-triangle, 'segment-routing'
- Tests: host-check UT
