# PrePress Master 印前大师 (CdrQrDocker) - 发布与分发中心

本项目是 **PrePress Master 印前大师 (CorelDraw 工业级印前自动化扩展系统)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐，原生组件一并更新）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.7.10)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免安装热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.83 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.7.10 更新亮点

1. **彻底攻克矢量巡边直角/锐角倒角削平与转角精度不足痛点**：
   - 重构原生切向量角点检测算法（`DetectMacroCorners`）：改用物理空间累积弧长微分（5.0px 窗口）计算切向夹角，彻底解耦离散顶点疏密不均问题；引入欧氏空间聚类抑制，根除平局丢弃与对称长边角点漏检缺陷；
   - 引入自适应几何交点锐化微调（`Corner Apex Miter Sharpening`）：根据转折角自适应距离限制，精确计算前后射线几何交点，将 Marching Squares 离散网格 45° 阶梯截角精确定位并顶回真实物理顶点，割线顶点严格到达真实物理尖角顶点，彻底消除招牌红色外角外露与倒角削平；
2. **直线段快速通道锁定 100% 笔直边缘**：
   - 在拟合管道中新增直线特征快速通道，平直轮廓（如招牌边框、立柱）直接退化拟合为标准一次退化三次贝塞尔直线段，100% 笔直且杜绝波浪抖动；
3. **保持单对象一体化融合、Stone-DeRose 弦投影单调与全域 0 死结（0 Knots）保障**。

---

## ⚡ v2.0.7.9 历史亮点

1. **巡边单对象一体化融合与多图层膨胀根除**：
   - 描边（CutContour 割线）、置入容器（PowerClip 裁切）与白色底衬（WhiteBacking 填充）全部融合于单一轮廓割线对象中执行，不再产生多余图层与层级分组；
2. **巡边设置窗口紧凑化排版**：
   - 重构 `ContourSettingsWindow`，禁用垂直滚动条，紧凑化卡片与控件垂直排版，完美适配各类屏幕分辨率。

---

## ⚡ v2.0.7.8 历史亮点

1. **彻底根除巡边生成瞬间其他后台程序界面一闪而过的闪烁现象**：
   - 定位并修复 Windows DWM 焦点回弹反模式：重构 `ContourSettingsWindow`，移除全局 `Topmost="True"` 置顶设置；
   - 原生挂接 CorelDRAW 主窗口 HWND 为 Owner 宿主，点击「确定生成」及弹窗销毁时，将焦点平滑、无感归还给 CorelDRAW 主窗口；
   - 升级进度提示窗（`ProgressWindow`）：引入 `ShowActivated="False"`，杜绝毫秒级进度窗显示与关闭时争夺桌面焦点，从根源上消除后台应用跳窗。
2. **保持高精矢量巡边 0 死结与全句柄会话解锁全链路稳定运行**。

---

## ⚡ v2.0.7.7 历史亮点

1. **彻底修复免抠图矢量巡边「原生轮廓提取引擎不可用或提取失败」阻断**：
   - 深入攻克 CorelDraw 运行环境下出厂目录旧模块与热更目录新模块共存时的动态库数据段隔离陷阱；
   - 引入全句柄动态导出符号广播解锁机制（`NativeLicenseBridge.GetAllNativeHandles`），对宿主进程内所有 `CdrQrCoreNative.dll` 模块进行统一 Session 解锁；
   - 彻底解决静态 P/Invoke 锁定宿主旧模块导致底层算力栅栏拦截返回 0 的核心缺陷。
2. **强化巡边前置会话主动校验与精准诊断反馈**：
   - 巡边前自动调用 `EnsureNativeSessionUnlocked()` 唤醒底层会话状态；
   - 彻底优化报错诊断：清晰区分授权会话状态未激活与图片色彩容差参数调整建议，拒绝模糊报错。
3. **出厂 Payload 与单文件安装包全量同步**：
   - 全量同步最新核心动态库至出厂目录与安装包 Payload，多版本 CorelDraw 即装即用。

---
