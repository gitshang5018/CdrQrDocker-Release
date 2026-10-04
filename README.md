# CorelDraw AI工具箱 (CdrQrDocker) - 发布与分发中心

本项目是 **CdrQrDocker (CorelDraw 智能辅助插件与 AI 工具箱)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐新用户）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.5.2)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免重启热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.60 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.5.2 更新亮点

1. **通用抠图彻底还原为纯净托管流程**：
   - 完全直通原图 RGB 色彩与原始 Alpha，彻底移除任何去饱和、边缘灰度混合及 Alpha 非线性收缩，100% 完整保留印章黄色底色与鲜艳度；
   - 彻底解决黄色圆形底色被误洗白、变成极浅微白半透明圈的缺陷。
2. **恢复经典 BFS 连通域自动拆分**：
   - 基于二值连通域直接提取独立对象外接矩形框，准确将不相连的印章独立拆分成 CorelDRAW 图元对象。
3. **通用抠图完全解耦原生 C++ 依赖**：
   - 通用抠图直通托管 ImageSharp 高保真 Bicubic 插值与 OnnxRuntime 推理，免疫 Windows DLL 进程常驻锁定。

---

## 📄 当前版本配置

本仓库根目录的 `version.json` 由客户端自动拉取以检测新版本。
