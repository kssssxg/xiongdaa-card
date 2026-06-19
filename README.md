# 🌐 xiongdaa 个人名片

> 一个精美的玻璃拟态风格个人主页，包含音乐播放器、实时时钟、一言展示、歌词同步等功能。

## 📸 页面截图

### 主界面
![主界面截图](./2ad87f928b21eb6fec08319b9aa99854.png)

### 歌词面板
![歌词面板截图](./8db5affe3e23581b82d0853472f0c5e1.png)

## ✨ 功能特性

- **玻璃拟态设计** — 采用现代 Glassmorphism 风格，毛玻璃效果搭配动态背景
- **音乐播放器** — 支持 QQ 音乐、网易云音乐搜索播放，黑胶唱片动画，歌词同步显示
- **实时时钟** — 精确到秒的时间显示，带日期信息
- **一言展示** — 随机一言 + 打字机效果
- **🆕 自定义背景** — 支持图片/视频背景，可自由上传本地图片或视频文件作为页面背景
- **🆕 Bing 壁纸** — 集成 Bing 每日精选壁纸 API，一键获取高质量全屏壁纸
- **🆕 历史记录** — 自动记录播放历史，下次打开页面即可快速回顾
- **🆕 持久化壁纸数据** — 壁纸偏好设置自动保存至 localStorage，刷新页面不丢失
- **🆕 默认壁纸 API 更新** — 默认壁纸源已切换，加载更稳定、画质更清晰
- **接口日志** — 内置终端日志面板，实时查看 API 响应
- **响应式布局** — 完美适配桌面端和移动端
- **元标签优化** — 完整的 meta 标签、sitemap、robots.txt 配置

## 🚀 快速开始

### 🌐 在线预览

- **GitHub Pages**: https://kssssxg.github.io/xiongdaa-card/

> 💡 每次 `push` 或创建 `PR` 到 `main` 分支后，页面会自动重新部署，约 1-2 分钟生效。

### 本地运行

```bash
# 直接用浏览器打开 index.html 即可
open index.html
```

### 部署到 GitHub Pages（已配置自动部署）

本项目已配置 GitHub Actions 自动部署：

```bash
# 只需 push 到 main 分支即可自动部署
git push origin main
```

- **触发条件**: 每次 `push` 或创建 `PR` 到 `main` 分支
- **部署地址**: https://kssssxg.github.io/xiongdaa-card/
- **生效时间**: 约 1-2 分钟

### 部署到其他平台

- **Vercel**: `vercel --prod`
- **Netlify**: 拖拽整个文件夹到 Netlify Drop
- **Cloudflare Pages**: `wrangler pages deploy .`

## 📁 项目结构

```
xiongdaa-card/
├── index.html          # 主页面（玻璃拟态个人主页）
├── head-meta.html      # Meta 标签模块
├── 404.html            # 404 页面（公益跳转）
├── robots.txt          # 搜索引擎爬虫配置
├── sitemap.xml         # 站点地图
├── README.md           # 项目说明
└── LICENSE             # MIT 开源协议
```

## 🔧 自定义配置

### 修改个人信息

> ⚠️ **重要**：本项目中所有个人信息已替换为占位符，部署前请务必替换为自己的信息！

编辑 `index.html`，找到以下位置修改：

| 位置 | 内容 | 占位符 | 替换为 |
|------|------|--------|--------|
| Line ~319 | 姓名 | `xiong da` | 你的昵称 |
| Line ~326 | GitHub 链接 | `https://github.com/kssssxg` | 你的仓库 |
| Line ~331 | QQ 号码 | `你的QQ号` | 你的 QQ |
| Line ~336 | 微信号 | `你的QQ号` | 你的微信 |
| Line ~341 | 邮箱 | `你的邮箱` | 你的邮箱 |
| Line ~70 | 头像图片 | `https://q1.qlogo.cn/g?b=qq&nk=你的QQ号&s=640` | 你的头像URL |
| Line ~947 | 音乐封面 | `https://q1.qlogo.cn/g?b=qq&nk=你的QQ号&s=640` | 你的封面URL |
| Line ~2448 | Bio 头像 | `https://q1.qlogo.cn/g?b=qq&nk=你的QQ号&s=640` | 你的头像URL |

### 修改博客 API

博客 JSON API 已替换为占位符，请替换为可用的 API：

```javascript
// 在 index.html 的 <script> 部分找到以下位置
const BLOG_API = '你的博客API';  // ← 替换为你的博客 JSON API
```

#### 📋 博客 JSON 配置文档

页面期望的博客 JSON API 返回以下格式的数据：

```json
{
  "posts": [
    {
      "title": "文章标题",
      "url": "https://yourblog.com/post/1",
      "date": "2026-06-20",
      "excerpt": "文章摘要，最多显示 100 个字符",
      "tags": ["标签1", "标签2"]
    }
  ],
  "total": 1,
  "page": 1,
  "pageSize": 10
}
```

#### 🔍 字段说明

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `posts` | Array | ✅ | 文章列表数组 |
| `posts[].title` | String | ✅ | 文章标题 |
| `posts[].url` | String | ✅ | 文章链接（完整 URL） |
| `posts[].date` | String | ✅ | 发布日期（格式：YYYY-MM-DD） |
| `posts[].excerpt` | String | ❌ | 文章摘要（可选，为空时显示标题） |
| `posts[].tags` | Array | ❌ | 标签数组（可选） |
| `total` | Number | ❌ | 文章总数（可选） |
| `page` | Number | ❌ | 当前页码（可选） |
| `pageSize` | Number | ❌ | 每页数量（可选） |

#### 📝 完整示例

```json
{
  "posts": [
    {
      "title": "我的第一篇博客",
      "url": "https://xiongdaa.me/blog/post-1",
      "date": "2026-06-20",
      "excerpt": "这是第一篇博客的摘要内容，用来展示在个人主页上。",
      "tags": ["生活", "随笔"]
    },
    {
      "title": "ESP32-S3 嵌入式开发笔记",
      "url": "https://xiongdaa.me/blog/esp32-s3-dev",
      "date": "2026-06-18",
      "excerpt": "记录 ESP32-S3 的嵌入式开发过程，包括 GPIO 控制、WiFi 连接等。",
      "tags": ["嵌入式", "ESP32", "开发"]
    },
    {
      "title": "前端玻璃拟态设计实践",
      "url": "https://xiongdaa.me/blog/glassmorphism",
      "date": "2026-06-15",
      "excerpt": "",
      "tags": ["前端", "CSS", "设计"]
    }
  ],
  "total": 3,
  "page": 1,
  "pageSize": 10
}
```

#### 🛠️ 如何生成博客 JSON

**方式一：静态博客生成**
```bash
# 如果使用 Hexo/Hugo/Jekyll 等静态博客
# 在构建时生成 posts.json 文件
hexo generate --json
# 或手动编写 posts.json 放在博客根目录
```

**方式二：自建 API 接口**
```javascript
// Node.js + Express 示例
app.get('/api/posts', async (req, res) => {
  const posts = await db.query('SELECT * FROM posts ORDER BY date DESC LIMIT 10');
  res.json({
    posts: posts.map(p => ({
      title: p.title,
      url: `https://yourblog.com${p.slug}`,
      date: p.created_at.split('T')[0],
      excerpt: p.excerpt,
      tags: p.tags.split(',')
    })),
    total: posts.length
  });
});
```

**方式三：第三方聚合 API**
- 使用 RSS 转 JSON 服务（如 `https://rss2json.com/`）
- 使用静态博客托管平台的 API

#### ⚠️ 注意事项

1. **CORS 跨域**：确保 API 支持 CORS，允许从 GitHub Pages 域名访问
2. **HTTPS**：GitHub Pages 是 HTTPS，API 也必须是 HTTPS
3. **缓存**：建议在 API 响应中添加缓存头，减少请求频率
4. **错误处理**：API 失败时页面会显示错误提示，请确保 API 稳定可用

**推荐的博客 JSON API 源：**
- 自建博客的 JSON 导出接口
- 第三方博客聚合 API
- 静态博客生成的 JSON 文件

### 修改音乐 API

音乐搜索 API 配置在 `index.html` 的 `<script>` 部分：

```javascript
// QQ音乐 API
const url = `https://cyapi.top/API/qq_music.php?apikey=${CYAPI_KEY}...`;

// 网易云音乐 API
const url = `https://v2.alapi.cn/api/music/search?keyword=...`;
```

请替换为可用的 API 密钥。

### 🆕 自定义背景（图片/视频）

页面支持设置自定义背景，可在设置面板中上传本地图片或视频文件：

- **图片背景**：支持 JPG/PNG/WebP 等常见图片格式
- **视频背景**：支持 MP4/WebM 等视频格式，自动循环播放
- **持久化保存**：背景设置自动保存至浏览器 localStorage，刷新页面后自动恢复

### 🆕 Bing 壁纸

页面已集成 Bing 每日精选壁纸，点击壁纸切换按钮即可获取 Bing 最新高清壁纸：

- 使用 `bing.biturl.top` API 获取全尺寸原图（非缓存缩略图）
- 自动适配桌面/移动端分辨率
- 壁纸偏好（是否启用 Bing 壁纸）持久化保存

### 🆕 历史记录

音乐播放历史自动记录：

- 每播放一首歌曲，自动添加到历史记录列表
- 历史记录保存在 localStorage 中，关闭页面不丢失
- 可在播放器面板中快速回顾并重新播放

### 🆕 默认壁纸 API 更新

默认壁纸源已更新为更稳定的接口：

- 新默认壁纸 API：`https://img.8845.top/acg`
- 更少的请求延迟，更高的成功率
- 如需更换壁纸源，可在 `index.html` 的 `<script>` 部分修改 `DEFAULT_BG_API` 配置

## 📄 开源协议

本项目采用 **MIT License** 开源。

详见 [LICENSE](./LICENSE) 文件。

**使用时请保留作者标注**，在 HTML 页面底部已包含仓库链接标注。

---

## ⚠️ 重要声明 / 免责声明

### 🎵 音乐 API 使用须知

> **请务必仔细阅读以下内容，使用本项目即表示您已理解并接受以下条款。**

1. **API 非官方接口**  
   本项目中使用的 QQ 音乐、网易云音乐等音乐搜索及播放接口均为**第三方非官方 API**，并非由 QQ 音乐、网易云音乐等官方提供。本项目作者与这些 API 的提供方无任何合作关系。

2. **仅供学习研究**  
   本项目**仅供个人学习与技术研究使用**，严禁用于任何商业用途、盈利目的或大规模分发。请勿将本项目用于任何侵犯音乐版权的场景。

3. **API 稳定性不保证**  
   第三方 API 随时可能**变更、停止服务或增加验证机制**，导致音乐搜索或播放功能失效。本项目作者**不对 API 的可用性、稳定性、响应速度做任何保证**，也不承担因 API 变更导致的任何损失或责任。

4. **版权风险自负**  
   通过本项目播放的音乐可能涉及**版权风险**。音乐作品的版权归原著作权人所有，未经授权传播或播放可能构成侵权。**使用者需自行承担由此产生的任何法律风险**，本项目作者对此不承担任何责任。

5. **API 密钥安全**  
   项目中包含的 API Key 仅供学习参考，**请勿泄露、共享或用于商业项目**。如发现 API Key 被滥用，API 提供方可能封禁该密钥，导致功能不可用。

6. **音乐链接有效期**  
   音频直链通常具有**时效性**，可能随时失效。如遇歌曲无法播放，属于正常现象，请尝试更换搜索词或等待 API 更新。

### 📋 使用建议

| 场景 | 建议 |
|------|------|
| 个人学习/测试 | ✅ 可以使用，请遵守上述条款 |
| 个人博客/主页 | ✅ 可以使用，建议替换为自己的 API Key |
| 商业项目 | ❌ **严禁使用** |
| 二次分发/打包出售 | ❌ **严禁使用** |
| 大规模公开部署 | ❌ 不建议，API 可能限流或封禁 |

### 🔒 隐私与安全

- 本项目**不会收集或上传任何用户数据**
- 所有 API 请求均直接从用户浏览器发出，**不经过本项目作者的服务器**
- 请勿在项目中填入您的**真实联系方式**，示例中已全部替换为占位符
- 部署前请自行检查并替换所有敏感信息（API Key、邮箱、QQ、微信等）

### 📞 关于 API 问题

如遇 API 失效、响应错误、音乐无法播放等问题：

- ❌ 本项目作者**无法修复第三方 API 的问题**
- ✅ 您可以尝试：更换 API 源、寻找替代 API、或等待 API 提供方修复
- ✅ 欢迎在 GitHub Issues 中反馈，但作者**不保证会修复**

---

> **总结：这是一个学习项目，音乐功能仅供演示。请尊重音乐版权，不要商用，API 挂了别怪我～**

## 🙏 致谢

- [Font Awesome](https://fontawesome.com/) - 图标库
- [Noto Sans SC](https://fonts.google.com/) - 中文字体
- [Hitokoto](https://hitokoto.cn/) - 一言 API
- 所有开源社区 contributors

## 📝 更新日志

### 2026-06-20 — 敏感信息替换
- ✅ QQ号替换为占位符（包括头像URL中的QQ号参数）
- ✅ 微信号替换为占位符
- ✅ 邮箱替换为占位符
- ✅ 博客API替换为占位符
- ✅ 所有个人信息已移除，部署前请自行替换

### 2026-06-19 — 功能增强
- 🆕 自定义背景（图片/视频）
- 🆕 Bing 每日壁纸
- 🆕 播放历史记录
- 🆕 默认壁纸 API 更新
- 🆕 接口日志终端面板

---

## 📮 联系

- GitHub: [@kssssxg](https://github.com/kssssxg)
- 仓库: [xiongdaa-card](https://github.com/kssssxg/xiongdaa-card)

---

> ⭐ 如果觉得有用，请点个 Star 支持一下！

<!-- Updated at 2026-06-20 -->
