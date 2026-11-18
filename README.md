# POCO X3 Pro ROM setup files

This folder contains files collected for a POCO X3 Pro custom-ROM setup. The codename is `vayu` for global models and `bhima` for the Indian model. Confirm the device codename before flashing anything.

## Important file status

- `crDroidAndroid-17.0-20261117-vayu-v13.1.zip` opens as a ZIP and its installer metadata lists `vayu,bhima`. SHA-256: `64f5db1d33d72a26673438e535bd0c7ff545c6312af4d27a682fa761ec0014fe`. This local check does not verify the full payload or prove its download source.
- `vayu/crDroidAndroid-17.0-20261117-vayu-v13.1.zip` is a truncated 655,086-byte copy and is not a valid ZIP. Do not use it.
- Both `stock_india_fastboot.tgz` copies are truncated: listing their contents fails while reading `images/boot.img`. They are not usable for restore. Do not run any script from an incomplete package.
- The standalone `recovery.img` differs from the recovery image inside the crDroid ZIP. Its source and intended use are unverified; do not flash it until verified against its publisher.
- `gapps.sha256sum` matches the local MindTheGapps archive. A match against a locally supplied checksum is not independent source verification.
- The Mi Unlock executable's Windows Authenticode signature verified as Xiaomi-signed on this machine. This does not establish that the other bundled files are authentic or current.

Replace the damaged stock archive and verify all flashable files against checksums from their publishers before use. Back up personal data first. Never relock the bootloader while a custom ROM is installed; the included stock package has a `flash_all_lock.bat` script that runs `fastboot oem lock`.

## Clone

Install Git and Git LFS, then clone this repository. Large archives, APKs, and images are stored with Git LFS:

```powershell
git lfs install
git clone https://github.com/alif-primary/poco-x3-pro-rom-setup.git
```

The `.lnk` shortcuts are intentionally excluded: they point to machine-specific paths and are not needed to use the files.
