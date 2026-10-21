# iGoBeat Chart Studio

独立 Mac 曲谱编辑器 · 0.19.2 测试版

![应用图标](docs/editor-help-assets/icon.png)

[下载安装包](https://github.com/GloobyFF/iGoBeat-Chart-Studio/releases/tag/v0.19.2) · [图文使用指南](docs/EditerHelp.html) · [网站帮助](https://www.igobeat.com/EditerHelp.html)

## 0.19.2 更新

- 新增 Beat Saber 独立工作台：单首或批量扫描，按已认可规则制作 Quad、Hex、Piano、Fall 四种玩法，共 11 张难度谱；保存原谱与设计报告。
- Quad → Hex 使用当前原滑动优先规则，可调滑动保留方式、新增比例、长按、奖励与落点设计；支持对应难度批量转换、预览和撤销。
- 曲谱作者默认 iGoBeat，手动修改后长期记住。
- 新滑动默认 5 帧，可选 3／4／5 帧；原谱保留路径不改原间隔。
- 修复密集 Hex 排布失败，以及编辑器辅助 BPM 数据造成的打击时间偏移。
- 修复 Beat Saber 工作台成品在 iPhone／iPad 导入时的时长字段格式错误；失败详情可展开，并保存错误日志。

[工作台详细说明](docs/WORKBENCH.md)。此前生成的错误时长曲包需要重新保存或制作；已安装的手机游戏无需更新。

## 安装

支持 Apple Silicon（M1 或更新）及 macOS 14+。下载 Release 中的 `iGoBeat-Chart-Studio-0.19.2-macOS-arm64.zip`，解压后把 `Distribution/iGoBeat Chart Studio.app` 拖入应用程序，双击启动。不需要安装 Xcode 或 Python。

本版是 ad-hoc 签名、尚未 Developer ID 公证的测试版本。如被 macOS 拦截，核对来源后在“系统设置 → 隐私与安全性”选择“仍要打开”。不要关闭系统安全保护。暂不提供 Intel、Windows 或 iPhone 版安装包。

内置 Python、htdemucs 与 madmom 分析模型，可离线编辑、四分轨和检测起音/节拍。解压约 1.2 GB；分析需要额外工作空间。分析不等同于逐字歌词识别，需要人工听审。

## 使用

打开音乐或 `.igb` → 选择玩法与难度 → 编辑/分析 → ⌘S 保存。所有难度与玩法保存在同一个 `.igb`。

- 图形音符工具、长按/滑动编辑、批量调时和模式转换。
- Quad / Hex 自动制谱规则与导入谱面参考。
- Fall 转换与预览，不支持逐格编辑。
- 工具栏“帮助”打开内置离线图文说明。
- 关闭时可选“保存 / 取消 / 放弃所有修改”；放弃仅丢弃未保存草稿，保留已保存曲包。
- 工作缓存：`~/Library/Application Support/iGoBeat Chart Studio/Workspace`。

![编辑器截图](docs/editor-help-assets/overview.png)

## 授权与范围

这是用于非商业制作与测试的分发仓库，不是开源游戏源码仓库。未另行授予编辑器源码、美术或品牌的再许可权。本包不包含歌曲、个人草稿或凭据。

第三方组件保留各自许可证。madmom 模型使用 **CC BY-NC-SA 4.0**，商业用途需向权利人另行取得许可；htdemucs / Demucs 为 MIT。完整组件与许可证位于 App 的 `Contents/Resources/ThirdPartyNotices` 及内置 Python 目录。

## 维护与校验

每次版本发布使用独立 tag 与附件，不覆盖旧版文件。Release 包含 App ZIP、网站静态 ZIP 和 `SHA256SUMS.txt`；下载后可运行 `shasum -a 256 -c SHA256SUMS.txt` 校验两个 ZIP。

网站上传包 `EditerHelp-website.zip`：将 `EditerHelp.html` 与 `editor-help-assets` 一起上传网站根目录。正式网站由维护者另行上传，GitHub 发布不等于网站已更新。

本次验证：32 项制谱与导入回归、工作台导出格式回归通过；真实歌曲 11 张谱面通过游戏原生解析、内嵌运行时一致性和完整游戏导入检查。分发 ZIP 完整性、版本与签名检查通过。未逐首真机听审，也未做 Apple 公证。
