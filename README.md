# GPT-Image-2 图片生成器 - 网页版

一个可分享的图片生成器网页应用，支持纯文字生图和图+文字生图。

## ✨ 功能特点

- 🎨 使用 gpt-image-2 模型生成图片
- ⚙️ 可配置的 API 端点和密钥
- 💾 本地保存配置（下次打开自动加载）
- 📝 纯文字生图模式
- 🖼️ 图+文字生图模式（上传参考图 + 文字描述）
- 🖱️ 拖拽上传图片
- 💾 一键下载生成的图片
- 📋 快速复制提示词
- 📚 生成历史记录（最近50张）
- 🌙 精美的暗色主题
- 📱 完全响应式设计，支持手机端

## 🚀 快速开始

### 方法一：直接打开

直接用浏览器打开 `index.html` 文件即可使用。

### 方法二：本地服务器

```bash
# 使用 Python
python -m http.server 8080

# 或使用 Node.js
npx serve .

# 或使用 PHP
php -S localhost:8080
```

然后访问 `http://localhost:8080`

### 方法三：部署到在线服务器

#### GitHub Pages（免费）

1. Fork 或创建新仓库
2. 上传 `index.html`
3. 进入 Settings → Pages
4. Source 选择 main 分支
5. 访问 `https://username.github.io/repo-name`

#### Vercel（免费）

1. 注册 [Vercel](https://vercel.com)
2. 导入项目
3. 无需配置，自动部署
4. 获得免费域名

#### Netlify（免费）

1. 注册 [Netlify](https://netlify.com)
2. 拖拽文件夹到 Netlify
3. 自动部署
4. 获得免费域名

#### Cloudflare Pages（免费）

1. 注册 [Cloudflare](https://pages.cloudflare.com)
2. 连接 Git 仓库
3. 自动部署
4. 全球 CDN 加速

## 📖 使用方法

### 1. 配置 API

首次使用需要配置你的中转站 API：

1. 展开「API 配置」面板
2. 输入 API 端点地址（如 `https://your-api.com`）
3. 输入 API 密钥（如 `sk-xxx`）
4. 确认模型名称（默认 `gpt-image-2`）
5. 点击「💾 保存配置」

配置会保存在浏览器本地存储中，下次打开自动加载。

### 2. 生成图片

#### 纯文字生图
1. 确保选中「📝 纯文字生图」标签
2. 在提示词框输入图片描述
3. 选择图片尺寸
4. 点击「🚀 生成图片」
5. 等待生成完成

#### 图+文字生图
1. 切换到「🖼️ 图+文字生图」标签
2. 点击上传区域或拖拽图片
3. 输入如何基于图片生成新图的描述
4. 点击「🚀 生成图片」
5. 等待生成完成

### 3. 管理图片

- **下载图片**：点击「💾 下载图片」按钮
- **复制提示词**：点击「📋 复制提示词」按钮
- **查看历史**：在页面底部查看历史记录
- **重新使用**：点击历史记录中的图片可快速使用该提示词

## 💡 提示词示例

### 中文提示词
```
一只可爱的橘猫坐在阳光下的窗台上，温暖的光线洒在它身上，卡通风格，高清
```

```
水彩画风格的山水画，远处是连绵的青山，近处有小桥流水，中国风
```

```
未来城市夜景，霓虹灯倒映在雨后的街道上，赛博朋克风格，电影质感
```

### 英文提示词
```
A futuristic city at sunset, neon lights reflecting on wet streets, cyberpunk style, cinematic
```

```
A cute orange cat sitting on a sunny windowsill, warm light, cartoon style, high quality
```

```
Watercolor landscape painting, distant green mountains, small bridge and flowing water, Chinese style
```

## ⚠️ 常见问题

### Q: 无法连接 API？

A: 检查以下几点：
- API 端点地址是否正确
- API 密钥是否正确
- 中转站服务是否正常运行
- 浏览器控制台是否有错误信息

### Q: 遇到 CORS 跨域错误？

A: 由于浏览器安全策略，直接访问其他域名会受限。解决方案：
- 使用支持 CORS 的中转站
- 部署到与 API 相同的域名
- 使用代理服务器
- 本地测试时使用浏览器 CORS 插件

### Q: 图片生成失败？

A: 可能的原因：
- API 不支持该模型
- API 密钥权限不足
- 提示词不符合安全策略
- 服务器响应超时

### Q: 524 错误是什么？

A: 524 错误表示请求超时，服务器响应太慢。建议：
- 检查网络连接
- 使用更简单的提示词
- 稍后重试
- 联系服务商确认服务状态

### Q: 图+文字模式不工作？

A: 确保你的 API 支持 `/v1/images/edits` 端点。如果不支持，请使用纯文字模式。

### Q: 如何清除保存的配置？

A: 在浏览器开发者工具中：
1. 打开 Console（F12）
2. 输入：`localStorage.clear()`
3. 刷新页面

## 📁 项目结构

```
gpt-image-web/
├── index.html      # 完整的单页面应用
└── README.md       # 使用说明
```

## 🛠️ 技术栈

- **HTML5** - 语义化标签
- **CSS3** - 现代样式（渐变、动画、响应式）
- **Vanilla JavaScript** - 原生 JS，无框架依赖
- **localStorage** - 本地存储配置和历史记录
- **Fetch API** - HTTP 请求
- **File API** - 文件上传处理
- **Drag and Drop API** - 拖拽上传

## 🔧 API 接口要求

### 纯文字生图

**端点**: `POST /v1/images/generations`

**请求体**:
```json
{
  "model": "gpt-image-2",
  "prompt": "your prompt",
  "n": 1,
  "size": "1024x1024"
}
```

**响应**:
```json
{
  "data": [
    {
      "url": "https://...",
      "b64_json": "..."
    }
  ]
}
```

### 图+文字生图

**端点**: `POST /v1/images/edits`

**请求**: `multipart/form-data`

**参数**:
- `model`: 模型名称
- `prompt`: 文字描述
- `n`: 生成数量
- `size`: 图片尺寸
- `image`: 图片文件

**响应**: 同上

## 📄 License

MIT License - 可自由使用和分发

## 🔗 相关资源

- [new-api 项目](https://github.com/QuantumNous/new-api)
- [OpenAI API 文档](https://platform.openai.com/docs/api-reference)
- [GPT-Image-2 介绍](https://openai.com/index/image-generation/)
