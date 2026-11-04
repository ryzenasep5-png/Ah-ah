# Source Audit — Initial Findings

## Verified upstream facts
- Repository: https://github.com/MiCode/Xiaomi_Kernel_OpenSource
- Branch: surya-q-oss
- Branch head: 5e0a8dada006832d3c0511fdc7903c68474cad87
- Commit message: "Kernel: Xiaomi kernel changes for Redmi POCO X3 Android Q"
- Commit metadata names Qualcomm base tag LA.UM.8.9.r1-09300-SM6xx.0.
- Commit metadata explicitly states the kernel config used is sdmsteppe-perf_defconfig.
- Defconfig exists at arch/arm64/configs/vendor/sdmsteppe-perf_defconfig.
- Root Makefile reports Linux 4.14.117.
- ARM64 config includes Qualcomm SM6150/SDM Magpie platform options, WALT scheduler, CPU frequency governors, CPU boost, ZRAM, Qualcomm KGSL, touchscreen support (including NT36xxx host-download SPI), and thermal support.

## Important limits / unresolved audit
- The upstream branch metadata and platform config are consistent with the Android Q Poco X3 release, but the exact surya device DTS/DTBO mapping and final boot packaging have not yet been verified.
- The upstream defconfig is named sdmsteppe-perf_defconfig. Do not rename it or assume another defconfig without evidence.
- A config option being enabled does not establish that a feature is optimized or validated on the phone.
- Toolchain compatibility and exact build dependencies remain to be established by a real build.
- KernelSU-Next and SUSFS patch compatibility with this legacy tree has not been established.
- MemKernel source was deliberately not inspected, per user instruction. No claim of compatibility or integration is made.

## Safety decisions
- Preserve upstream device drivers and thermal protections.
- No overclock, voltage changes, thermal bypass, or automatic flashing.
- Do not publish a boot image unless the build produces it and its packaging is verified.
- Build success is not equivalent to boot success.
