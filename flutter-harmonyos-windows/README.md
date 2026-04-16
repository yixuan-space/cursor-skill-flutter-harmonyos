# flutter-harmonyos-windows

[中文](#中文) | [English](#english)

---

## 中文

用于在 Windows 上配置并构建 Flutter HarmonyOS（OpenHarmony/OHOS/鸿蒙）项目的 Cursor Skill。

### 功能覆盖
- 基础依赖安装（Git、JDK17、DevEco Studio）
- OpenHarmony（OHOS/鸿蒙）SDK、ArkUI-X、模拟器安装
- 环境变量配置与校验
- OpenHarmony/OHOS（鸿蒙）适配 Flutter SDK 安装
- 项目创建、构建、签名、运行全流程
- 常见问题排查

### 文件结构
- `SKILL.md`：主技能指令（Agent 执行入口）
- `reference.md`：详细参考说明
- `troubleshooting.md`：故障排查手册
- `LICENSE`：MIT 开源许可证

### 安装方式
项目级共享（推荐团队协作）：
- 复制到 `.cursor/skills/flutter-harmonyos-windows/`

个人级复用（推荐个人多项目）：
- 复制到 `~/.cursor/skills/flutter-harmonyos-windows/`

### 使用示例
可直接对 Cursor 说：
- "帮我在 Windows 配置 Flutter 鸿蒙开发环境"
- "用 DevEco 构建 Flutter 的 ohos 项目"
- "hdc 命令不可用怎么修"

触发关键词通常包括：
- Flutter HarmonyOS
- DevEco
- OpenHarmony
- ArkUI-X
- hdc
- hap build

### 开源建议
- 发布到 GitHub 时，建议补充仓库标签：`cursor-skill`、`flutter`、`harmonyos`、`deveco`
- 如需对外展示，可在仓库首页附一张使用流程图或 GIF

### 5 分钟可行性自检（Smoke Test）
在一个新终端中按顺序执行：

```bash
flutter --version
flutter doctor -v
flutter create --platforms ohos smoke_demo
cd smoke_demo
flutter build app --release
```

预期结果：
- `flutter doctor -v` 没有关键阻断项（可有非关键 warning）
- 构建完成后可在 `ohos/build/outputs/default` 找到未签名 `.hap`

---

## English

A Cursor Skill for setting up and building Flutter HarmonyOS (OpenHarmony/OHOS/鸿蒙) projects on Windows.

### What this skill covers
- Base dependency setup (Git, JDK17, DevEco Studio)
- OpenHarmony (OHOS/鸿蒙) SDK, ArkUI-X, and emulator setup
- Environment variable configuration and validation
- OpenHarmony/OHOS (鸿蒙)-adapted Flutter SDK setup
- End-to-end create, build, sign, and run workflow
- Common troubleshooting paths

### File structure
- `SKILL.md`: Main agent instructions
- `reference.md`: Extended reference and path templates
- `troubleshooting.md`: Common failures and fixes
- `LICENSE`: MIT open-source license

### Installation
Project scope (team sharing):
- Copy to `.cursor/skills/flutter-harmonyos-windows/`

Personal scope (cross-project reuse):
- Copy to `~/.cursor/skills/flutter-harmonyos-windows/`

### Usage examples
Ask Cursor with prompts like:
- "Set up Flutter HarmonyOS development on Windows"
- "Build an OHOS Flutter project with DevEco"
- "How to fix unrecognized hdc command"

Typical trigger terms:
- Flutter HarmonyOS
- OHOS
- 鸿蒙
- DevEco
- OpenHarmony
- ArkUI-X
- Device Manager
- hdc
- signing
- hap build

### 5-minute smoke test
Run in a fresh terminal:

```bash
flutter --version
flutter doctor -v
flutter create --platforms ohos smoke_demo
cd smoke_demo
flutter build app --release
```

Expected:
- `flutter doctor -v` has no blocking errors
- Unsigned `.hap` exists at `ohos/build/outputs/default`
