# QR StarCode

> 免费、开源、纯前端的在线二维码生成器与扫码工具。无需注册、没有水印、不上传数据，打开浏览器即可使用。

<p align="center">
  <img src="og-image.png" alt="QR StarCode 预览" width="720" />
</p>

<p align="center">
  <a href="https://wgh208.github.io/QRstudio/"><img src="https://img.shields.io/badge/在线演示-06b6d4?style=flat-square" alt="Live Demo" /></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-22c55e?style=flat-square" alt="MIT License" /></a>
  <img src="https://img.shields.io/badge/backend-none-06b6d4?style=flat-square" alt="No Backend" />
  <img src="https://img.shields.io/badge/QR%20types-11-8b5cf6?style=flat-square" alt="11 QR Types" />
  <img src="https://img.shields.io/badge/languages-5-f59e0b?style=flat-square" alt="5 Languages" />
</p>

## 项目简介

QR StarCode 是一个功能完整的二维码工具，所有计算都在浏览器本地完成。它不仅能生成常见的网址、文本、Wi-Fi、名片等二维码，还提供 **ChromaCode 图片融合二维码**、**DuitNow 支付码生成** 以及带 **EMV 字段解析的扫码器**。

整个应用由原生 HTML、CSS 和 JavaScript 编写，没有框架、没有构建步骤、没有后端服务。核心页面是单个 HTML 文件，克隆后直接双击即可运行。

- **隐私优先**：二维码内容、Logo、图片均在本机处理，不会上传到任何服务器。
- **免费无限制**：不需要账号，不限制生成次数，导出图片不带水印。
- **开箱即用**：无需安装依赖，支持 GitHub Pages、Cloudflare Pages、Netlify 等静态托管。
- **多语言界面**：内置 English、简体中文、Русский、日本語、한국어 五种语言。

## 功能特性

### 标准二维码生成

- **11 种内容类型**：网址、文本、Wi-Fi、邮件、电话、短信、WhatsApp、地理位置、日历事件、vCard 名片、DuitNow 支付码。
- **实时预览**：输入内容时二维码即时更新，无需点击“生成”。
- **颜色定制**：自定义前景色与背景色，内置 7 套配色方案，并提供对比度提醒。
- **中心 Logo**：上传任意图片作为二维码中心 Logo，自动留出安全边距。
- **边框与留白**：可调整静区宽度和边框样式。
- **节日模板**：圣诞、万圣节、新年、复活节、情人节、圣帕特里克节、生日等装饰边框。
- **Wi-Fi 信息展示**：可将 SSID、密码和加密方式直接写入导出的图片。
- **编码内容可复制**：每种类型都会显示实际编码字符串（如 `mailto:`、`tel:`、`geo:`），并支持一键复制。
- **180+ 国家区号**：电话相关字段提供带国旗表情的国际区号下拉列表。
- **实时校验**：输入时即时检查格式并给出清晰的错误提示。
- **多分辨率导出**：支持 256px、512px、1024px、2048px PNG。
- **SVG 导出**：矢量格式，适合印刷和无限缩放。

### DuitNow 二维码生成

- **EMV QR 字符串构建**：按照 [PayNet QR Spec v1.5](https://docs.developer.paynet.my/docs/duitNow-QR/integration/QR-generation-specification/merchant-presented-mode/qr-data-object) 生成结构合法的 DuitNow EMV 二维码。
- **70 家收单机构**：内置 PayNet 官方列表中的银行、电子钱包和支付服务商。
- **自动 CRC-16**：按 ISO/IEC 13239 计算校验码，并通过 PayNet 规范中的 4 个示例验证。
- **品牌化输出**：生成带有 “MALAYSIA NATIONAL QR” 粉色边框的 DuitNow 样式二维码。
- **静态 / 动态切换**：可选择可重复使用的静态码或一次性动态码。
- **MCC 分类**：提供 25+ 常用商户类别代码。
- **附加字段**：支持参考标签、终端号、账单号、门店标签等。

> **说明**：生成的二维码符合 EMV 格式且 CRC 正确，但**不能直接用于真实收款**。商户号 / QR ID 必须通过收单银行在 PayNet 注册。该功能适合开发者测试 EMV 解析器或学习 DuitNow QR 结构。

### ChromaCode 图片融合二维码

- **图像融合马赛克**：将品牌图片融入二维码，同时保持可扫描性。
- **自动获取 Favicon**：输入网址后自动拉取网站图标。
- **上传或图片 URL**：支持本地图片和远程图片。
- **5 个版本预览**：可对比 QR Version 7、10、13、15、18 的效果。
- **高级参数调节**：点形状（圆形 / 圆角 / 方形）、暗点范围、残影强度、残影阈值。
- **自动调参**：根据图片特征自动选择较合适的参数。
- **配色提取**：自动提取并展示源图片的主色调。

### 扫码器与 DuitNow 解析

- **三种扫描方式**：摄像头、图片上传、剪贴板粘贴。
- **DuitNow EMV 解码**：逐字段展示 DuitNow 与 JomPAY 二维码内容。
- **70 家收单机构识别**：根据 Acquirer ID 显示对应的银行或钱包。
- **CRC-16 校验**：显示校验通过 / 失败，失败时给出期望值。
- **300+ MCC 代码**：将商户类别代码转换为可读名称。
- **JomPAY 识别**：自动识别 JomPAY 二维码（Acquirer 898989）并显示 Biller Code。
- **小费与便利费**：解析 EMV ID 55、56、57。
- **商户渠道解码**：将 3 位字段（ID 62.11）拆解为媒体类型、交易地点和商户存在方式。
- **数据完整性校验**：存在 SHA-256 哈希（ID 82）时进行展示。
- **多语言模板**：展示备用语言的商户名称和城市（ID 64）。
- **丰富附加字段**：账单号、手机号、门店标签、会员号、参考号、客户标签、终端号、用途、消费者数据请求、商户税号、RRN、地理坐标等。
- **22 种货币**：MYR、USD、SGD、THB、IDR、CNY、GBP、EUR、JPY、AUD、HKD、KRW 等。
- **重新生成干净二维码**：根据解析结果重建可扫描的 DuitNow 品牌二维码，支持贴纸到 A4 的打印尺寸以及商户名 / 银行名字号调节。
- **二维码安全分析**：标记可疑网址、开放 Wi-Fi、加密货币地址和支付类二维码风险。

### 通用能力

- 深色 / 浅色主题，自动记忆用户偏好。
- 移动端优先的响应式布局，适配手机、平板和桌面。
- 支持系统原生分享 API。
- 五种界面语言，可随时切换。
- 单文件架构，无构建步骤、无 `node_modules`。
- 所有数据仅在浏览器内处理。

## 快速开始

### 方式一：直接打开

下载或克隆仓库后，双击 `index.html` 即可使用。

```bash
git clone https://github.com/wgh208/QRstudio.git
cd QRstudio
```

> 摄像头扫码功能受浏览器安全策略限制，需要通过 `https://` 或 `http://localhost` 访问。直接以 `file://` 打开时，仍可使用图片上传和剪贴板扫码。

### 方式二：本地静态服务器

```bash
# 任选一种
npx serve .
# 或
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

### 方式三：部署到 GitHub Pages

1. Fork 或在 GitHub 创建本仓库。
2. 打开 **Settings → Pages**。
3. 在 **Source** 中选择 `main` 分支和 `/ (root)` 目录。
4. 保存后访问 `https://<你的用户名>.github.io/QRstudio/`。

`index.html` 为英文默认页，也可以直接访问对应语言页面：

| 页面 | 语言 |
| --- | --- |
| `index.html` | English |
| `zh.html` | 简体中文 |
| `ru.html` | Русский |
| `ja.html` | 日本語 |
| `ko.html` | 한국어 |

## 项目结构

```text
QRstudio/
├── index.html            # 英文主页面，包含全部应用逻辑
├── zh.html               # 简体中文
├── ru.html               # 俄语
├── ja.html               # 日语
├── ko.html               # 韩语
├── blog/                 # 多语言博客文章与列表页
├── ads-analytics.js      # 全站统计 / 广告代码注入入口（默认为空）
├── worker.js             # ChromaCode Favicon CORS 代理（Cloudflare Worker）
├── favicon.svg           # 站点图标
├── apple-touch-icon.png  # iOS 主屏图标
├── og-image.png          # 社交分享预览图
├── robots.txt            # 搜索引擎规则
├── sitemap-0.xml         # 站点地图
└── LICENSE               # MIT 许可证
```

## 支持的二维码类型

| 类型 | 编码格式 | 典型用途 |
| --- | --- | --- |
| URL | `https://example.com` | 网站、活动页、下载链接 |
| 文本 | 原始文本 | 留言、说明、序列号 |
| Wi-Fi | `WIFI:T:WPA;S:MyNet;P:pass123;;` | 扫码自动连接网络 |
| 邮件 | `mailto:hi@example.com?subject=...` | 预填收件人与主题 |
| 电话 | `tel:+8613800138000` | 一键拨号 |
| 短信 | `sms:+8613800138000?body=...` | 预填短信内容 |
| WhatsApp | `https://wa.me/8613800138000?text=...` | 直接发起 WhatsApp 对话 |
| 地理位置 | `geo:39.9042,116.4074` | 地图定位与导航 |
| 日历事件 | iCalendar（`.ics`） | 活动时间、地点、提醒 |
| vCard | vCard 3.0 | 联系人名片 |
| DuitNow | EMV QR（TLV） | 马来西亚支付码测试与演示 |

## ChromaCode Favicon 代理（可选）

ChromaCode 的 **Favicon** 标签会根据网址自动获取网站图标。由于浏览器的跨域限制（CORS），这一功能需要一个代理。没有代理时，**上传图片** 和 **图片 URL** 两种方式仍然可以正常使用。

可以使用免费的 Cloudflare Worker 搭建自己的代理（每天 10 万次免费请求）：

1. 登录 [Cloudflare Workers](https://workers.cloudflare.com/)。
2. 创建一个 Worker，名称例如 `qr-proxy`。
3. 将 [`worker.js`](worker.js) 的内容粘贴到 Worker 编辑器中并部署。
4. 使用以下地址测试：
   ```text
   https://qr-proxy.YOUR-SUBDOMAIN.workers.dev/?url=https://www.google.com/favicon.ico
   ```
5. 在 `index.html` 中找到 `MY_PROXY` 配置并填入你的 Worker 地址：
   ```javascript
   const MY_PROXY = 'https://qr-proxy.YOUR-SUBDOMAIN.workers.dev';
   ```

未配置代理时，应用会尝试使用公共 CORS 代理，但速度和稳定性无法保证。

## 技术栈

| 层级 | 技术 |
| --- | --- |
| 页面与逻辑 | 原生 HTML / CSS / JavaScript |
| 二维码引擎 | [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) 1.4.4 |
| 二维码识别 | [jsQR](https://github.com/cozmo/jsQR) 1.4.0（按需加载） |
| ChromaCode 算法 | [Toms Nimanis / IT Linden](https://github.com/TomsNimanis/chromacode) |
| DuitNow 规范 | [PayNet QR Spec v1.5](https://docs.developer.paynet.my/docs/duitNow-QR/integration/QR-generation-specification/merchant-presented-mode/qr-data-object) |
| 字体 | DM Sans + JetBrains Mono（Google Fonts） |
| 构建系统 | 无 |
| 后端 | 无 |
| 数据统计 | 默认关闭，可在 `ads-analytics.js` 中接入 |

## 隐私说明

QR StarCode 不会把二维码内容、Logo、上传图片或扫码结果发送到服务器。所有生成、渲染、识别和解析都在浏览器中完成。

项目中包含一个可选的 `ads-analytics.js` 注入入口，默认没有任何统计或广告代码。如果你自行接入第三方统计服务，请根据所在地区的法律法规更新隐私政策。

## 自定义与二次开发

- **品牌名称**：搜索 `QR StarCode` 可统一替换页面标题、页头、页脚和元信息。
- **站点地址**：搜索 `SITE_URL` 和 `qrcode.aixmb.cn`，替换为你的域名。
- **默认语言**：直接修改各语言页面的默认文案，或调整 `LANG` 初始化逻辑。
- **主题配色**：在页面顶部的 CSS 变量中修改 `--accent` 等颜色。
- **Favicon 代理**：修改 `MY_PROXY` 常量即可。

## 参与贡献

欢迎提交 Issue 和 Pull Request：

1. Fork 本仓库。
2. 创建功能分支：`git checkout -b feature/your-feature`。
3. 提交修改：`git commit -m "Add your feature"`。
4. 推送分支：`git push origin feature/your-feature`。
5. 在 GitHub 上发起 Pull Request。

由于核心应用是单个 HTML 文件，大多数改动只需要编辑一个文件，调试成本很低。

## 致谢

- 本项目源自 [aixmbcom/QRstudio](https://github.com/aixmbcom/QRstudio)，原作者 [deadboy18](https://github.com/deadboy18)。
- ChromaCode 算法：[Toms Nimanis / IT Linden](https://github.com/TomsNimanis/chromacode)。
- DuitNow EMV 研究与实现参考：[natsu90](https://github.com/natsu90/duitnowqr-test)、[PayNet Developer Docs](https://docs.developer.paynet.my/docs)。

## 许可证

本项目基于 [MIT License](LICENSE) 开源，可自由使用、修改和分发。
