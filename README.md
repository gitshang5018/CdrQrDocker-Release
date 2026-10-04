# CorelDraw AI工具箱 (CdrQrDocker) - 发布与分发中心

本项目是 **CdrQrDocker (CorelDraw 智能辅助插件与 AI 工具箱)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐新用户）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.5.0)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免重启热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.70 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.5.0 更新亮点

1. **实用工具面板精简**：
   - 移除实用工具面板中与悬浮工具条重复的「选择工具」与「对齐分布」区块，界面更紧凑清爽，突出核心排版与图像处理工具。
2. **修复图片导出指定路径失效**：
   - 彻底阻断 Release 代码混淆重命名穿透缺陷，保证指定导出路径与文件名精准生效；
   - 开放导出目标路径文本框直接输入/粘贴，优化选择文件夹弹窗置顶（绑定 CorelDRAW 主窗口 HWND 防遮挡），一键【提取】时同步提取 CDR 文件同级目录。
3. **修复抠图背景替换与证件照尺寸失效**：
   - 全面重构抠图参数为显式参数字典，彻底杜绝背景色与证件照尺寸参数丢失；
   - 补齐 6 种背景颜色单选框实时预览文案联动（透明、白色、蓝色、红色、浅蓝、浅灰）。
4. **全局代码混淆安全防御**：
   - 关闭属性重命名，从根源消除所有面板在 Release 混淆下匿名对象与 DTO 序列化丢失的系统性隐患。
5. **悬浮工具条贴身锚定与位置优化**：
   - 默认停靠在选中对象下方并左对齐，垂直间距 20 像素；CorelDRAW 最小化时自动隐藏，杜绝桌面残留。
6. **C++ 原生高性能引擎重构与全局事务治理**：
   - PLT 刻绘重排加速比达 1885 倍；
   - 异形排料 2.0 支持大件孔洞智能套排小件；
   - 矢量巡边引擎灰度 Alpha/RGBA 自适应极速生成 CutContour 割线；
   - 极简 RAII CdrBatchScope 全局防冻结与重绘闪烁。

---

## 📄 当前版本配置

本仓库根目录的 `version.json` 由客户端自动拉取以检测新版本。
