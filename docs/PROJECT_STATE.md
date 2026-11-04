# Project State

Updated: 2026-11-05

## Repository
- Repository: https://github.com/ryzenasep5-png/Ah-ah
- Branch: main
- Visibility: public
- Write permission: verified

## Target
- Device: Xiaomi Poco X3 NFC (surya)
- SoC/GPU: Snapdragon 732G / Adreno 618
- Android target: 10 / MIUI 12.0.9
- Expected kernel base: Linux 4.14.117
- Kernel local name target: RyzenX-Surya

## Source baseline
- URL: https://github.com/MiCode/Xiaomi_Kernel_OpenSource
- Branch: surya-q-oss
- Pinned commit: 5e0a8dada006832d3c0511fdc7903c68474cad87
- Commit date: 2020-11-20
- Commit subject: Kernel: Xiaomi kernel changes for Redmi POCO X3 Android Q
- Defconfig recorded in upstream commit: sdmsteppe-perf_defconfig
- Path verified: arch/arm64/configs/vendor/sdmsteppe-perf_defconfig
- Kernel Makefile verified: VERSION=4, PATCHLEVEL=14, SUBLEVEL=117

## Status
- Repository access: SUCCESS
- README: committed
- Source branch and commit metadata: SUCCESS
- Kernel version and defconfig path: SUCCESS
- Full source/device-tree audit: INCOMPLETE
- Baseline build: NOT TESTED
- KernelSU-Next: NOT TESTED
- SUSFS: NOT TESTED
- MemKernel: NOT INTEGRATED (user instructed not to inspect its source)
- Physical-device boot: NOT TESTED
- Flashing: NOT PERFORMED

## Last change
- Commit: 6ed7561a633ae3cb94f48a67eb0c77779c6ec523
- Message: chore: initialize RyzenX kernel project README

## Next steps
1. Complete source audit, especially device-specific DTS/DTBO and build dependencies.
2. Run pinned baseline build using the upstream vendor defconfig.
3. Diagnose only the first actionable build failure; keep logs as workflow artifacts.
4. Audit KernelSU-Next legacy integration and SUSFS compatibility separately.
5. Consider MemKernel only through the user-provided setup instructions, without reading its source; keep it disabled until a successful baseline build.
6. Do not claim boot or performance results without physical-device testing.
