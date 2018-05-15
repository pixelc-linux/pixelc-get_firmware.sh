# Pixel C firmware downloader and archiver

This script fetches and archives the necessary firmware for the Pixel C.

To use, simply exec:

```
./get_firmware.sh
```

The result is two archives:

- `firmware_all.tar.gz`
- `firmware_brcm_extra_only.tar.gz`

The first archive contains all the firmware needed to bring up the onboard
hardware. The second archive contains only the parts not present out of box
in the `linux-firmware` repository/packages.

If your distro provides a `linux-firmware` package, it is recommended to
install that and then use the `firmware_brcm_extra_only.tar.gz` archive to
supply the rest of the files, otherwise you can use the `firmware_all.tar.gz`
archive. The primary reason to use `linux-firmware` as whole is for potential
peripherals needing proprietary blobs.

If you are sure you won't be needing any of those and want something minimal
that does not take up extra space, feel free to use `firmware_all.tar.gz`.