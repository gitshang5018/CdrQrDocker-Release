# PrePress Master 印前大师 (CdrQrDocker) - 发布与分发中心

本项目是 **PrePress Master 印前大师 (CorelDraw 工业级印前自动化扩展系统)** 的官方公开分发与在线更新中心。

---

## 🚀 快速下载与安装

### 1. 全量安装程序（推荐，原生组件一并更新）
- **官方直接下载**：[CorelDraw插件安装程序.exe (v2.0.7.13)](CorelDraw插件安装程序.exe)
- **国内加速下载**：[加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CorelDraw插件安装程序.exe)
- **安装方法**：双击运行安装程序，一键检测并安装到电脑上的 CorelDraw（支持 X7 到 2026/2027 各版本）。

### 2. 免安装热更补丁（老用户静默或手动升级）
- **补丁直接下载**：[CdrQrDocker.Core.zip (2.83 MB)](CdrQrDocker.Core.zip)
- **国内加速下载**：[加速下载](https://nuima.cc.cd/https://raw.githubusercontent.com/gitshang5018/CdrQrDocker-Release/main/CdrQrDocker.Core.zip)

---

## ⚡ v2.0.7.13 更新亮点

1. **字体管理全量 8400+ 字体毫秒级秒开渲染优化（彻底根除卡顿与迟滞）**：
   - 彻底移除外部文件夹 URI 磁盘检索瓶颈，改用纯净的 Windows DirectWrite 内存共享字体族名构造，杜绝渲染线程对本地字体文件夹的海量磁盘 IO 扫描，列表滚动与渲染瞬间丝滑如飞；
   - 引入 `RangeObservableCollection` 高性能批量装载机制，单次 `Reset` 通知注入 8400+ 款字体，彻底根除 UI 主线程数千次频繁事件通知调度与 Grouping 视图重建假死；
   - 在 ListBox 的 GroupStyle 中显式启用 `VirtualizingStackPanel` 分组虚拟化模板并开启 Pixel 像素级滚动，实现海量字体按需即时渲染，保障全量 8400+ 款字体一款不少、以自身字形样式瞬间秒开呈现。

---

## ⚡ v2.0.7.12 历史亮点

1. **矢量巡边自然圆弧与自由插画圆润度全面恢复（杜绝折角与生硬割角）**：
   - 彻底重构底层角点检测算法，将局部步长锁定为微观稳定尺度（6.0px），彻底消除大外扩偏移下跨越小圆球灯（15px）与弯曲藤蔓波浪时误判的大量虚假转折角点；
   - 引入严格的正交多边形拓扑判据：直角尖角 Miter 求交外延仅对 4 边的纯正交矩形生效；对于用户插画、小圆球、波浪藤蔓等自由曲线，绝对不触发几何直线重构，100% 享受高精拉普拉斯平滑与贝塞尔平滑拟合，彻底恢复极致圆滑圆润的贝塞尔平顺轮廓。
2. **CorelDRAW 曲线平滑原生保障**：
   - 在 CorelHelper 中对平滑贝塞尔段统一采用 `AppendCurveSegment2` 原生平滑节点绘制，杜绝段间强制插入 Cusp 尖锐折角，确保节点切线连续顺滑。
3. **巡边设置面板滚动条彻底消除**：
   - 紧凑化重构 `ContourSettingsWindow` 界面卡片边距与垂直排版，将 `VerticalScrollBarVisibility` 彻底设为 `Disabled`，在各种高分屏与 DPI 缩放比例下坚决不出现任何滚动条。

---

## ⚡ v2.0.7.11 历史亮点

1. **字体管理秒开加载加速（彻底解决打开面板卡顿问题）**：
   - 彻底移除后台线程对 8400+ 款字体逐个执行 `TryGetGlyphTypeface` 串行磁盘/内存字形解析的性能瓶颈，消除长达数十秒的阻塞与无响应；
   - 充分利用 WPF 虚拟化列表（VirtualizingStackPanel）按需 GPU 硬件加速即时渲染可见项，打开字体面板加载时间从数十秒骤降至毫秒级，实现瞬间秒开。
2. **字体显示名称规范化与去重清洗（还原纯正规范的字体家族名称）**：
   - 全面重构 `CleanFamilyDisplayName`，精准剥离 `(TrueType)` 等技术后缀并清洗 `Bold`、`Regular`、`ExtraBold`、`Heavy`、`中黑体` 等字重修饰词；
   - 还原纯正简洁的字体显示名称（如“微软雅黑”、“思源黑体 CN”、“方正超值体”），确保 CorelDRAW 原生字体属性赋值与匹配 100% 准确。
3. **复合 FontFamily 双路自适应渲染（100% 呈现各字体自身的艺术字形效果）**：
   - 引入复合字体家族声明（优先解析 `%LocalAppData%\Microsoft\Windows\Fonts` 用户目录，兜底系统 `C:\Windows\Fonts` 目录）；
   - 列表项 100% 按照字体自身字形样式呈现（书法、艺术、毛笔、黑体、宋体等真实视觉效果），彻底根除用户字体全部退化显示为普通西文字体的问题。

---

## ⚡ v2.0.7.10 历史亮点

1. **字体管理全量枚举引擎恢复（彻底解决字体获取不全与用户字体丢失）**：
   - 重构 `FontManager.cs` 底层枚举体系，废弃存在 Windows 10/11 用户目录盲区的 GDI+ 简单集合；
   - 引入 Win32 GDI 底层 `EnumFontFamiliesEx` P/Invoke 物理图形枚举与 Windows 注册表（HKCU/HKLM 双路）全量融合，彻底打通普通用户权限安装字体（`%LocalAppData%\Microsoft\Windows\Fonts`）及各类第三方商业字库；
   - 过滤 `@` 竖排兼容字体并剔除 `(TrueType)` 等技术后缀，单机字体识别量从 384 款暴增至 8400+ 款，完美还原 16 个厂商分组。
2. **矢量巡边外扩直角高精保真重构（解决外扩圆角钝化与割角碎线）**：
   - 攻克 EDT 欧氏距离场外扩带来的圆角弧钝化问题，基于多边形相邻主边中点切线求交（Polygon Miter Reconstruction）与 CAD 正交吸附，直接还原几何真实尖锐直角；
   - 实心矩形外扩由 11 段碎线精简至严格 4 段标准直线，外角顶点物理误差从 1.131mm 极限收敛至 0.254mm（<= 1px）；
   - CorelDRAW 原生图元直绘全面对接：对平直线段调用 `sp.AppendLineSegment(epX, epY)`，生成纯正 CorelDRAW 直线段与 Cusp 尖角节点。
3. **保持全域 0 死结（0 Knots）、Stone-DeRose 弦投影单调性与全图层一体化融合**。

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
