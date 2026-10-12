# PORDA · 泊达 2026.10.13.1

macOS 和 Windows 安装包在本发行页一同提供。程序／安装器版本为 **1.1.6**，内部构建为 **2026.10.13.1**。本版继续作为公开测试版发行。

- 修复复制粘贴快捷键冲突。文件使用系统文件剪贴板，文字输入使用普通文字复制；后复制的文字会替换先复制的文件，待处理的文件复制不会覆盖新文字。
- 新增 **T** 文本工具：按 T 后点击画板插入纯文字注释，Esc 退出；编辑中输入 T 和中文输入法组合输入不会误触工具。
- 已有连接线文字可单击修改；Enter 或失焦保存，Esc 取消，撤销可恢复；几何重绘不替换正在编辑的输入框。
- 修复采集港弹窗拖入画板。原文件移动到画板目录，采集港原位置和条目同步移除。
- 明确文件和注释分别复制。文字注释保持为画板内容；删除空间组解除分组并保留文件；文件节点的删除操作作用于源文件。
- 保留圆角连接线、路径中点文字、图片选中时的文件名及右键分享本地目录地址。Windows 排除宠物功能；应用身份和数据目录保持兼容。

## 下载

- **Windows x64**：`PORDA-2026.10.13.1-Windows-x64-Setup.exe`
- **macOS 14+ / Apple Silicon**：`PORDA-2026.10.13.1-macOS-arm64.dmg`
- 安装说明、验证报告、许可、产物清单和 `SHA256SUMS.txt` 一同提供。

## 本版验证

Windows 11 x64 实机 22 项新版检查通过，覆盖安装、独立运行、中文路径、原生文件／文字／图片剪贴板、真实文件移动与撤销、T 工具、连线文字修改、采集港拖入、重启保存及关闭退出。使用独立测试目录，个人数据校验一致；外部拖入验证采用真实磁盘文件与原生拖拽载荷。

macOS 19 项包内检查通过，其中包含针对包内实际后端和资源的 12 项交互检查；同版源码的 13 项原生菜单／剪贴板检查通过。最低系统、签名完整性、入门资源和 Launch Services 启动已核对。

本版未测试 Windows 跨版升级、卸载、手动 Explorer 操作与原生截图／裁剪；macOS 包原生窗口自动视觉检查未完成。完整范围见 `PORDA-Installation-and-Validation.md` 和对应 JSON 报告。旧版结果不作为本版验证结论。

macOS 采用本地 ad-hoc 签名，未做 Apple 公证；Windows 未做 Authenticode 签名。仅发布安装包、说明、校验值与许可，不含应用私有源码、内部构建输入、个人项目或凭据。许可按随附 `LICENSE` 和第三方组件各自的条款执行。

## English

Both **macOS arm64 DMG** and **Windows x64 Setup.exe** are provided in this release. Build: **2026.10.13.1**; application/installer version: **1.1.6**. This remains a public test release.

The update fixes clipboard shortcuts and stale file-copy races, adds the T annotation tool, enables single-click editing of existing connector labels with Enter/blur save and Escape cancel, and fixes collection-popup drag as an actual file move. Notes remain annotations and copy as plain text; files and notes are copied separately. Spatial-group deletion keeps files. Stable app IDs and data directories are retained; Windows pets remain excluded.

All 22 current-version native Windows checks passed on Windows 11 x64. macOS passed 19 package checks, including 12 packaged-backend interactions, and 13 native clipboard/menu checks on the same source revision. Launch Services startup passed. Windows cross-version upgrade/uninstall, manual Explorer gestures and screenshot/cropping, and macOS native packaged-window visual automation were not verified for this release. See attached reports for scope and SHA-256 for download integrity. The Windows installer is unsigned; the macOS app is ad-hoc signed and not notarized. Private application source and personal projects are excluded.


---

# PORDA · 泊达 v0.5.3 · 2026.10.11.2 · 2026-10-11

- 产品正式更名为 **PORDA**，中文名称 **泊达**；安装包、窗口、快捷方式、平台说明和下载文件使用新名称，沿用兼容的应用身份与数据目录。
- 两个相向节点之间采用简单的三段折线与两个圆角，端点贴合节点真实边缘并显示终点箭头；保留四方向端点、重连与折线调整。
- 连线文字放在整条圆角路径长度的中点，以透明间隔断开文字背后的线条；拖动折线时文字跟随中点，进入编辑时保持原位置。
- 修复连线输入框获得焦点导致整张画板滚动的问题，中文输入法确认不会提前结束编辑。
- 图片取消卡片外框、标题栏和内边距，按真实比例完整显示；仅选中时在右上方显示文件名，双击可重命名真实文件。
- 改进文字节点中文输入、换行、加粗等格式与完成编辑后的尺寸。
- 右键可复制当前层级或子文件夹的实际本地目录地址；该操作不上传项目，接收方需要能访问同一目录。
- 保留系统原生文件复制和移动：文字复制替换旧文件引用，节点复制提供真实文件，外部普通文件拖入实际移动原件，撤销恢复原文件与画板显示。
- Windows 保留离线 NSIS 安装、中文路径、系统剪切标志、端口避让、升级和标准卸载保留数据；本版继续排除宠物功能。
- macOS 明确最低系统为 14，并固定编译目标，避免开发工具默认版本高于本机系统而导致无法启动。
- 本地更新仅保留最新版 PORDA.app，清理过时测试应用和重复入口；项目与素材继续保留。

验证：macOS 48 项原生回归检查、141 个连线算法用例通过；安装包解压后签名校验通过，入门项目 10 张画板、13 个文件素材可读取。本地升级核对 49 个画板与 193 个文件，数据未变化。Windows [47 项最新原生验证](https://github.com/Acho001/PORDA/actions/runs/38141320642)通过，结果见本版 Release 的 `PORDA-Windows-validation.json`；覆盖实际安装、原生文件剪贴板、移动及撤销、最新画板交互、旧版升级与卸载保留数据。Windows 验证环境为 Windows Server 2022 x64。

Windows 安装器与 macOS 应用版本均为 **1.1.4**，内部构建均为 **2026.10.11.2**。本版仅发布应用二进制、入门指南、Skill、平台说明、验证报告和 SHA-256，不包含个人项目、素材、账号配置或内部构建输入。

English: This release renames the product to PORDA / 泊达, introduces simple rounded orthogonal connectors with target arrows and half-length labels, preserves label position during editing, removes image card chrome while showing selected filenames, improves Chinese text editing, and adds local folder-path sharing. Native file clipboard and move/undo behavior remain authoritative. Compatible application IDs and data directories are retained, Windows pets are excluded, and macOS explicitly targets version 14 or later. Both platforms use build 2026.10.11.2 and product version 1.1.4. See the attached native validation reports and SHA-256 file for the tested scope and download verification.

历史记录保留当时的产品名称和许可说明。

---

# v0.5.2 · 2026.10.07.2 · 2026-10-07

- 统一使用系统剪贴板，移除节点 JSON 剪贴板与延迟粘贴回退。复制节点提供真实文件，选中文字或在输入框中复制提供文字。
- 修复“复制新文字后仍粘贴旧节点”：复制文字清除旧文件引用，正在准备的文件复制无法覆盖后续文字复制。
- 外部文件拖入画板实际移动到画板目录；文件粘贴和复制产生独立文件，撤销同时恢复真实文件与画板显示。
- 文字节点复制为 TXT；其他结构内容使用携带素材的真实文件或文件夹，可粘贴到支持文件的系统位置。
- macOS 补齐原生编辑菜单，修复真实 ⌘A／⌘C／⌘V 不生效；增加单实例检查，避免第二个窗口与后台脱节。
- Windows 兼容系统图片剪贴板和原生剪切标志；读取与写入采用当前原生剪贴板接口。
- Windows 原生文件拖入取得真实文件引用后再异步准备画板，避免事件结束后文件列表失效；旧导入监听不再覆盖原生移动动作。
- Windows 保留离线 NSIS 安装、中文路径、LocalAppData 数据、端口避让、升级及卸载保留数据，继续排除宠物功能。

Windows 安装器／macOS 应用版本均为 1.1.3。[Windows 原生验证](https://github.com/Acho001/PORDA/actions/runs/37611386636)的 33 项检查全部通过，覆盖安装、剪贴板、原文件移动及撤销、升级和卸载，详情见 Release 的 `Windows-validation.json`；macOS 验证见 `macOS-clipboard-validation.json`，包括旧版真实按键失败的复现、新版真实按键验证及 23 项原生交互检查。Windows 验证环境为 Windows Server 2022 x64；未宣称已覆盖每台 Windows 10/11 电脑。

发行内容仅含应用包、入门指南、Skill、用户说明和验证报告，不含个人项目、素材或账号配置。应用及本次附带 Skill 按随附 PolyForm Noncommercial License 1.0.0 发行；历史版本随附的许可仍保留。

---

# Windows v0.5.1 · 2026.10.01.1 · 2026-10-01

## 中文

- 将最新画布交互、语言与主题设置、回收站体验带到 Windows 10/11 x64。
- 提供完整离线安装引导、桌面与开始菜单快捷方式、标准卸载；无需外部压缩软件、系统 Python 或浏览器。
- 修复旧封装依赖外部解压入口、使用旧前后端和向安装目录写数据的问题。
- 适配中文及带空格的安装/文件路径、Windows 文件剪贴板、Ctrl+C/Ctrl+V、资源管理器、原生导入和导出。
- 支持截图采集、裁剪及本地视频缩略图；全局截图快捷键可修改。
- 关闭软件时停止自己的后台；重复启动聚焦同一窗口。服务端口占用时自动避让，语言、主题与快捷键仍保留。
- 兼容旧 storage/library 数据目录，无需管理员权限或符号链接。覆盖升级、标准卸载保留用户项目和素材。
- Windows 版不提供宠物窗口、设置入口或资源。
- 只附 10 张入门指南画板、空采集库和最新版配套 Skill；没有个人项目、上传素材、账号配置或应用开发源码。

此发行物的 Windows 原生验证结果见 Release 附件 `Windows-validation.json`。验证运行在 Windows Server 2022 x64；不代表已测试每一台 Windows 10/11 用户电脑。安装器版本为 1.1.1，未使用 Authenticode 证书签名。请核对 SHA-256 和下载来源。

## English

- Brings the latest canvas interactions, language/theme preferences and trash experience to Windows 10/11 x64.
- Complete offline installer, desktop/Start menu shortcuts and standard uninstallation. No system Python, external browser or archive utility is needed.
- Fixes stale frontend/backend packaging, external extraction dependencies and writes to the installation directory.
- Supports Chinese paths, paths containing spaces, native file clipboard operations, Ctrl+C/Ctrl+V, Explorer and native import/export dialogs.
- Includes capture/cropping and local video thumbnails, configurable global capture shortcuts, single-instance activation and owned-backend shutdown.
- Handles occupied ports while retaining desktop preferences. Migrates older library layouts without symbolic links or administrator rights.
- Upgrades and standard uninstallation preserve user projects and media. Pets are excluded from the Windows package.
- Bundles ten onboarding canvases, an empty inbox and the latest companion Skill. Personal projects, uploads, credentials and application development sources are excluded.

Native validation results are attached as `Windows-validation.json`. Tests run on Windows Server 2022 x64; individual Windows 10/11 machines still need user acceptance. Installer version: 1.1.1. This test package is not Authenticode-signed; verify its source and SHA-256.

---

# v0.5.1 · 2026.09.30.1 · 公开测试更新 / Public test update

## 中文

- 设置重新分为通用、截图采集、桌宠三类；统一布局、开关和数值展示，改善小窗口适配及键盘焦点。
- 增加中文、English、跟随系统语言；首次安装读取系统首选语言列表中的首个支持语言，不修改用户内容。
- 回收站增加一键清空与二次确认，使用 ID 快照保护已恢复的画板。清理画板记录不意味着删除所有关联素材。
- 同步上一轮文件复制优化：复制文件及批量复制用于系统文件剪贴板；不同聊天软件是否接受文件粘贴取决于目标软件。
- 修复打包程序启动修改签名资源的问题；DMG 提供拖入 Applications 的安装引导，运行数据写入用户可写目录。
- 更新 Skill：运行时 API 发现、具体 ID 路由匹配、结构化编排、布局审计、可视化推理及安全备份规则；Python 适配器不依赖特定 AI 模型。
- 包内仅保留入门指南示例、空采集库和空默认项目；新版 Skill 放入指南的「05 导入导出与 Agent」。不含个人项目、上传素材、账号配置、备份或应用源代码。

验证：隔离启动、指南 10 张画板及空采集库、实际 ID API 调用、Skill 格式检查、签名完整性；设置/语言/回收站已做隔离交互回归测试。未声明 Intel 或 Windows 兼容。

## English

- Reorganized settings into General, Capture & collect, and Desktop pet, with consistent controls, responsive layout and keyboard focus handling.
- Added Chinese, English and system-language preferences. First launch selects the first supported system-preferred language; user content is preserved.
- Added confirmed bulk trash clearing using an ID snapshot, protecting restored canvases. Removing canvas records does not necessarily remove all media.
- Includes improved single and multi-file copying through the system file clipboard; destination apps determine paste support.
- Fixed startup modification of signed bundle resources. The DMG guides users to drag into Applications; runtime data uses writable user storage.
- Updated the Skill with live API discovery, concrete-ID route matching, structured composition, layout audits, visual reasoning and backup rules. Python adapters are model-independent.
- Bundles only the onboarding guide, empty collection library and empty default project. Updated Skill included in guide chapter 05. No personal projects, uploads, account configuration, backups or app source code.

Validated isolated startup, ten guide canvases plus empty inbox, concrete-ID API calls, Skill format and signature; settings/language/trash interaction regressions were tested in isolation. No Intel or Windows compatibility claim.

macOS 13+ / Apple silicon. Ad-hoc signed, not Apple-notarized. Skill MIT license only; app distributed as a test binary. Still being optimized: back up important projects and report problems through Issues.

---

## v0.5 archive

Port Depot v0.5 is a public test release. This package includes the macOS Apple-silicon installer and the Port Depot Canvas Agent Skill.

Port Depot is still being optimized. Future updates will continue to improve canvas interactions, file collection, import/export, stability, and the overall experience.

Port Depot's key idea is to turn file organization into a visual workspace: place assets on an infinite canvas, connect them with notes and relationships, collect material before organizing it, and export portable projects that can also be edited with the included Agent Skill.

Port Depot v0.5 是公开测试版，提供 Apple 芯片 Mac 安装包与 Port Depot Canvas Agent Skill。

软件仍处于持续优化阶段，后续会继续改进画布交互、文件采集、导入导出、稳定性与整体使用体验。

Port Depot 的核心卖点是把文件整理变成可视化工作空间：在无限画布上摆放素材，用批注和关系线呈现思路，先采集再编排，并导出可移交、可由随附 Agent Skill 辅助处理的项目。

The installer contains an ad-hoc signed, non-notarized app. The Skill is released under MIT; the application source code is not included in this release.

安装包内应用使用临时签名，尚未经过 Apple 公证。本次仅发布安装包和 Skill，不包含应用源代码；MIT 许可仅适用于 Skill。
