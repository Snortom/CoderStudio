# CoderStudio

[![最新版本](https://img.shields.io/github/v/release/Snortom/CoderStudio?label=release&color=0ea5e9)](https://github.com/Snortom/CoderStudio/releases/latest)
[![支持平台](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20HarmonyOS-0ea5e9)](#下载)
[![官方网站](https://img.shields.io/badge/website-coderstudio.cn-0ea5e9)](https://www.coderstudio.cn)

CoderStudio 是一款面向开发者的一站式桌面工作台，将 API 调试、SSH / SFTP 远程管理、数据库客户端、AI 助手、项目管理、笔记、待办、流程图与思维导图整合在同一个应用中。

> 本仓库为 CoderStudio 官方发行仓库，仅用于发布各平台安装包与版本说明，不包含应用程序源代码。

- 官方网站：<https://www.coderstudio.cn>
- 下载地址：<https://github.com/Snortom/CoderStudio/releases/latest>
- 更新日志：<https://github.com/Snortom/CoderStudio/releases>
- 问题反馈：<https://github.com/Snortom/CoderStudio/issues>

## 下载

前往 [Releases](https://github.com/Snortom/CoderStudio/releases/latest) 页面下载最新版本。请根据操作系统与 CPU 架构选择对应安装包：

| 平台              | 架构                 | 安装包                                                              |
| ----------------- | -------------------- | ------------------------------------------------------------------- |
| Windows 10 / 11   | x64                  | `CoderStudio-<version>-x64.exe`                                     |
| Windows 10 / 11   | ARM64                | `CoderStudio-<version>-arm64.exe`                                   |
| macOS 13+         | Intel（x64）         | `CoderStudio-<version>-x64.dmg`                                     |
| macOS 13+         | Apple Silicon（arm64） | `CoderStudio-<version>-arm64.dmg`                                   |
| Linux             | x64                  | `CoderStudio-<version>-x86_64.AppImage`、`CoderStudio-<version>-amd64.deb` |
| Linux             | arm64                | `CoderStudio-<version>-arm64.AppImage`、`CoderStudio-<version>-arm64.deb`  |
| HarmonyOS 5.0+    | ARM64                | `CoderStudio-<version>-arm64.hap`、`CoderStudio-<version>-arm64.app` |

其中 `<version>` 为版本号。下载前请确认设备架构，安装包与架构不匹配时应用无法启动。

> 国内网络环境建议优先使用官网下载页，速度通常更快：<https://www.coderstudio.cn>

## 安装

### Windows

1. 下载与系统架构匹配的 `.exe` 安装包。
2. 双击运行，按向导选择安装目录并完成安装。
3. 安装程序默认按「所有用户」安装，需要管理员权限。
4. 安装完成后自动启动，并在桌面与开始菜单创建快捷方式。

若首次运行时出现 Windows SmartScreen 提示，可点击「更多信息」→「仍要运行」。覆盖安装会保留已有配置与本地数据。

### macOS

1. 下载与芯片匹配的 `.dmg`：Intel 机型选择 `x64`，Apple Silicon 机型选择 `arm64`。
2. 打开磁盘映像，将 **CoderStudio** 拖入「应用程序」文件夹。
3. 从「应用程序」中启动 CoderStudio。

若首次启动提示「无法验证开发者」，可在「系统设置 → 隐私与安全性」中允许打开。若提示应用已损坏，通常是 Gatekeeper 隔离属性导致，可执行：

```bash
sudo xattr -dr com.apple.quarantine /Applications/CoderStudio.app
```

### Linux

AppImage（免安装）：

```bash
chmod +x CoderStudio-<version>-x86_64.AppImage
./CoderStudio-<version>-x86_64.AppImage
```

如果系统缺少 FUSE 2：

```bash
sudo apt install libfuse2        # Ubuntu 22.04 / Debian 11
sudo apt install libfuse2t64     # Ubuntu 24.04 及以上

# 或者不依赖 FUSE，直接解包运行：
./CoderStudio-<version>-x86_64.AppImage --appimage-extract-and-run
```

Debian / Ubuntu 安装 deb：

```bash
sudo apt install ./CoderStudio-<version>-amd64.deb
```

arm64 设备请将文件名中的 `x86_64` / `amd64` 替换为 `arm64`。

### HarmonyOS

1. 下载 ARM64 架构的 `.hap` 或 `.app` 安装包（`.app` 为包含全部模块的应用包）。
2. 在设备上开启开发者模式与 USB 调试，连接电脑后使用 HarmonyOS SDK 中的 `hdc` 工具安装：

```bash
hdc install CoderStudio-<version>-arm64.hap
# 或
hdc install CoderStudio-<version>-arm64.app
```

3. 安装完成后在桌面或应用列表中启动 CoderStudio。

## 系统要求

| 平台    | 最低要求                                                                                         |
| ------- | ------------------------------------------------------------------------------------------------ |
| Windows | Windows 10 及以上，x64 或 ARM64                                                                  |
| macOS   | macOS 13 (Ventura) 及以上，Intel 或 Apple Silicon                                                |
| Linux   | 主流 64 位发行版（x86_64 / arm64）；AppImage 需要 FUSE 2，或使用 `--appimage-extract-and-run` 运行 |
| HarmonyOS | HarmonyOS NEXT（5.0）及以上，ARM64                                                            |
| 硬件    | 4 GB 内存及以上，建议预留 2 GB 磁盘空间                                                          |

> CoderStudio 目前仅提供 64 位版本，不支持 32 位系统。

## 功能概览

- API 调试
- SSH / SFTP
- 数据库
- AI 助手
- 项目管理
- 笔记
- 待办
- 流程图与思维导图
- 错误日志与反馈中心
- 插件系统与能力市场

## 自动更新

应用内置自动更新能力。登录账号后，可在「设置 → 软件更新」中检查、下载并重启安装新版本，也可以开启「启动时自动检查更新」。

- 自动更新由官方更新源提供；GitHub Releases 用于手动下载完整安装包、查看历史版本与回滚。
- 应用不会在后台强制安装更新，下载完成后由你决定何时重启。
- 升级前建议先通过「数据备份」导出一份本地数据。

## 数据与隐私

- 应用数据默认保存在本地（SQLite 数据库），绝大多数本地功能无需登录即可使用。
- 密码、Token 等敏感字段使用 Electron `safeStorage` 结合系统密钥环加密存储。
- 登录、会员、应用市场与 AI 等在线功能会将必要的账号与请求信息发送至官方服务器。
- 卸载程序默认不会删除本地数据；如需彻底清除，请手动删除系统用户数据目录下的 CoderStudio 数据文件夹。

## 常见问题

### macOS 提示「应用已损坏，无法打开」怎么办？

先确认下载的安装包与芯片架构匹配。若架构正确，通常是 Gatekeeper 隔离属性导致，执行上文 `xattr` 命令后再尝试打开。

### Linux 上 AppImage 无法运行怎么办？

确认已赋予可执行权限，并安装 FUSE 2（`libfuse2` 或 `libfuse2t64`）。如果无法安装 FUSE，可使用 `--appimage-extract-and-run` 参数运行。

### Windows 安装时出现 SmartScreen 提示？

点击「更多信息」→「仍要运行」即可继续安装。请确保安装包来自本仓库 Releases 或官网，避免使用来源不明的文件。

### 是否支持 32 位系统？

不支持。当前版本仅提供 Windows x64 / ARM64、macOS Intel / Apple Silicon、Linux x86_64 / arm64、HarmonyOS ARM64 安装包。

### 覆盖安装会丢失数据吗？

不会。应用配置与本地数据库独立于安装目录，覆盖安装或升级不会删除已有数据。仍建议在升级前备份重要数据。

### 自动更新提示需要登录？

软件更新属于登录门槛操作，请先登录账号，再进入「设置 → 软件更新」检查更新。也可以直接从 Releases 下载新版本覆盖安装。

### 如何回滚到旧版本？

从 Releases 下载旧版本安装包覆盖安装即可。回滚前请备份数据，旧版本可能无法读取新版本已升级的数据库结构。

### 下载速度慢怎么办？

优先使用官网下载页；GitHub Releases 可作为备用渠道。

## 反馈与支持

- 官网：<https://www.coderstudio.cn>
- 问题反馈：<https://github.com/Snortom/CoderStudio/issues>

提交问题时请尽量附上以下信息，便于快速定位：

- 操作系统版本与 CPU 架构
- CoderStudio 版本号（「设置 → 关于」中查看）
- 复现步骤、预期结果与实际结果
- 相关截图或错误日志

## 版权

Copyright © 2026 Cloud. 保留所有权利。

本仓库仅用于分发 CoderStudio 官方安装包。未经授权，请勿修改安装包、二次打包或以官方名义分发。
