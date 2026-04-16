# Reference

This document is a long-form companion for the skill.  
Use it when users need detailed walkthroughs, not for first-pass execution.

## Verified Version Matrix
Use this table to communicate known-good combinations.

| Component | Recommended | Notes |
|---|---|---|
| OS | Windows 10/11 x64 | Keep latest patches |
| DevEco Studio | 6.x | Match OpenHarmony toolchain packages |
| JDK | 17 | Required by current workflow |
| Flutter branch | `oh-3.27.4-dev` | Harmony-adapted branch |
| OpenHarmony SDK | 6.x family | Install from DevEco SDK manager |
| ArkUI-X | Version bundled for DevEco 6.x | Keep same generation as SDK |

## Hardware/Virtualization Prerequisites
Before emulator setup, verify:
- CPU virtualization is enabled in BIOS/UEFI
- Windows virtualization features required by emulator are available
- RAM is at least 16 GB (8 GB minimum for light usage)
- Free disk space is at least 20 GB for SDK + emulator images

If emulator startup repeatedly fails, verify virtualization first before re-installing tools.

## Recommended Install Order
1. Git
2. JDK 17
3. DevEco Studio 6.x
4. OpenHarmony SDK
5. ArkUI-X
6. Emulator image
7. Harmony-adapted Flutter SDK branch

## Path Templates
Replace `<ROOT>` with your own install base folder.

- `<ROOT>/HarmonyOS/DevEco Studio/sdk/default/openharmony/toolchains`
- `<ROOT>/HarmonyOS/DevEco Studio/tools/ohpm/bin`
- `<ROOT>/HarmonyOS/DevEco Studio/tools/node`
- `<ROOT>/HarmonyOS/DevEco Studio/tools/hvigor/bin`
- `DEVECO_SDK_HOME=<ROOT>/HarmonyOS/DevEco Studio/sdk`

Flutter path template:
- `<ROOT>/Flutter/flutter_flutter/bin`

## Core Commands
```bash
git clone -b oh-3.27.4-dev https://gitcode.com/openharmony-tpc/flutter_flutter.git
flutter --version
flutter doctor -v
flutter create --platforms ohos <projectName>
flutter build app --release
```

## Build Output
After successful release build, check:
- `ohos/build/outputs/default`

Look for unsigned `.hap` package.

## Device Connection (Real Device)
Use Harmony device wireless debugging page to get IP and port.

```bash
hdc tconn <ip:port>
```

## Signing Notes
- Open Project Structure in DevEco
- Use `Sign In`
- Complete browser authorization
- Return to DevEco and ensure signing config is refreshed

## Impeller Setting
Project can toggle:
- `"enable_impeller": "true"`
- `"enable_impeller": "false"`

Location is typically in project resources after create/run/build workflow.
