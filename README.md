# 🎯 智能运动检测系统 Pro

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![Mobile Only](https://img.shields.io/badge/Platform-Mobile%20Only-green.svg)](https://github.com/yiranrumengqaq/Buyaa)

一个功能强大的实时运动检测系统，专为移动设备设计，采用先进的视频分析技术，提供精准的运动监控、智能反馈和完善的数据记录功能。

[在线演示](https://yiranrumengqaq.github.io/Buyaa/) | [报告问题](https://github.com/yiranrumengqaq/Buyaa/issues) | [功能建议](https://github.com/yiranrumengqaq/Buyaa/issues/new)

---

## ⚡ 核心特性

### 📹 智能视频检测

- **实时运动分析** - 基于像素差异的高精度运动检测
- **可调节检测区域** - 自定义检测范围（30%-100%）
- **多级灵敏度** - 10 级灵敏度调节，适应不同场景
- **双摄像头支持** - 前后摄像头快速切换
- **高帧率处理** - 支持 5-30 FPS 可调检测频率

### 🎮 多种预设模式

- **⚖️ 平衡模式** - 日常使用的最佳配置
- **🔍 高灵敏度** - 捕捉细微运动变化
- **🔋 省电模式** - 延长续航时间
- **🔒 安防模式** - 最高灵敏度的安全监控
- **🔇 静音模式** - 禁用所有反馈提示
- **⚙️ 自定义** - 完全自定义所有参数

### 🔔 智能反馈系统

- **震动反馈** - 可调节的触觉反馈
- **音频提示** - 蜂鸣声警报（可调音量）
- **推送通知** - 运动检测时的系统通知
- **实时强度显示** - 可视化运动强度指示器

### 📊 数据统计与日志

- **实时日志系统** - 详细记录所有事件
- **分类过滤** - 信息/成功/警告/错误分类
- **CSV 导出** - 一键导出日志数据
- **运行统计** - 检测次数、震动次数、通知次数
- **运行时长** - 精确的累计运行时间

### 🔋 电源管理

- **电池监控** - 实时显示电量和充电状态
- **充电速度预测** - 智能计算充满时间
- **自动变暗** - 省电模式下自动降低亮度
- **Wake Lock** - 保持屏幕常亮防止休眠

### 🎨 现代化界面

- **标签页导航** - 监控/设置/日志/统计四大模块
- **响应式设计** - 完美适配各种移动设备
- **玻璃态效果** - 现代化的毛玻璃设计风格
- **平滑动画** - 流畅的交互体验
- **仅限移动端** - PC 端显示 404 页面

---

## 🚀 快速开始

### 在线使用

访问 [https://yiranrumengqaq.github.io/Buyaa/](https://yiranrumengqaq.github.io/Buyaa/)

**⚠️ 注意：必须使用移动设备访问，PC 端会显示 404 页面**

### 本地部署

1. **克隆仓库**
   ```bash
   git clone https://github.com/yiranrumengqaq/Buyaa.git
   cd Buyaa
   ```

2. **启动本地服务器**
   ```bash
   # 使用 Python
   python -m http.server 8000
   
   # 或使用 Node.js
   npx http-server
   ```

3. **移动端访问**
   
   在移动设备上访问：`http://你的电脑IP:8000`

---

## 📖 使用指南

### 基础操作

#### 1. 启动检测

1. 点击"开始检测"按钮
2. 授予摄像头权限
3. 系统开始实时监控运动

#### 2. 选择预设模式

- 点击任一预设按钮快速应用配置
- **平衡模式**：推荐日常使用
- **高灵敏度**：需要捕捉细微动作时
- **省电模式**：电量不足时使用
- **安防模式**：作为监控摄像头使用

#### 3. 自定义参数

切换到"设置"标签页：

- **检测区域大小**：调整监控范围
- **检测灵敏度**：控制触发阈值
- **震动阈值**：设置触发震动的强度
- **通知阈值**：设置发送通知的强度

### 高级功能

#### 日志系统

1. **查看日志**
   - 切换到"日志"标签页
   - 按级别筛选（全部/信息/成功/警告/错误）

2. **导出日志**
   - 点击"导出CSV"按钮
   - 日志将保存为时间戳命名的 CSV 文件

3. **清空日志**
   - 点击"清空"按钮
   - 确认后删除所有日志记录

#### 电源管理

- **自动变暗**：无操作一定时间后降低屏幕亮度
- **变暗超时**：设置进入省电模式的等待时间
- **亮度降低程度**：控制变暗后的亮度水平

#### 反馈设置

- **震动间隔**：两次震动之间的最小间隔
- **通知间隔**：两次通知之间的最小间隔
- **持续监控模式**：持续触发反馈 vs 单次触发

---

## 🛠️ 技术实现

### 核心算法

#### 运动检测算法

```javascript
function compareFrames(current, previous) {
    const data1 = current.data;
    const data2 = previous.data;
    let diffPixels = 0;
    const step = config.sampleStep * 4;
    
    // 采样比较像素差异
    for (let i = 0; i < data1.length; i += step) {
        const diff = Math.abs(data1[i] - data2[i]) +
                    Math.abs(data1[i+1] - data2[i+1]) +
                    Math.abs(data1[i+2] - data2[i+2]);
        
        if (diff > config.pixelThreshold) {
            diffPixels++;
        }
    }
    
    // 计算运动强度百分比
    const totalPixels = data1.length / (step * 3);
    return (diffPixels / totalPixels) * 100;
}
```

### 技术栈

- **前端框架**：原生 HTML5 + CSS3 + JavaScript ES6+
- **视频处理**：Canvas API + MediaStream API
- **硬件接口**：
  - Vibration API（震动反馈）
  - Notification API（推送通知）
  - Battery Status API（电量监控）
  - Screen Wake Lock API（保持唤醒）
- **数据存储**：LocalStorage（设置持久化）
- **响应式检测**：User-Agent 检测 + Media Queries

### 核心 API 使用

#### 1. 摄像头访问

```javascript
const constraints = {
    video: {
        facingMode: currentCamera,
        width: { ideal: 1280 },
        height: { ideal: 720 }
    }
};

const stream = await navigator.mediaDevices.getUserMedia(constraints);
```

#### 2. Wake Lock

```javascript
if ('wakeLock' in navigator) {
    wakeLock = await navigator.wakeLock.request('screen');
}
```

#### 3. 电池监控

```javascript
const battery = await navigator.getBattery();
battery.addEventListener('levelchange', updateBatteryInfo);
```

---

## 📊 参数说明

### 检测参数

| 参数 | 范围 | 默认值 | 说明 |
|------|------|--------|------|
| 检测区域大小 | 30-100% | 60% | 监控画面的百分比 |
| 检测灵敏度 | 10-90 | 50 | 触发检测的阈值 |
| 像素变化阈值 | 10-100 | 40 | 单个像素的差异阈值 |
| 检测频率 | 5-30 fps | 15 fps | 每秒分析的帧数 |
| 最小持续时间 | 100-2000 ms | 500 ms | 有效运动的最短时长 |
| 采样步进 | 2-10 px | 4 px | 像素采样间隔 |

### 反馈参数

| 参数 | 范围 | 默认值 | 说明 |
|------|------|--------|------|
| 震动阈值 | 10-100% | 50% | 触发震动的强度 |
| 通知阈值 | 10-100% | 60% | 触发通知的强度 |
| 震动间隔 | 0.5-5 秒 | 2 秒 | 震动反馈间隔 |
| 通知间隔 | 3-30 秒 | 10 秒 | 通知间隔 |
| 音量 | 0-100% | 50% | 提示音音量 |

### 电源参数

| 参数 | 范围 | 默认值 | 说明 |
|------|------|--------|------|
| 变暗超时 | 10-120 秒 | 30 秒 | 无操作后变暗时间 |
| 亮度降低 | 30-90% | 70% | 变暗后的亮度水平 |

---

## 🎯 预设模式详解

### 平衡模式（推荐）

```javascript
{
    sensitivity: 50,
    pixelThreshold: 40,
    frameRate: 15,
    minDuration: 500,
    sampleStep: 4,
    vibrateThreshold: 50,
    notificationThreshold: 60
}
```

**适用场景**：日常监控、一般用途

### 高灵敏度模式

```javascript
{
    sensitivity: 80,
    pixelThreshold: 20,
    frameRate: 25,
    minDuration: 200,
    sampleStep: 2,
    vibrateThreshold: 30,
    notificationThreshold: 40
}
```

**适用场景**：需要捕捉细微动作、精确监控

### 省电模式

```javascript
{
    sensitivity: 30,
    pixelThreshold: 60,
    frameRate: 8,
    minDuration: 1000,
    sampleStep: 8,
    vibrateThreshold: 70,
    notificationThreshold: 80
}
```

**适用场景**：电量不足、长时间监控

### 安防模式

```javascript
{
    sensitivity: 90,
    pixelThreshold: 15,
    frameRate: 30,
    minDuration: 100,
    sampleStep: 2,
    vibrateThreshold: 20,
    notificationThreshold: 25
}
```

**适用场景**：安全监控、入侵检测

---

## 🔧 开发说明

### 项目结构

```
Buyaa/
│
├── index.html          # 单文件应用（包含所有代码）
├── README.md           # 项目文档
├── LICENSE             # MIT 开源协议
└── screenshots/        # 截图目录（可选）
```

### 核心模块

1. **检测引擎** - `detectMotion()`
   - 视频帧捕获
   - 像素差异计算
   - 运动强度分析

2. **反馈系统** - `handleMotionDetected()`
   - 震动控制
   - 音频提示
   - 推送通知

3. **日志系统** - `addLog()`
   - 事件记录
   - 分类过滤
   - CSV 导出

4. **电源管理** - Power Management
   - 电池监控
   - Wake Lock
   - 自动变暗

5. **数据持久化** - `saveSettings()` / `loadSettings()`
   - LocalStorage 存储
   - 配置自动恢复

### 自定义开发

#### 添加新的预设模式

```javascript
const presets = {
    // ... 现有预设
    myCustom: {
        sensitivity: 60,
        pixelThreshold: 35,
        frameRate: 20,
        minDuration: 300,
        sampleStep: 3,
        vibrateThreshold: 45,
        notificationThreshold: 55
    }
};
```

#### 修改检测算法

在 `compareFrames()` 函数中调整算法：

```javascript
// 示例：使用加权差异
const diff = Math.abs(data1[i] - data2[i]) * 0.3 +
            Math.abs(data1[i+1] - data2[i+1]) * 0.59 +
            Math.abs(data1[i+2] - data2[i+2]) * 0.11;
```

---

## 📱 设备兼容性

### 支持的浏览器

| 浏览器 | 版本 | 状态 |
|--------|------|------|
| Chrome (Android) | 90+ | ✅ 完全支持 |
| Safari (iOS) | 14+ | ✅ 完全支持 |
| Firefox (Android) | 88+ | ✅ 完全支持 |
| Samsung Internet | 14+ | ✅ 完全支持 |
| Edge (Mobile) | 90+ | ✅ 完全支持 |

### 必需的 API 支持

- ✅ **必需**：MediaStream API（摄像头访问）
- ✅ **必需**：Canvas API（视频处理）
- ⚠️ **可选**：Vibration API（震动反馈）
- ⚠️ **可选**：Notification API（推送通知）
- ⚠️ **可选**：Battery Status API（电量监控）
- ⚠️ **可选**：Screen Wake Lock API（保持唤醒）

### 设备要求

- **处理器**：中等性能以上
- **内存**：2GB+ 推荐
- **摄像头**：前置/后置摄像头
- **系统**：Android 8.0+ / iOS 13.0+

---

## 🤝 贡献指南

欢迎贡献代码、报告问题或提出建议！

### 贡献流程

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启 Pull Request

### 开发规范

- 保持代码风格一致
- 添加必要的中文注释
- 测试移动端兼容性
- 更新相关文档
- 确保 PC 端仍显示 404

---

## 📋 待办事项

### 功能增强
- [ ] 支持录制检测到运动的视频片段
- [ ] 添加人脸/人形检测（使用 TensorFlow.js）
- [ ] 支持多区域独立检测
- [ ] 云端数据同步（可选）
- [ ] 定时监控功能
- [ ] 地理位置记录

### 界面优化
- [ ] 暗黑模式
- [ ] 更多主题选择
- [ ] 手势操作增强
- [ ] 横屏支持优化
- [ ] 平板适配

### 技术优化
- [ ] PWA 支持（离线使用）
- [ ] WebAssembly 加速
- [ ] WebGL 图像处理
- [ ] 多线程处理（Web Worker）
- [ ] 性能优化（减少内存占用）

---

## ⚠️ 注意事项

### 使用限制

1. **仅限移动端**
   - PC 端访问会显示 404 页面
   - 请使用手机或平板设备

2. **摄像头权限**
   - 首次使用需授予摄像头权限
   - HTTPS 环境下才能访问摄像头

3. **电量消耗**
   - 长时间运行会消耗电量
   - 建议使用省电模式或连接充电器

4. **通知权限**
   - 需要授予通知权限才能接收推送
   - 部分浏览器可能不支持

### 隐私说明

- ✅ **完全本地处理**：所有视频处理在设备上完成
- ✅ **零数据上传**：不会上传任何图像或视频
- ✅ **无服务器**：纯前端应用，无后端服务器
- ✅ **配置本地存储**：设置保存在浏览器 LocalStorage

### 性能建议

1. **推荐配置**
   - 使用平衡模式或省电模式
   - 关闭不需要的反馈功能
   - 降低检测频率以节省电量

2. **高性能场景**
   - 使用高灵敏度或安防模式
   - 提高检测频率（20-30 fps）
   - 降低采样步进（2-3 px）

3. **省电场景**
   - 使用省电模式
   - 降低检测频率（5-10 fps）
   - 增加采样步进（6-10 px）
   - 启用自动变暗

---

## 📄 开源协议

本项目采用 [MIT License](LICENSE) 开源协议。

```
MIT License

Copyright (c) 2025 依然如梦

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 🙏 致谢

- **MediaStream API** - 提供摄像头访问能力
- **Canvas API** - 实现图像处理功能
- **Web APIs** - 各种硬件接口支持
- 所有贡献者和用户的反馈

---

## 📞 联系方式

- **作者**：依然如梦
- **邮箱**：[aoiud543@gmail.com](mailto:aoiud543@gmail.com)
- **GitHub**：[@yiranrumengqaq](https://github.com/yiranrumengqaq)
- **项目主页**：[yiranrumengqaq.github.io/Buyaa](https://yiranrumengqaq.github.io/Buyaa/)
- **问题反馈**：[Issues](https://github.com/yiranrumengqaq/Buyaa/issues)

---

## 🌟 支持项目

如果这个项目对你有帮助，请：

- ⭐ 给项目一个 Star
- 🔀 Fork 并改进项目
- 🐛 报告 Bug 和问题
- 💡 提出新功能建议
- 📢 分享给需要的人

---

## 📸 界面预览

### 监控界面
- 实时视频预览
- 检测框高亮显示
- 运动强度指示器
- 一键暂停/继续

### 设置界面
- 多种预设模式
- 详细参数调节
- 反馈控制选项
- 电源管理功能

### 日志界面
- 实时事件记录
- 分类筛选功能
- CSV 导出支持
- 统计数据展示

### 统计界面
- 检测次数统计
- 震动次数统计
- 通知次数统计
- 累计运行时长

---

## 💡 使用技巧

### 快速上手

1. **首次使用**
   - 选择平衡模式
   - 授予必要权限
   - 开始检测测试

2. **日常监控**
   - 固定设备位置
   - 调整检测区域
   - 设置合适阈值

3. **省电技巧**
   - 使用省电模式
   - 启用自动变暗
   - 关闭不需要的反馈

### 常见问题

**Q: 为什么 PC 端显示 404？**  
A: 本应用专为移动设备设计，请使用手机或平板访问。

**Q: 检测不够灵敏怎么办？**  
A: 提高检测灵敏度，降低像素阈值，或使用高灵敏度模式。

**Q: 电量消耗太快怎么办？**  
A: 使用省电模式，降低检测频率，启用自动变暗功能。

**Q: 如何导出日志？**  
A: 切换到日志标签页，点击"导出CSV"按钮即可。

**Q: 通知不工作？**  
A: 确保已授予通知权限，并检查系统通知设置。

---

<div align="center">

**[⬆ 回到顶部](#-智能运动检测系统-pro)**

Made with 💜 by 依然如梦

**让监控更智能 | 让安全更简单**

</div>
