# PORDA · 泊达

完全本地的无限画板文件管理与创意采集工作台。

**公开测试版 v0.5.3 · 构建 2026.10.11.2 · Windows 10/11 x64 · macOS 14+ Apple 芯片**

PORDA 原名 Port Depot。新版沿用原有数据目录与应用身份，升级保留项目、素材和设置。

## 本版更新

- 节点连接线采用圆角折线，支持四个方向的端点、箭头、重新连接和折线拖动。
- 连线文字位于路径长度的中点，线条在文字处留出透明间隔；进入编辑时位置保持一致，画板不会因输入框获得焦点而滚动。
- 图片节点取消外框和标题栏，完整显示图片；文件名仅在选中时显示在右上方，双击文件名可重命名真实文件。
- 优化中文输入、换行、文字格式及输入后的节点尺寸。
- 右键分享当前层级或子文件夹的实际本地地址。接收方需要能访问同一目录，该操作不会上传项目。
- 保留系统原生文件复制：节点复制提供真实文件，文字复制覆盖旧文件剪贴板；外部文件拖入实际移动原文件，撤销恢复文件和画板显示。

## 下载

前往 [最新版 Release](https://github.com/Acho001/port-depot-preview/releases/tag/v0.5.3-porda)：

| 文件 | 用途 |
| --- | --- |
| `PORDA-v0.5.3-Windows-x64-Setup.exe` | Windows 离线安装包 |
| `PORDA-v0.5.3-macOS-arm64.zip` | macOS 应用包，内含 PORDA.app |
| `PORDA-Canvas-Agent-Skill-v0.5.3.zip` | 可安装的画板自动化 Skill |
| `README-PORDA-Windows.txt` / `README-PORDA-macOS.txt` | 平台安装与操作说明 |
| `PORDA-Windows-validation.json` / `PORDA-macOS-validation.json` | 当前构建验证报告 |
| `SHA256SUMS-PORDA.txt` | 下载文件校验值 |

完整变化见 [PORDA 更新记录](RELEASE_NOTES.md)。发行内容仅包含应用、入门指南、Skill 和说明，不包含个人项目、上传素材或账号配置。

## 安装与升级

**Windows**：双击 Setup.exe，选择语言和安装目录，从桌面或开始菜单打开 **PORDA**。无需系统 Python、Node.js、外部浏览器、压缩软件或管理员权限。升级会替换现有应用并清理旧名称快捷方式；项目保存在 `%LOCALAPPDATA%\Port Depot Data`，升级及标准卸载保留这些数据。Windows 版暂不提供宠物功能。详见 [PORDA Windows 说明](README-PORDA-Windows.txt)。

**macOS**：解压 ZIP，得到 **PORDA.app**，将它拖入 **Applications（应用程序）**。更新时先退出应用，再替换现有 PORDA.app；仅保留最新版，不保留旧测试应用或重复快捷方式。项目仍位于 `~/Library/Application Support/Port Depot`，删除旧应用不会删除该目录。详见 [PORDA macOS 说明](README-PORDA-macOS.txt)。

测试发行物尚未使用 Windows Authenticode 或 Apple Developer ID 签名／公证；请核对 Release 来源与 SHA-256，并按系统提示首次打开。

## 验证范围

macOS 最新构建通过 48 项原生回归检查和 141 个连线算法用例；本地升级核对 49 个画板和 193 个原有文件，项目与素材保持完整。Windows [47 项原生检查](https://github.com/Acho001/port-depot-preview/actions/runs/38141320642)通过，验证在 Windows Server 2022 x64 上运行，覆盖真实离线安装、中文路径、原生剪贴板、移动及撤销、画板交互、旧版升级与保留数据的卸载，具体结果见本版报告；这不代表覆盖每台 Windows 10/11 设备。

## 配套 Skill

下载名称使用 PORDA；Skill 的标识仍为 `portdepot-canvas-agent`，已有调用继续有效。它通过应用的实时 API 创建、编辑和检查画板项目，接口与系统文件操作兼容。[Skill 说明](portdepot-canvas-agent/SKILL.md)

## 公开发行范围与许可


PORDA 采用 [PolyForm Noncommercial License 1.0.0](LICENSE)：**非商业用途免费使用；不在许可证允许范围内的商业用途，须事先取得权利人的单独授权。** 商业授权事宜请通过 [GitHub Issues](https://github.com/Acho001/port-depot-preview/issues) 联系维护者。具体允许用途、复制、修改、分发及免责声明以英文许可证原文为准。

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

**PORDA** is a local infinite-canvas file manager and creative collection workspace, formerly named Port Depot.

**Public test release v0.5.3 · build 2026.10.11.2 · Windows 10/11 x64 · macOS 14+ Apple silicon**

This update adds rounded orthogonal connectors, target arrows and four connection sides; labels follow the half-length point of the route and retain their position during editing. Images appear without card chrome, with their filename above the top-right corner only while selected. Chinese input, multiline text and formatting are improved. Context menus can copy the actual current or child-folder path.

The native system clipboard remains authoritative: copied nodes are real files; copied text replaces old file references; external file drops move the original file, and undo restores it. Sharing a folder path copies text locally and requires the recipient to have access to that directory.

Download the current Windows installer, macOS ZIP, Skill, platform guides, validation reports and checksums from the [v0.5.3 Release](https://github.com/Acho001/port-depot-preview/releases/tag/v0.5.3-porda). The assets contain onboarding content only, with no personal projects, uploads or account configuration.

**Windows**: run `PORDA-v0.5.3-Windows-x64-Setup.exe`. The offline installer needs no system Python, Node.js, external browser or administrator rights. Upgrades replace the application and remove old-name shortcuts. User data remains in `%LOCALAPPDATA%\Port Depot Data` across upgrades and standard uninstallation. Pets are excluded.

**macOS**: unzip `PORDA-v0.5.3-macOS-arm64.zip` and drag **PORDA.app** to **Applications**. Quit the old application before replacing it; keep only the latest application. User data remains in `~/Library/Application Support/Port Depot`. This release supports Apple silicon on macOS 14 or later.

These test builds are not Authenticode-signed or Apple-notarized. Verify their origin and SHA-256. macOS validation includes 48 native regression checks and 141 routing cases. All 47 [native Windows checks](https://github.com/Acho001/port-depot-preview/actions/runs/38141320642) passed on Windows Server 2022 x64; consult the attached report for the tested scope.

The companion Skill keeps the compatible identifier `portdepot-canvas-agent`, with PORDA names in its display and documentation.

### Public distribution scope and license


PORDA uses the [PolyForm Noncommercial License 1.0.0](LICENSE): **noncommercial use is free; commercial purposes outside the license's permitted uses require prior, separate authorization from the rights holder.** Contact the maintainer through [GitHub Issues](https://github.com/Acho001/port-depot-preview/issues) about commercial licensing. The English license text governs permitted purposes, copying, modification, distribution, and disclaimers.

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
