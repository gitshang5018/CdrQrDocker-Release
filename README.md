# CorelDraw AI工具箱 (CdrQrDocker) - 发布与分发中心

本项目是 **CdrQrDocker (CorelDraw 智能辅助插件与 AI 工具箱)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐新用户）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.3.0)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免重启热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.55 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.3.0 更新亮点

1. **全面代码混淆与 C++ 核心混合安全防护**：
   - 引入 C++ 原生机器码动态库 `CdrQrCoreNative.dll`（/MT 静态编译，零外部运行时依赖）；
   - 集成 Obfuscar 全量字符串加密与控制流平坦化混淆，彻底防御反编译与抄袭；
2. **极速矢量巡边（免 AI 抠图）**：
   - 彻底解除巡边功能对 AI 大模型（`modnet.onnx`）的依赖与下载卡顿；
   - 支持透明通道极速巡边 + 普通白底/实色背景四角方差自适应采样，50~100 毫秒瞬间生成高精度矢量切割线；
3. **性能大幅提升**：
   - 异形排版算法实现一维内存复用与 C++ 原生位碰撞加速，计算速度提升 2.76 倍；
4. **双通道免重启热更**：
   - 客户端默认通过 `nuima.cc.cd` 加速镜像实现秒级检测与无缝更新。

---

## 📄 当前版本配置

本仓库根目录的 `version.json` 由客户端自动拉取以检测新版本。
