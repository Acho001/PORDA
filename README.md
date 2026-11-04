# PORDA · 泊达

本地无限画板文件管理与采集工作台。文件和文件夹是真实磁盘对象，画板保存它们的显示位置、文字注释、空间分组和连线。

**macOS 最新公开测试版 2026.11.04.1 · 应用版本 1.1.9 · macOS 14+ Apple 芯片**

Windows 保持 **2026.10.13.1 / 1.1.6**；本次仅发布 macOS，不更新 Windows 包。

PORDA 原名 Port Depot，沿用原应用身份和用户数据目录。

## 本版更新

- **直接选择格式**：右键“格式转换”打开 Filee 风格环形菜单，点击目标格式即转换；每页最多 8 项，支持分页和键盘，无需搜索。
- **图片注释与菜单互斥**：打开右键菜单时收起图片注释预览；注释输入保持焦点，菜单、注释与侧栏独立滚动，不再缩放背后画板。
- **减少大画板重复绘制**：视口按帧合并更新，保留小地图位图及未变化的连线，缓存节点尺寸；图片加载、缩放与跨画板切换正确刷新几何。
- 保留真实文件转换、原文件保护、重名不覆盖及撤销；继续自带 Filee CLI 2.2.0 与兼容 macOS 14 的官方 7-Zip 26.05。
- 保留独立圆形文件夹同步按钮、按层目录读取、只读后台轮询、截图采集、采集港暂存与调度、T 文本工具及系统原生文件复制粘贴。

转换能力由包内及本机实际可用引擎决定，并非所有上游格式都能在此包中转换。未额外打包 FFmpeg、LibreOffice 等大型可选引擎。新增的转换运行环境使 Mac 包体积高于上一版。

## 下载与安装

| 平台 | 下载 |
| --- | --- |
| macOS 14+ Apple Silicon（本次更新） | [2026.11.04.1 Mac Release](https://github.com/Acho001/PORDA/releases/tag/v2026.11.04.1) · `PORDA-2026.11.04.1-macOS-arm64.dmg` |
| Windows x64（保持原版） | [2026.10.13.1 Windows Release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1) · `PORDA-2026.10.13.1-Windows-x64-Setup.exe` |

macOS：退出正在运行的 PORDA，打开 DMG，将 **PORDA.app** 拖入“应用程序”并替换原版本。仅保留一个最新版应用入口。数据继续位于 `~/Library/Application Support/Port Depot`，更新时不要删除该目录。详见 [macOS 说明](README-PORDA-macOS.txt)。

本次 Mac 包为本地 ad-hoc 签名，未进行 Apple Developer ID 签名或公证。请核对发布来源及 SHA256SUMS.txt；系统阻止打开时，可在系统设置“隐私与安全性”中针对 PORDA 允许打开。

## 操作与验证范围

文件复制粘贴使用系统原生文件体系。外部文件拖入移动原件，文件选择器导入执行复制。纯文字注释保存在画板，不生成 TXT；组是空间集合，删除组保留文件。文件节点删除操作真实源文件。导出包包含真实文件与画板 JSON；导入 ZIP 后保留原 ZIP。

本次通过 **51 项文件回归、141 项连接算法用例、画板状态测试、30 项包内检查、12 项既有交互回归**，以及注释/菜单、转换和性能交叉测试。实际包内引擎完成 PNG→JPG/PDF、Markdown→HTML、ZIP→7Z；原件保留及撤销通过。

另以独立临时应用和合成资料完成 **14 项 Mac 原生 WKWebView 检查**：画板进入、注释与菜单互斥、中文输入保存、连线修改、环形菜单点击与键盘分页、真实 JPG 文件及撤销、正常启动关闭。临时应用已注销清理；本轮没有替换本机原有安装。

千节点合成画板的 Chrome 对照测试显示平移/缩放/拖动长帧明显减少；五千节点仍有初始加载、缩放和拖动瓶颈。性能测试不是原生帧率承诺。未在物理 macOS 14 测试，未穷举格式，未重测原生截图与 Finder 拖拽手势。Windows 本次暂停构建与验收。详见 [安装与验证](PORDA-Installation-and-Validation.md) 和 [性能与审查说明](PORDA-Performance-and-Review.md)。

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

**Latest macOS test release: 2026.11.04.1, app 1.1.9, Apple silicon, macOS 14+. Windows remains 2026.10.13.1 / 1.1.6.**

This Mac update uses a direct Filee-style radial format picker without search, resolves image annotation/context-menu and scroll conflicts, and reduces redundant canvas work through frame scheduling, retained connector/minimap layers and dimension caching. Real files, original preservation, undo and the circular folder-sync button remain authoritative. Includes Filee CLI 2.2.0 and compatible official 7-Zip 26.05; no separate Filee GUI, Python or .NET is required. Optional large engines are not all bundled.

Download the [2026.11.04.1 Mac DMG](https://github.com/Acho001/PORDA/releases/tag/v2026.11.04.1); Windows users continue to use the [previous Windows release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1). Quit PORDA and replace the single PORDA.app in Applications. Keep `~/Library/Application Support/Port Depot` to preserve your data. This Mac build is ad-hoc signed and not notarized.

Validation passed 51 filesystem tests, 141 connector cases, state tests, 30 packaged checks, 12 existing interactions, annotation/conversion regressions and 14 targeted native WKWebView checks with synthetic data. Native format selection, real JPG conversion/undo, Chinese annotation input and connector editing were exercised. Temporary validation apps were removed; the existing installed application was not replaced. Synthetic Chrome benchmarks show a substantial improvement at 1,000 nodes; 5,000-node loading/zoom/drag still has limitations. These are not native FPS guarantees. No physical macOS 14 test, exhaustive format sweep, native screenshot or Finder-gesture rerun. Windows was not rebuilt. See the scope and performance reports.

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
