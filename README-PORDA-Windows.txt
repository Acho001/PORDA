PORDA · 泊达 2026.10.13.1 — Windows x64 公开测试版
程序／安装器版本：1.1.6

安装：下载 PORDA-2026.10.13.1-Windows-x64-Setup.exe，运行安装器，从桌面或开始菜单打开 PORDA。当前用户安装，自带运行时，不需要系统 Python、Node.js 或外部浏览器。Windows 版不包含宠物窗口、设置或资源。

数据：%LOCALAPPDATA%\Port Depot Data。保留原应用身份和数据目录。替换程序无需删除项目；备份应完整复制数据目录。不要在安装目录中存储个人项目。

操作：Ctrl+C / Ctrl+V 使用系统剪贴板。复制文件提供真实文件；输入框和文字注释复制使用普通文字。文件与注释请分别复制。按 T 后点击画板插入文字，Esc 退出。已有连线文字可单击修改，Enter 或失焦保存，Esc 取消。采集港弹窗文件拖入画板会移动原文件；外部文件拖入也是移动，Ctrl+Z 可恢复。右键分享复制实际本地文件夹地址。

验证：Windows 11 x64 实机 22 项新版检查通过；完整范围见 PORDA-Installation-and-Validation.md 和 PORDA-Windows-validation.json。本版未测试跨版升级、卸载、手动 Explorer 操作或原生截图／裁剪，历史验证不能替代本版结果。

此包未进行 Authenticode 签名。请核对官方发行页和 SHA256SUMS.txt。许可按随附 LICENSE 与第三方组件各自条款执行；应用私有源码和个人项目不在公开发行内容中。

English: Run the x64 Setup.exe; the offline installer includes its runtimes and excludes pets. User data stays in %LOCALAPPDATA%\Port Depot Data. Native file copy, newer text replacement, move/undo, T annotations, connector-label editing, collection drag and restart persistence passed on Windows 11 x64. Cross-version upgrades/uninstallation, manual Explorer gestures and native capture/cropping were not tested in this release. The installer is unsigned. Consult the attached scope report, license and SHA256SUMS.txt.

https://github.com/Acho001/PORDA/releases/tag/v2026.10.13.1
