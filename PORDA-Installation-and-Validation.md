# PORDA · 泊达 2026.11.02.1 安装与验证

本次只发布 Apple Silicon / macOS 14+ 的 Mac DMG，应用版本 1.1.7，内含 Filee CLI 2.2.0 与官方 7-Zip 26.05。Windows 版本保持 2026.10.13.1，本次没有新建、替换或重新验收 Windows 安装包。

## 安装与数据

退出 PORDA，打开 DMG，将 PORDA.app 拖入“应用程序”并替换原版。仅保留一个应用入口。用户数据仍在 `~/Library/Application Support/Port Depot`，不要删除该目录来更新软件。内置仅有入门示例，不含个人项目或凭据。

此包自带 Filee CLI 和运行时，不要求另装 Filee GUI、Python 或 .NET。文件转换完全本地执行，保留原件、避免覆盖、支持撤销。可选的大型引擎不在包内，可用格式以实际检测为准。

## 本次通过的检查

- 49 项源码文件回归和 Canvas 状态测试。
- 28 项实际 Mac 安装包检查，覆盖版本、应用身份、签名完整性、最低系统声明、入门文件、资源一致性和运行时不写安装目录。
- 包内 24 个转换引擎原生组件均为 arm64，部署目标不高于 macOS 14。原引擎附带的 macOS 26 解压程序已替换为官方兼容版本，没有修改二进制的最低系统标记来伪造兼容性。
- 在独立数据目录与受限 PATH 下运行实际冻结后端及包内 Filee；真实完成 PNG→JPG/PDF、Markdown→HTML、ZIP→7Z，并验证输出存在、原件保留及撤销。
- 12 项原有包内交互回归，覆盖 T 工具、连线编辑、较新文字替换旧文件复制与采集港真实移动。
- 新界面流程：格式弹窗、搜索、转换撤销、外部新增/改名/修改/删除手动同步、刷新前保留未保存批注；检查浅色/深色与 1440/900/600/390 像素布局。
- 使用独立临时应用身份验证正常 Launch Services 启动。临时应用已注销并清理，未替换用户已安装应用。

## 范围限制

以上后端/浏览器检查针对实际安装包资源。当前机器不是 macOS 14，最低系统仅核查声明和原生部署目标；没有在 macOS 14 实机执行。没有穷举 Filee 全部格式；没有重测本次包原生窗口中的 Finder 拖拽手势、截图、系统剪贴板与原生窗口自动视觉操作。旧版的原生验证结果不能视为本版结果。Windows 本次未构建和验收。

应用为本地 ad-hoc 签名，没有 Developer ID 签名或 Apple 公证。按 macOS 系统提示允许打开，核对发行来源和 SHA256SUMS.txt。

私有源码、内部构建记录、开发路径及个人资料不在此公开发行包中。第三方代码保留各自许可证；随附 LICENSE 仅覆盖项目自有部分。

## English

This release contains only the macOS arm64 DMG, app 1.1.7. It includes Filee 2.2.0 and official 7-Zip 26.05; Windows remains unchanged. Validation covers 49 source filesystem regressions, 28 packaged checks, 12 existing browser interaction regressions, new conversion/sync UI flows, actual bundled-engine conversion, read-only installation resources, deployment metadata and normal Launch Services startup. Temporary validation apps were removed. Not tested on a physical macOS 14 machine; not all formats, native Finder gestures, screenshots, native clipboard acceptance or native packaged-window visual automation were exercised. Ad-hoc signed and not notarized. Keep the existing user-data directory when replacing the application.
