# Troubleshooting

## `hdc` Not Recognized
Symptoms:
- `hdc` command not found

Checks:
1. Confirm `.../openharmony/toolchains` is in `Path`
2. Re-open terminal after editing environment variables
3. Run `hdc --help`

Fix:
- Re-add path entries exactly
- Avoid quoting the path value in Windows env var editor

## `flutter` Not Recognized
Symptoms:
- `flutter` command not found

Checks:
1. Confirm `.../flutter_flutter/bin` is in `Path`
2. Re-open terminal
3. Run `flutter --version`

## `flutter doctor -v` Reports Missing Toolchain
Symptoms:
- Doctor reports unresolved dependencies

Fix order:
1. Verify JDK 17 installation
2. Verify DevEco-related path entries
3. Verify `DEVECO_SDK_HOME`
4. Re-run `flutter doctor -v`

## Sign In Fails In DevEco
Symptoms:
- Auto signing cannot complete

Checks:
1. Browser authorization completed
2. System clock is accurate
3. Network is stable and unrestricted

Fix:
- Sync Windows time and timezone, retry Sign In

## Build Fails On `flutter build app --release`
Symptoms:
- Build stops with OHOS or dependency errors

Checks:
1. Project created with `--platforms ohos`
2. SDK components installed in DevEco
3. Environment variables loaded in current shell

Fix:
1. Re-run `flutter doctor -v`
2. Confirm target SDK version in project config
3. Retry build after shell restart

## Emulator Startup Issues
Symptoms:
- Emulator not booting or not detected

Checks:
1. Emulator image downloaded completely
2. Emulator path is writable
3. DevEco Device Manager shows the instance

Fix:
- Recreate emulator instance in Device Manager
- Restart DevEco Studio
