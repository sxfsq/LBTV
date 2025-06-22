# LibreTV - 免费在线视频搜索与观看平台

## 📺 项目简介

LibreTV是一个轻量级、免费的在线视频搜索与观看平台，提供来自多个视频源的内容搜索与播放服务。无需注册，即开即用，支持多种设备访问。项目采用纯前端技术构建，可轻松部署在各类静态网站托管服务上。

## ✨ 主要特性

- 🔍 多源视频搜索功能，覆盖电影、电视剧等内容
- 📱 响应式设计，完美支持电脑、平板和手机
- 🌐 聚合多个视频源，自动提取播放链接
- 🔄 支持自定义API接口，灵活扩展
- 💾 本地存储搜索历史，提升使用体验
- 🚀 纯静态部署，无需后端服务器
- 🛡️ 内置广告过滤功能，提供更干净的观影体验
- 🎬 自定义视频播放器，支持HLS流媒体格式
- ⌨️ 键盘快捷键支持，提高观影体验

## ⌨️ 键盘快捷键

LibreTV播放器支持以下键盘快捷键：

- **Alt + 左箭头**：播放上一集
- **Alt + 右箭头**：播放下一集
- **空格键**：暂停/播放
- **左/右箭头**：快退/快进5秒
- **上/下箭头**：调整音量
- **F**：全屏/退出全屏

### CMS采集站源兼容性

本项目支持标准的苹果CMS V10 API格式。自定义API需遵循以下格式：
- 搜索接口: `https://example.com/api.php/provide/vod/?ac=videolist&wd=关键词`
- 详情接口: `https://example.com/api.php/provide/vod/?ac=detail&ids=视频ID`

**重要提示**: 像 `https://360zy.com/api.php/provide/vod` 这样的CMS源需要按照以下格式添加：
1. 在设置面板中选择"自定义接口"
2. 接口地址只填写到域名部分: `https://360zy.com`（不要包含`/api.php/provide/vod`部分）
3. 项目会自动补全正确的路径格式

如果CMS接口非标准格式，可能需要修改项目中的`config.js`文件中的`API_CONFIG.search.path`和`API_CONFIG.detail.path`配置。

## 🛠️ 技术栈

- HTML5 + CSS3 + JavaScript (ES6+)
- Tailwind CSS (通过CDN引入)
- HLS.js 用于HLS流处理和广告过滤
- DPlayer 视频播放器核心
- 前端API请求拦截技术
- localStorage本地存储

## 🔧 自定义配置

项目主要配置在`js/config.js`文件中，你可以修改以下内容：

- `PROXY_URL`: 修改为你自己的代理服务地址
- `API_SITES`: 添加或修改视频源API接口
- `SITE_CONFIG`: 更改站点名称、描述等基本信息
- `PLAYER_CONFIG`: 调整播放器参数，如自动播放、广告过滤等
- `HIDE_BUILTIN_ADULT_APIS`: 用于控制是否隐藏内置的黄色采集站API，默认值为`true`。设置为`true`时，内置的某些敏感API将不会在设置面板中显示，可根据实际需要修改配置。

注意：若使用docker部署，可进入容器，在`/usr/share/nginx/html/js`内修改相关配置


## ⚠️ 免责声明

LibreTV 仅作为视频搜索工具，不存储、上传或分发任何视频内容。所有视频均来自第三方API接口提供的搜索结果。如有侵权内容，请联系相应的内容提供方。
