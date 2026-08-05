# 小记 - 每日思考与体验

你的私人日记本，支持每日思考问题记录和生活体验记录。

---

## 📱 iPhone 安装方式（推荐：PWA）

无需下载，直接添加到主屏幕，体验接近原生 App：

### 步骤

1. **用 Safari 打开日记页面**
   - 如果你已经部署到服务器，直接访问网址
   - 如果要在本地预览，见下方的「本地预览」

2. **点击 Safari 底部的分享按钮**（⬆️ 方框带箭头）

3. **向下滚动，找到「添加到主屏幕」**

4. **点击「添加」**

5. **完成！** 现在你的 iPhone 主屏幕上就有了「小记」图标，点击即可打开，和原生 App 一样流畅

### PWA 特性
- ✅ 离线可用（无网络也能写日记）
- ✅ 全屏体验（无 Safari 地址栏）
- ✅ 数据保存在本地，隐私安全
- ✅ 启动画面和图标已配置

---

## 🍎 原生 iOS App（需要 Mac）

如果你想打包成真正的 `.ipa` 文件（可以从 App Store 分发），需要一台 Mac 电脑：

### 环境要求
- macOS 系统
- Xcode（从 App Store 安装）
- Node.js + npm

### 步骤

```bash
# 1. 安装依赖
npm install

# 2. 添加 iOS 平台
npx cap add ios

# 3. 同步网页代码到原生项目
npx cap sync ios

# 4. 用 Xcode 打开项目
npx cap open ios
```

然后在 Xcode 中：
- 选择你的 Apple ID 签名
- 连接 iPhone 或选择模拟器
- 点击 ▶️ 运行按钮

打包发布：
```bash
# 在 Xcode 中选择 Product → Archive
# 然后按照提示上传到 App Store Connect
```

---

## 💻 本地预览

### 方式一：Python 简易服务器

```bash
# 进入项目目录
cd diary

# Python 3
python3 -m http.server 8080

# 然后浏览器打开 http://localhost:8080
```

### 方式二：Node.js 服务器

```bash
# 安装 serve（如果还没有）
npm install -g serve

# 启动服务器
serve .

# 会自动打开浏览器，或访问显示的地址
```

### 方式三：VS Code Live Server 插件

在 VS Code 中安装「Live Server」插件，右键 `index.html` → 「Open with Live Server」

---

## 📁 项目结构

```
diary/
├── index.html              # 主页面
├── manifest.json           # PWA 配置
├── service-worker.js       # 离线缓存
├── icon-192.png            # 应用图标（小）
├── icon-512.png            # 应用图标（大）
├── capacitor.config.json   # Capacitor 原生配置
├── package.json            # npm 依赖配置
└── README.md               # 本文件
```

---

## 🔧 数据说明

- 所有日记数据保存在浏览器 `localStorage` 中
- 数据不会上传到任何服务器
- 清除浏览器数据会导致日记丢失
- 建议定期备份（可以导出为文本）

---

## 🎨 功能特性

- ✏️ 每日思考问题记录
- 🌟 每日体验记录
- 📅 支持补写往日记录
- 📖 侧边栏历史记录列表
- 🐱 可切换头像（🐱/🐶/🐦）
- 📱 完美适配手机端
- 🌙 手绘风格界面

---

**Enjoy writing! ✨**
