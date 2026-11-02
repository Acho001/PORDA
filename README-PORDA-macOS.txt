PORDA · 泊达 — macOS 2026.11.02.1 / 应用版本 1.1.7

支持 Apple Silicon（M 系列芯片），macOS 14 或更新；本次没有 Intel 或 Windows 新包。

安装：退出 PORDA，打开 DMG，将 PORDA.app 拖到“应用程序”并替换原版。仅保留一个 PORDA.app，保留 ~/Library/Application Support/Port Depot 数据目录。

新功能：右键文件→格式转换→选择目标格式；转换在本地生成真实文件并保留原件，重名不覆盖，可以撤销。右上四按钮左侧的独立圆形按钮用于先保存编辑、再同步画板对应的真实文件夹。

包内带有 Filee 2.2.0 CLI 与兼容的 7-Zip 26.05，不另装 Filee GUI、Python 或 .NET。格式以本地可用引擎为准，大型可选引擎没有额外打包。

本包为 ad-hoc 签名，未 Developer ID 签名或 Apple 公证。如系统阻止打开，在系统设置“隐私与安全性”中针对 PORDA 允许打开。请核对 SHA256SUMS.txt。

English: Requires Apple silicon and macOS 14+. Quit PORDA and drag PORDA.app to Applications, replacing the old app. Keep the data directory. This update includes local Filee conversion and a separate circular folder-sync button. It is ad-hoc signed, not notarized. Refer to the attached scope report; macOS 14 deployment targets were inspected but not tested on a physical macOS 14 machine.

https://github.com/Acho001/PORDA/releases/tag/v2026.11.02.1
