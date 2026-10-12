# PORDA · 泊达

本地无限画板文件管理与采集工作台。文件和文件夹是真实磁盘对象，画板保存它们的显示位置、文字注释、分组和连线。

**公开测试版 2026.10.13.1 · 应用／安装器版本 1.1.6 · Windows x64 · macOS 14+ Apple 芯片**

PORDA 原名 Port Depot，沿用原应用身份和用户数据目录。

## 本版更新

- 修复复制粘贴快捷键冲突：文件复制使用系统文件剪贴板；在输入框复制文字会替换旧文件内容，待处理的文件复制不能覆盖后来的文字复制。
- 按 **T** 启用文本工具，点击画板插入纯文字注释；**Esc** 退出。编辑文字和输入法组合输入不会误触工具。
- 已有连线文字可单击修改，**Enter** 或失焦保存，**Esc** 取消；连线重绘时保留输入焦点。
- 修复采集港弹窗文件拖入画板：真实文件移动到目标目录，原采集条目随之移除。
- 项目对应真实一级文件夹。文字注释保持为画板内容；复制注释使用普通文本。文件与注释同时选中时需分别复制。
- 组是空间集合，删除组解除分组并保留其中的文件。文件节点的删除按钮、菜单和键盘入口操作源文件。
- 保留圆角连接线、路径中点文字、选中时显示图片文件名，以及右键分享真实文件夹地址。Windows 包继续排除宠物。

## 下载与安装

前往 [2026.10.13.1 Release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1)，两种平台安装包在同一发行页：

| 文件 | 用途 |
| --- | --- |
| `PORDA-2026.10.13.1-Windows-x64-Setup.exe` | Windows x64 离线安装包 |
| `PORDA-2026.10.13.1-macOS-arm64.dmg` | macOS 14+ Apple Silicon 拖拽安装包 |
| `README-PORDA-Windows.txt` / `README-PORDA-macOS.txt` | 平台操作说明 |
| `PORDA-Installation-and-Validation.md` | 验证范围与未测项目 |
| `PORDA-Windows-validation.json` / `PORDA-macOS-validation.json` | 本次验证报告 |
| `PORDA-Release-Manifest.json` / `SHA256SUMS.txt` | 版本与校验值 |

**Windows**：运行 Setup.exe，从桌面或开始菜单打开 PORDA。离线包自带运行时，无需系统 Python、Node.js 或外部浏览器。项目与素材位于 `%LOCALAPPDATA%\Port Depot Data`，替换程序无需删除该目录。详见 [Windows 说明](README-PORDA-Windows.txt)。

**macOS**：打开 DMG，退出正在运行的 PORDA，将 **PORDA.app** 拖入“应用程序”，已有版本时替换。仅保留一个最新版应用入口。数据目录 `~/Library/Application Support/Port Depot` 保持兼容，不要删除该目录来更新程序。详见 [macOS 说明](README-PORDA-macOS.txt)。

这些测试发行物未使用 Windows Authenticode 或 Apple Developer ID 签名／公证；校验值和安装步骤见对应说明。

## 操作与验证范围

复制文件使用系统原生文件剪贴板；在输入框复制使用普通文字。画板注释粘贴不创建 TXT。外部文件拖入移动原件，撤销恢复文件与画板显示；文件选择器导入执行复制。导出包包含真实文件与画板 JSON；导入 ZIP 后保留原 ZIP。

Windows 11 x64 实机 **22 项新版检查通过**，覆盖安装、独立运行、中文路径、原生文件和文字剪贴板、图片剪贴板、真实文件移动及撤销、T 工具、连线编辑、采集港拖入、重启保存和关闭退出。测试使用隔离目录，现有个人数据校验一致。外部拖入使用真实磁盘文件与原生拖拽载荷；手动 Explorer 操作、原生截图、跨版升级及卸载未在本版测试。不能把旧版的测试结果当作本版结果。

macOS 包 **19 项检查通过**，包含实际包内后端与静态文件的 **12 项交互检查**；同版源码另通过 **13 项原生剪贴板／菜单检查**。最低系统、签名完整性和 Launch Services 启动已核对。安装包原生窗口的自动视觉检查未完成，完整范围见 [安装与验收说明](PORDA-Installation-and-Validation.md)。

变化见 [PORDA 更新记录](RELEASE_NOTES.md)。公开发行内容仅包含安装包、校验值、许可和用户说明；不发布私有应用源码、构建输入或个人项目。

现有配套 Skill 保留标识 `portdepot-canvas-agent`，可按 [Skill 说明](portdepot-canvas-agent/SKILL.md) 使用。本次未另行发布 Skill 安装包。

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

**PORDA / 泊达** is a local infinite-canvas file manager and collection workspace, formerly Port Depot. Files are real filesystem objects; canvas JSON stores their presentation, notes, spatial groups and connections.

**Public test release 2026.10.13.1 · application/installer version 1.1.6 · Windows x64 · macOS 14+ Apple silicon**

This update fixes clipboard shortcut conflicts, adds the **T** text tool, makes existing connector labels editable with a single click, and fixes collection-popup drag into the canvas. Files use the native system file clipboard; newer copied text replaces old file references. Notes copy as plain text and paste as annotations without creating TXT files. Files and notes must be copied separately. External file drops move the originals; undo restores them. Deleting a spatial group keeps its files. Windows excludes pets.

Get both platform installers, guides, validation reports and SHA-256 values from the [2026.10.13.1 Release](https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1). **Windows**: run the x64 Setup.exe; no system Python, Node.js or external browser is required. User data stays in `%LOCALAPPDATA%\Port Depot Data`. **macOS**: open the arm64 DMG and drag PORDA.app into Applications, replacing the old application after quitting it. Data stays in `~/Library/Application Support/Port Depot`.

All **22 current-version native Windows checks** passed on Windows 11 x64. They cover installation, Unicode paths, native file/text/bitmap clipboard, real move/undo, collection drag, text tools, connector editing, restart persistence and shutdown of the owned backend. Manual Explorer gestures, screenshot/cropping, cross-version upgrades and uninstallation were not tested for this release. macOS passed **19 package checks**, including **12 packaged-backend interaction checks**, plus **13 native clipboard/menu checks** on the same source revision. Launch Services startup passed; native packaged-window visual automation was not completed. Consult the attached scope report; these results do not cover every device or application.

These test builds are not Authenticode-signed or Apple-notarized; the macOS app is ad-hoc signed. Verify the release origin and SHA-256. The public repository distributes installers and documentation without private application source, build inputs or personal projects.

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
