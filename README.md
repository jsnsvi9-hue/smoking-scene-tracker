# 烟瘾观察 · 吸烟场景记录器

无需注册、不上传行为数据的静态网页应用。记录每次烟瘾：时间、场景、强度、是否抽烟、根数及备注；可修改、删除、查看 7 天统计，导入/导出 JSON、CSV。

## 使用 GitHub Pages 免费发布

1. 登录 https://github.com/new ，建立一个 **Public（公开）** 仓库，建议仓库名称为 `smoking-scene-tracker`。如果选择 README 初始化，先建仓库后上传以下文件。
2. 将本 ZIP 解压后，进入仓库主页，点 **Add file → Upload files**，上传 `index.html`、`manifest.webmanifest`、`sw.js`、`icon-192.png`、`icon-512.png`、`.nojekyll`（`.nojekyll` 隐藏文件可不传）。**文件必须放在仓库根目录，不要多套一层文件夹。** 最后点 Commit changes。
3. 打开仓库 **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main / (root) → Save**。
4. 等 GitHub 显示已发布后，打开 `https://你的GitHub用户名.github.io/smoking-scene-tracker/`。如果自选了其他仓库名，替换路径部分。
5. 安卓 Chrome 打开这个 HTTPS 网址，点右上角菜单 → **添加到主屏幕** 或 **安装应用**。之后只打开这个固定网址/桌面图标，不要再收藏本地 `content://` 地址。

官方说明： https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 重要：数据保存在何处？

- GitHub 只托管**应用代码**，不存储你的个人吸烟记录。记录保存在**这个域名下、这台设备、这个浏览器**的 localStorage 中。
- 从旧的本地 `.html` 文件切换到新域名时，记录不会自动转移。若旧文件还有数据，请先在旧版导出 JSON，在新版点击「导入 JSON 备份」。
- 清除浏览器网站数据、更换浏览器/设备、卸载关联 PWA 等操作可能导致数据丢失。建议每周导出一次 JSON 到安全位置，确认文件真实保存。
- 部分安卓设备仅显示「添加到主屏幕」快捷方式而非可安装 PWA，这是浏览器行为，不影响打开网页和记录数据。
- 初次加载需要联网；访问一次后，支持在常见兼容浏览器中离线打开，但应提前实际测试。
- GitHub Pages 公共站点任何人都可以看到应用**源代码**，不要把个人记录、真实备份 JSON 或密钥上传仓库。

## 仅用手机快速发布

如果你在安卓手机里上传整包文件比较费劲，可以先只把 `index.html` 和 `icon-192.png` 上传到仓库根目录并开通 Pages，此时固定 HTTPS 网址和本地记录可用，但完整 PWA 安装/离线功能需再上传剩余文件。建议优先一次上传全部文件。

## 技术

原生 HTML/CSS/JavaScript，无依赖、无广告、无分析代码和远程 API。兼容 GitHub Pages 子路径，静态部署无需后端。`smoking-scene-tracker-v1` 为持久化数据键。
