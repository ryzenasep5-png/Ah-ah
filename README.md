# RyzenX Kernel — Poco X3 NFC

Custom kernel project for Xiaomi Poco X3 NFC (surya).

## Target

- Device: Poco X3 NFC (surya)
- SoC/GPU: Qualcomm Snapdragon 732G / Adreno 618
- Target OS: Android 10, MIUI 12.0.9
- Kernel base: Linux 4.14.117
- Maintainer: Ryzen

## Source baseline

- Repository: https://github.com/MiCode/Xiaomi_Kernel_OpenSource
- Branch: surya-q-oss
- Pinned source commit: 5e0a8dada006832d3c0511fdc7903c68474cad87
- Defconfig: arch/arm64/configs/vendor/sdmsteppe-perf_defconfig

The upstream branch commit message identifies the source as the Xiaomi kernel changes for Redmi/POCO X3 Android Q and names sdmsteppe-perf_defconfig. The source Makefile reports Linux 4.14.117. This is a verified source baseline, not proof that a resulting image boots on a physical device.

## Current status

See docs/PROJECT_STATE.md and docs/SOURCE_AUDIT.md.

No kernel image is published yet. KernelSU-Next, SUSFS, MemKernel, runtime performance, and physical-device boot remain unverified until their respective build or device tests pass.

## Build

Use GitHub Actions → Build Poco X3 NFC kernel → Run workflow. The default run builds the pinned upstream source with the verified vendor defconfig. Optional KernelSU-Next and MemKernel paths are opt-in until the baseline build is confirmed.

Artifacts are uploaded only when actually produced. A successful compile does not establish boot compatibility.

## Safety

- No overclock or unsafe voltage changes are enabled.
- Thermal protections are not intentionally disabled.
- No automatic flashing or partition writes are performed.
- Make a full recovery/boot-image backup before any manual device testing.
- Do not flash an artifact unless its compatibility has been independently confirmed.

## License

The upstream Linux kernel source retains its original licenses. Project-specific scripts and documentation do not change those upstream terms.
