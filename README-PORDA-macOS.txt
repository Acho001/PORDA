PORDA · 泊达 — macOS 2026.10.13.1

适用于 Apple Silicon（M 系列芯片），macOS 14 或更新系统。本包不包含 Intel 版本。

安装：退出正在运行的 PORDA，打开 DMG，将 PORDA.app 拖到“应用程序”。已有版本时选择替换，仅保留 /Applications/PORDA.app 一个安装入口。
原应用 ID 与用户数据目录保持兼容；替换应用无需删除项目或文件。

这是本地 ad-hoc 签名安装包，未进行 Developer ID 签名或 Apple 公证。若系统阻止打开，请在系统设置“隐私与安全性”中针对 PORDA 允许打开。

本次更新：修复复制粘贴快捷键；按 T 后点击画板插入文字；已有连线文字可点击修改；修复采集港文件拖入画板。
安装包已通过完整性、版本、部署目标、包内后端与交互、系统启动检查；完整验收范围见随包说明。

程序／应用版本：1.1.6。公开测试版，许可按随附 LICENSE 和第三方组件各自条款执行。

English: Open the arm64 DMG and drag PORDA.app into Applications after quitting the previous application. Requires Apple silicon and macOS 14+. User data remains in ~/Library/Application Support/Port Depot. This release fixes clipboard shortcuts, adds T annotations, enables editing existing connector labels and fixes collection drag. Package/interaction and Launch Services checks passed; native packaged-window visual automation was not completed. Ad-hoc signed, not notarized. See the attached validation scope and SHA256SUMS.txt.

https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1
