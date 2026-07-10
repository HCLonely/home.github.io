# 个性化配置

## 关键文件

- 首页结构与文案：`index.html`
- 动效与背景逻辑：`assets/js/main.js`
- 主题与周报弹窗：`assets/js/theme-loader.js`
- Bing 壁纸列表生成脚本：`assets/js/bing.js`
- 自动生成的数据文件：
  - `assets/json/images.js`（Bing 壁纸 URL 列表）
  - `assets/json/config.js`（当天主题/时长）
  - `assets/json/weekly.js`（本周统计 + AI 点评）

## 1) 资源引用

当前 `index.html` 默认引用 jsDelivr CDN 资源：

- `https://testingcf.jsdelivr.net/gh/HCLonely/home.github.io@gh-pages/assets/...`
- `https://testingcf.jsdelivr.net/gh/HCLonely/home.github.io@gh-pages/img/logo.jpg`

如需本地调试或完全离线部署，可以把这些 URL 改回相对路径。

## 2) 修改头像、标题、链接

在 `index.html` 中可直接修改：

- 头像图片地址（`.js-avatar`）
- 标题/副标题（如 `HCLonely`、`NO CODE NO LIFE`）
- 导航链接（博客/导航等）

## 3) Email 显示

`index.html` 使用了 `decryptEmail()` 方式做简单混淆：

- 你可以把 Base64 字符串替换为你自己的邮箱
- 或改成明文邮箱链接（文件里已有注释示例）

## 4) 主题调试（无需等 Actions）

`assets/js/theme-loader.js` 支持 URL 参数调试：

- 示例：`/?theme=focused&hours=6`

可用主题名：`rest` / `relaxed` / `productive` / `focused` / `intense` / `legendary`

## 5) 关闭/替换功能（可选）

- 不想要 Bing 背景：删除或注释 `assets/js/main.js` 中加载 `assets/json/images.js` 的逻辑
- 不想要 WakaTime/周报弹窗：不加载 `assets/js/theme-loader.js` 或移除相关 CSS

> 建议先通过文档理解数据流（Actions 生成 → assets/json → 页面加载），再做裁剪。
