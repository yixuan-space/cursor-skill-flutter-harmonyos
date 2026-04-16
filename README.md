# flutter-harmonyos-windows

[中文](#中文) | [English](#english)

---

## 中文

用于在 Windows 上配置并构建 Flutter HarmonyOS（OpenHarmony/OHOS/鸿蒙）项目的 Cursor Skill。

### 这个 Skill 能做什么
- 检查并补齐基础环境（Git、JDK 17、DevEco Studio）
- 指导安装 OpenHarmony SDK、ArkUI-X 和模拟器
- 校验环境变量与工具链可用性
- 执行 Flutter OHOS 项目的创建、构建、签名与运行流程
- 根据错误现象给出排查步骤

### 仓库文件
- `SKILL.md`：主执行流程（优先阅读）
- `reference.md`：版本、路径与配置细节
- `troubleshooting.md`：常见问题与修复方案
- `CHANGELOG.md`：版本变更记录

### 安装方式
团队共享（项目级）：
- 复制到 `.cursor/skills/flutter-harmonyos-windows/`

个人复用（全局级）：
- 复制到 `~/.cursor/skills/flutter-harmonyos-windows/`

### 推荐提问方式
直接对 Cursor 说：
- “在 Windows 上配置 Flutter 鸿蒙开发环境”
- “帮我构建 OHOS Flutter 项目并生成 hap”
- “hdc 命令不可用怎么排查”

### 5 分钟自检（Smoke Test）
在新终端执行：

```bash
flutter --version
flutter doctor -v
flutter create --platforms ohos smoke_demo
cd smoke_demo
flutter build app --release
```

通过标准：
- `flutter doctor -v` 没有阻断性错误
- 产物目录 `ohos/build/outputs/default` 出现未签名 `.hap`

---

## English

A Cursor Skill for setting up and building Flutter HarmonyOS (OpenHarmony/OHOS) projects on Windows.

### What this skill helps with
- Validate and prepare prerequisites (Git, JDK 17, DevEco Studio)
- Set up OpenHarmony SDK, ArkUI-X, and emulator
- Verify environment variables and toolchain readiness
- Guide create/build/sign/run workflow for Flutter OHOS projects
- Troubleshoot common failures with actionable steps

### Repository files
- `SKILL.md`: Main execution flow (start here)
- `reference.md`: Version matrix and path/config details
- `troubleshooting.md`: Common issues and fixes
- `CHANGELOG.md`: Release and change history

### Installation
Project scope (team sharing):
- Copy to `.cursor/skills/flutter-harmonyos-windows/`

User scope (cross-project reuse):
- Copy to `~/.cursor/skills/flutter-harmonyos-windows/`

### Suggested prompts
- "Set up Flutter HarmonyOS development on Windows"
- "Build my OHOS Flutter project and generate a hap package"
- "How do I fix unrecognized hdc command"

### 5-minute smoke test
Run in a fresh terminal:

```bash
flutter --version
flutter doctor -v
flutter create --platforms ohos smoke_demo
cd smoke_demo
flutter build app --release
```

Pass criteria:
- `flutter doctor -v` has no blocking errors
- Unsigned `.hap` exists in `ohos/build/outputs/default`
