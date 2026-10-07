# PrePress Master 印前大师 (CdrQrDocker) - 发布与分发中心

本项目是 **PrePress Master 印前大师 (CorelDraw 工业级印前自动化扩展系统)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐新用户）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.6.5)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免重启热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.56 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[通过 nuima.cc.cd 加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.6.5 更新亮点

1. **“印前大师”品牌形象全面规范化**：
   - 用户界面、更新弹窗标题与提示文案全面规范统一为“印前大师”；
   - 包含《用户手册》与《说明文档》无遗漏对齐。
2. **智能默认路径平滑兼容**：
   - 默认存储路径全新升级为“文档\印前大师”，并具备历史目录“文档\CdrQrDocker”后向探测与无损过渡机制。
3. **彻底剥离 OpenCV，原生 NativeImageEngine 重构**：
   - 移除非托管 OpenCV 依赖，安装包轻量化至 19.8MB，文档漂白、透视变换与二值化全面采用 C++ 原生引擎加速。
4. **防退化自动化测试守护**：
   - 集成品牌文案与关键路径规范化自动化断言测试套件，确保系统长期稳定运行。
   - 全面升级产品品牌为 PrePress Master（印前大师），引入全新的 `PrePressCore.dll` 与 `PrePressBridge` 双轨 P/Invoke 架构；
   - 建立全生命周期 C/C++ 内存护盾与防御机制，原生模块与托管层零句柄挂留、零内存漂移。
2. **几何与排料高能原生化引擎 (NativeGeometryEngine & NativeNestingEngine)**：
   - 采用纯 C++ 高性能算法解算多边形骨架外扩、轮廓偏移与刀路排序优化；
   - 启发式自适应异形排料防碰撞检测，大幅缩短复杂图元的解算耗时。
3. **图像与 AI 抠图全闭环原生引擎 (NativeAiEngine & NativeWicCodec)**：
   - 基于 DirectML GPU 与多线程 CPU 动态降级的通用 ONNX Runtime C-API 治理引擎；
   - WIC 零磁盘 I/O 高性能图像解码与编码、动态极值扫描与背景噪声截断、精细边缘平滑修整。
4. **条码/二维码矢量原生化与 VDP 生产排版加速 (NativeBarcodeEngine & NativeVdpLayoutEngine)**：
   - 遵循 ISO/IEC 18004 与 ISO/IEC 15417 规范的纯原生 QR Code 与 Code128 编码器；
   - 工业级 RLE 水平相连暗模块合并算法，图元数量直降 80% 以上；
   - 10,000 张可变数据卡片阵列与高精裁切角线 24ms 极速解算，全面替代低效磁盘临时文件。

---

## 📄 当前版本配置

本仓库根目录的 `version.json` 由客户端自动拉取以检测新版本。
