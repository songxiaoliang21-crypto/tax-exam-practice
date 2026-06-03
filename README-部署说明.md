# 税务师刷题系统静态公网版

这个目录是可直接部署的静态网站目录。

## 文件

- `index.html`：刷题系统入口，已内置财务与会计第七章至第十九章题库，共 606 道选择题。
- `_headers`：Cloudflare Pages/Netlify 可识别的缓存与安全头配置。
- `robots.txt`：禁止搜索引擎索引，适合个人题库使用。

## 部署方式

### Cloudflare Pages

1. 登录 Cloudflare。
2. 进入 `Workers & Pages`。
3. 选择 `Pages`，点击 `Upload assets`。
4. 上传本目录 `static-public` 内的所有文件。
5. 部署完成后访问 Cloudflare 给出的域名。

### Netlify

1. 登录 Netlify。
2. 进入 `Sites`。
3. 将本目录 `static-public` 拖入页面。
4. 部署完成后访问 Netlify 给出的域名。

### Vercel

1. 新建一个空项目。
2. 将本目录内容上传到项目根目录。
3. Framework Preset 选择 `Other`。
4. Build Command 留空。
5. Output Directory 使用 `.`。

### GitHub Pages

1. 新建 GitHub 仓库。
2. 把本目录内的文件放到仓库根目录。
3. 进入仓库 `Settings -> Pages`。
4. Source 选择 `Deploy from a branch`。
5. Branch 选择 `main`，目录选择 `/root`。

## 数据说明

题库内置在 `index.html` 中，公网访问不需要数据库。

做题记录、收藏、错题本、轮次统计保存在访问设备当前浏览器的 IndexedDB 中：

- 同一浏览器再次打开不会丢失。
- 不同设备之间不会自动同步。
- 清空浏览器网站数据会清除学习记录。

后续如果要多设备同步，可以再增加导出/导入进度或云同步。
