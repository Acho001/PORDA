# PORDA · 泊达 2026.11.04.1 安装与验证

只发布Mac arm64 DMG，应用1.1.9，最低macOS14。Windows按用户要求暂停，仍使用2026.10.13.1。

## 安装

退出PORDA，打开DMG，将PORDA.app拖入“应用程序”替换旧版。只保留一个安装入口，保留 `~/Library/Application Support/Port Depot`。本轮临时验证应用已注销删除，本机原有安装未替换。

自带Filee CLI 2.2.0与官方兼容7-Zip26.05，不要求另装Filee GUI、Python或.NET。只显示实际本地可转换格式；转换生成真实文件并保留原件，支持撤销。

## 验证范围

本次通过 **51 项文件回归、141 项连接算法用例、画板状态测试、30 项包内检查、12 项既有交互回归**，以及注释/菜单、转换和性能交叉测试。实际包内引擎完成 PNG→JPG/PDF、Markdown→HTML、ZIP→7Z；原件保留及撤销通过。

另以独立临时应用和合成资料完成 **14 项 Mac 原生 WKWebView 检查**：画板进入、注释与菜单互斥、中文输入保存、连线修改、环形菜单点击与键盘分页、真实 JPG 文件及撤销、正常启动关闭。临时应用已注销清理；本轮没有替换本机原有安装。

千节点合成画板的 Chrome 对照测试显示平移/缩放/拖动长帧明显减少；五千节点仍有初始加载、缩放和拖动瓶颈。性能测试不是原生帧率承诺。未在物理 macOS 14 测试，未穷举格式，未重测原生截图与 Finder 拖拽手势。Windows 本次暂停构建与验收。详见 [安装与验证](PORDA-Installation-and-Validation.md) 和 [性能与审查说明](PORDA-Performance-and-Review.md)。

包内版本、身份、签名完整性、最低部署目标、13个入门素材、静态资源一致性和安装目录只读已检查；24个转换引擎原生组件均为arm64且部署目标不高于macOS14。没有修改二进制最低系统标记来伪造兼容性。

## 限制

ad-hoc签名，没有Developer ID或Apple公证；未在物理macOS14测试。原生检查为针对性验证，不代表所有手势、系统功能或转换格式已穷举。性能数字来自模拟API的Chrome基准，五千节点仍有明确瓶颈。用户资料、凭据、内部构建输入与私有应用源码不在公开发行材料中。第三方组件保留各自许可证。

English: Mac arm64 only, app1.1.9 / macOS14+. Passed 51 filesystem tests, 141 connector cases, state tests, 30 packaged checks, 12 existing interactions and 14 targeted native WKWebView checks. Temporary validation apps were removed. Existing production installation was not replaced. No physical macOS14, exhaustive-format, native-screenshot or Finder-gesture rerun. Synthetic Chrome performance data has documented scale limits. Ad-hoc signed, not notarized. Windows unchanged.
