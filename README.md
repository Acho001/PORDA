# PORDA · 泊达

本地无限画板文件管理与采集工作台。文件和文件夹是真实磁盘对象，画板保存它们的显示位置、文字注释、空间分组和连线。

**macOS 最新公开测试版 2026.11.02.1 · 应用版本 1.1.7 · macOS 14+ Apple 芯片**

Windows 保持 **2026.10.13.1 / 1.1.6**；本次仅发布 macOS，不更新 Windows 包。

PORDA 原名 Port Depot，沿用原应用身份和用户数据目录。

## 本版更新

- 文件节点右键新增 **格式转换**。二级弹窗按当前文件和本地可用引擎列出目标格式，支持搜索。转换生成真实文件，保留原件；重名不覆盖，支持文件撤销。
- 集成 Filee 2.2.0 命令行及自包含运行环境，安装后无需另外安装 Filee GUI、Python 或 .NET。附带兼容 macOS 14 的官方 7-Zip 26.05。
- 右上四个操作按钮左侧新增 **独立圆形刷新同步按钮**。先保存当前编辑，再扫描真实文件夹，同步新增、改名、修改与删除，保留仍存在节点的位置、批注和分组。
- 转换弹窗隔离画板快捷键；媒体自动尺寸和磁盘元数据不再被误判为阻止文件撤销的后续编辑。
- 继续保留截图采集、采集港暂存与拖放调度、T 文本工具、可编辑连线文字和系统文件复制粘贴。

转换能力由包内及本机实际可用引擎决定，并非所有上游格式都能在此包中转换。未额外打包 FFmpeg、LibreOffice 等大型可选引擎。新增的转换运行环境使 Mac 包体积高于上一版。

## 下载与安装

| 平台 | 下载 |
| --- | --- |
| macOS 14+ Apple Silicon（本次更新） | [2026.11.02.1 Mac Release](https://github.com/Acho001/PORDA/releases/tag/v2026.11.02.1) · `PORDA-2026.11.02.1-macOS-arm64.dmg` |
| Windows x64（保持原版） | [2026.10.13.1 Windows Release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1) · `PORDA-2026.10.13.1-Windows-x64-Setup.exe` |

macOS：退出正在运行的 PORDA，打开 DMG，将 **PORDA.app** 拖入“应用程序”并替换原版本。仅保留一个最新版应用入口。数据继续位于 `~/Library/Application Support/Port Depot`，更新时不要删除该目录。详见 [macOS 说明](README-PORDA-macOS.txt)。

本次 Mac 包为本地 ad-hoc 签名，未进行 Apple Developer ID 签名或公证。请核对发布来源及 SHA256SUMS.txt；系统阻止打开时，可在系统设置“隐私与安全性”中针对 PORDA 允许打开。

## 操作与验证范围

文件复制粘贴使用系统原生文件体系。外部文件拖入移动原件，文件选择器导入执行复制。纯文字注释保存在画板，不生成 TXT；组是空间集合，删除组保留文件。文件节点删除操作真实源文件。导出包包含真实文件与画板 JSON；导入 ZIP 后保留原 ZIP。

本次完成 **49 项源码文件回归**和 **28 项 Mac 安装包检查**，包含原有 **12 项包内交互回归**，以及实际包内 Filee 的 PNG→JPG/PDF、Markdown→HTML、ZIP→7Z。右键弹窗、转换撤销、手动目录同步、未保存批注保护、弹窗快捷键和宽窄屏布局已在实际包内后端验证。包内引擎不依赖开发机的 Filee 安装。

最低系统与原生组件部署目标、签名完整性、入门资料、安装资源不被运行时改写，以及 Launch Services 正常启动已核对。测试运行于当前 Mac，没有在 macOS 14 实机运行；未穷举全部转换格式，也未重测本次安装包原生窗口中的 Finder 手势、截图、系统剪贴板或原生窗口自动视觉操作。Windows 未在本次重新构建或验收。完整范围见 [安装与验收说明](PORDA-Installation-and-Validation.md)。

公开仓库提供安装包、更新说明、许可和校验值；私有应用源码、构建输入与个人项目不公开。配套 Skill 保留 [portdepot-canvas-agent](portdepot-canvas-agent/SKILL.md) 标识，本次未另发 Skill 包。

## 公开发行范围与许可


PORDA 采用 [PolyForm Noncommercial License 1.0.0](LICENSE)：**非商业用途免费使用；不在许可证允许范围内的商业用途，须事先取得权利人的单独授权。** 商业授权事宜请通过 [GitHub Issues](https://github.com/Acho001/PORDA/issues) 联系维护者。具体允许用途、复制、修改、分发及免责声明以英文许可证原文为准。

本许可适用于本仓库的项目自有文件、当前主分支的 [PORDA Canvas Agent Skill](portdepot-canvas-agent/LICENSE)，以及自本次许可声明起提供的 PORDA 应用二进制发行物。本仓库提供 Windows 和 macOS 测试安装包，尚未公开应用源代码。第三方组件仍按各自的许可证授权；用户自己的项目、素材和导出内容不因使用本应用而适用本许可证。

许可变更日期：**2026-10-01**。本次变更不撤销此前已授予的许可；历史 Release ZIP 和安装包内已明确按 MIT 发布的 Skill 文件继续适用其随附的 MIT 许可证。

PolyForm Noncommercial 是限制商业用途的源码可见许可证，不属于 OSI 定义的开源许可证。

##### 可信时间戳存证信息

| 项目 | 信息 |
| --- | --- |
| 证书编号 | `TSA-01-20261001184483245` |
| 时间戳认证码 | `F940563D6514D6762259347A97451217904A33B0D3D1F9F401D106DAB97BA637` |
| 时间戳签发时间 | 2026-10-01 17:18:39 (UTC+8) |

以上登记信息由项目维护者提供；具体认证文件及范围以认证证书和对应原始文件为准。本记录作为软件材料的存证说明，使用授权仍按上述许可证执行。



---

## English

**PORDA / 泊达** is a local canvas file manager and collection workspace, formerly Port Depot. Real files stay in real folders; the canvas stores layout, notes, spatial groups and connections.

**Latest macOS test release: 2026.11.02.1, app 1.1.7, Apple silicon, macOS 14+. Windows remains 2026.10.13.1 / 1.1.6.**

This Mac update adds a file context-menu conversion dialog powered by bundled Filee 2.2.0, and a separate circular refresh button beside the existing four-button toolbar. Conversion keeps the original and creates real output files with collision protection and undo. Refresh saves current edits before scanning the physical folder for additions, changes, renames and deletions. Filee's CLI runtime and a macOS-14-compatible official 7-Zip 26.05 are included; no separate Filee GUI, Python or .NET installation is required. Large optional engines such as FFmpeg and LibreOffice are not included, and only locally available routes are offered. The bundled runtime increases the Mac download size.

Download the [2026.11.02.1 Mac DMG](https://github.com/Acho001/PORDA/releases/tag/v2026.11.02.1); Windows users continue to use the [previous Windows release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1). Quit PORDA and replace the single PORDA.app in Applications. Keep `~/Library/Application Support/Port Depot` to preserve your data. This Mac build is ad-hoc signed and not notarized.

Validation includes 49 source filesystem regressions, 28 packaged Mac checks, 12 existing packaged-backend interactions, new conversion/sync UI checks, actual bundled-engine conversions and normal Launch Services startup. Deployment targets were inspected, but macOS 14 was not tested on a physical machine. Not every format was exercised; native packaged-window visual automation, Finder gestures, screenshots and native system-clipboard acceptance were not rerun for this release. Windows was not rebuilt. See the [scope report](PORDA-Installation-and-Validation.md) and release SHA-256 values.

### Public distribution scope and license


PORDA uses the [PolyForm Noncommercial License 1.0.0](LICENSE): **noncommercial use is free; commercial purposes outside the license's permitted uses require prior, separate authorization from the rights holder.** Contact the maintainer through [GitHub Issues](https://github.com/Acho001/PORDA/issues) about commercial licensing. The English license text governs permitted purposes, copying, modification, distribution, and disclaimers.

This license covers project-owned files in this repository, the [PORDA Canvas Agent Skill](portdepot-canvas-agent/LICENSE) on the current main branch, and PORDA application binaries offered from this licensing notice onward. This repository provides Windows and macOS test installers; application source code is not currently published. Third-party components retain their own licenses. Users' own projects, assets, and exports do not become subject to this license merely through use of the application.

License change date: **2026-10-01**. This change does not revoke previously granted licenses. Skill files explicitly released under MIT in historical Release ZIPs and installers remain under their bundled MIT license.

PolyForm Noncommercial is a source-available license restricting commercial use, rather than an open-source license under the OSI definition.

##### Trusted timestamp record

| Field | Value |
| --- | --- |
| Certificate number | `TSA-01-20261001184483245` |
| Timestamp authentication code | `F940563D6514D6762259347A97451217904A33B0D3D1F9F401D106DAB97BA637` |
| Timestamp issued at | 2026-10-01 17:18:39 (UTC+8) |

These registration details were supplied by the project maintainer. The certified files and scope are determined by the certificate and its corresponding original files. This record documents the timestamp evidence for the software materials; usage rights remain governed by the license above.
