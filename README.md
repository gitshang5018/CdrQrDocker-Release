# CorelDraw AI工具箱 (CdrQrDocker) - 发布与分发中心

本项目是 **CdrQrDocker (CorelDraw 智能辅助插件与 AI 工具箱)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐新用户）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.5.1)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免重启热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.70 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.5.1 更新亮点

1. **通用抠图预处理张量归一化规范化**：
   - 彻底修正 RMBG-1.4 预处理规范，由旧版 ImageNet 均值方差公式更正为标准中心对称归一化 `(x / 255.0 - 0.5)`，彻底消除通用物体抠图时的特征失真与主体误扣。
2. **Alpha 通道 Min-Max 动态拉伸与底噪消除**：
   - 原生 C++ 核心与 C# 托管回退层完全同构实现动态极值扫描与拉伸；
   - 对小于 2% 强度的微弱背景噪声实施强制归零截断，彻底根治抠图边缘白雾、背景残留与杂斑。
3. **连通域多目标自动拆分抗噪与面积过滤优化**：
   - 将多目标拆分判定二值化阈值提升至 20，避免边缘渐变羽化区域断裂；
   - 引入 0.1% 画布面积过滤保底机制（保底 50 像素），根治背景残存微小噪点引发的碎片式过度拆分。
4. **高保真双三次插值重构**：
   - 保证在规范化空间后执行 Catmull-Rom 插值采样，大幅提升超清图像与复杂边缘抠图的平滑度。

---

## 📄 当前版本配置

本仓库根目录的 `version.json` 由客户端自动拉取以检测新版本。
