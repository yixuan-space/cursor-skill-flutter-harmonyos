---
name: flutter-harmonyos-windows
description: Set up and build Flutter apps for HarmonyOS (OpenHarmony/OHOS/鸿蒙) on Windows using DevEco Studio, OpenHarmony SDK, ArkUI-X, environment variables, emulator, and signing workflow. Use when the user mentions Flutter HarmonyOS, OpenHarmony, OHOS, 鸿蒙, DevEco, ArkUI-X, Device Manager, hdc, 签名, or building HAP packages.
---

# Flutter HarmonyOS Windows

## Scope
This skill provides a practical workflow for:
- Setting up Flutter + HarmonyOS (OpenHarmony/OHOS/鸿蒙) tooling on Windows
- Creating and building Flutter OpenHarmony/OHOS (鸿蒙) projects
- Running on emulator or real OpenHarmony/OHOS (鸿蒙) devices
- Fixing common setup and signing issues

## Quick Workflow
Follow these phases in order:
1. Install base dependencies
2. Install DevEco components
3. Configure environment variables
4. Install Harmony-adapted Flutter SDK
5. Create and build OHOS project
6. Open in DevEco, sign, and run

## 1) Install Base Dependencies
Ensure these are installed:
- Git
- JDK 17
- DevEco Studio 6.x

Do not continue until all three are available in the system.

## 2) Install DevEco Components
Inside DevEco Studio, install:
- OpenHarmony SDK
- ArkUI-X
- Emulator components

Use custom install paths if needed, but keep all related SDK tools discoverable for environment variable setup.

## 3) Configure Environment Variables
Add these folders to `Path` (replace with local paths):
- `.../DevEco Studio/sdk/default/openharmony/toolchains`
- `.../DevEco Studio/tools/ohpm/bin`
- `.../DevEco Studio/tools/node`
- `.../DevEco Studio/tools/hvigor/bin`

Add/confirm these user or system variables:
- `DEVECO_SDK_HOME=.../DevEco Studio/sdk`
- `PUB_HOSTED_URL=https://pub.flutter-io.cn`
- `FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn`

Validation:
- Open a new terminal and run `hdc --help`
- If `hdc` is not recognized, re-check `Path` entries and restart terminal

## 4) Install Harmony Flutter SDK
Use:
```bash
git clone -b oh-3.27.4-dev https://gitcode.com/openharmony-tpc/flutter_flutter.git
```

Then add Flutter binary directory to `Path`:
- `.../flutter_flutter/bin`

Validation:
```bash
flutter --version
flutter doctor -v
```

## 5) Create And Build Project
Create project:
```bash
flutter create --platforms ohos <projectName>
```

Build release package:
```bash
flutter build app --release
```

Expected result:
- Unsigned `.hap` appears under `ohos/build/outputs/default`

## 6) Open, Sign, And Run In DevEco
1. Open created project in DevEco Studio
2. Accept trust prompt if asked
3. Align target SDK in project configuration
4. Choose runtime target:
   - Real device: connect with `hdc tconn <ip:port>`
   - Emulator: create/start emulator from Device Manager
5. Configure auto signing in Project Structure (`Sign In`)
6. Run project from top-right Run button

## Optional: Impeller Switch
For OHOS projects, `enable_impeller` can be toggled in `buildinfo.json5`:
- `true`: enable impeller-vulkan
- `false`: disable impeller

## Output Expectations
When asked to assist users, return:
- Current phase status
- Next command/action
- Verification result for each phase
- If failed, the exact failing command and targeted fix

## Troubleshooting
For common issues, read:
- [troubleshooting.md](troubleshooting.md)

For step screenshots and extended explanation, read:
- [reference.md](reference.md)

## Failure Decision Tree
Use this sequence for faster triage:
1. `hdc` unavailable:
   - Check `Path` has `.../openharmony/toolchains`
   - Re-open terminal
   - Re-run `hdc --help`
2. `flutter` unavailable:
   - Check `Path` has `.../flutter_flutter/bin`
   - Re-open terminal
   - Re-run `flutter --version`
3. `flutter doctor -v` has missing toolchain:
   - Confirm JDK 17
   - Confirm DevEco SDK variables and path entries
   - Re-run `flutter doctor -v`
4. Build/sign failure:
   - Confirm project created with `--platforms ohos`
   - Confirm target SDK alignment in project config
   - Confirm DevEco Sign In is complete
   - Retry build/run
