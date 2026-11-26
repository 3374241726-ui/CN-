# 中国 HIP-HOP 的未来 · KV互动网页

已整理为可直接上传 GitHub 的纯静态项目，无需 Node.js、npm、数据库或构建步骤。

## 1. 上传到 GitHub

1. 创建一个新的 GitHub 仓库，仓库名可使用 `hiphop-kv`。
2. 进入仓库，选择 **Add file → Upload files**。
3. 打开本项目文件夹，把**里面的全部文件和子文件夹**拖进上传区域，然后提交。上传后，`index.html` 必须直接位于仓库根目录，与 `assets/` 同级。不要额外套一层 `hiphop-kv-github/` 文件夹。
4. 如果使用提供的 ZIP，先解压，再上传解压后的内容；不要只把 ZIP 文件上传当作网页。

## 2. 启用 GitHub Pages

1. 仓库中打开 **Settings → Pages**。
2. 在 **Build and deployment → Source** 中选择 **Deploy from a branch**。
3. Branch 选择 **main**（或实际保存文件的分支），Folder 选择 **/(root)**，点击 **Save**。
4. 部署完成后，在 Pages 页面打开 GitHub 给出的访问地址。

项目已附 `.nojekyll`，按原样上传即可；没有部署密钥、账号令牌或原托管平台配置。Pages 的可用性取决于仓库及账号设置。

官方说明：[配置 Pages 发布来源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) · [通过网页上传文件](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)

## 文件结构

```text
index.html               完整KV长页入口
album.html               独立专辑抽取入口
style.css / kv.css       画布和长页样式
app.js / albums.js       专辑抽取与专辑资料
music.js                 专辑音乐及暂停控制
culture-music.js         Lilith2、OK、月光三个音乐卡
assets/                  KV切片、封面、噪点和11首音乐
exports/                 原有9套专辑静态SVG/PNG导出
专辑资料与来源.md         专辑资料口径和来源
ASSET_MANIFEST.json      网页文件大小与SHA-256校验清单
WORK_LOG.md              本交付包整理与验证记录
.nojekyll / .gitignore   静态发布标记与本地文件忽略规则
```

## 已保留的功能

- KV章节跳转及手机、平板、桌面等比布局。
- 8张专辑随机抽取、故障过渡、专辑介绍及对应音乐。
- 主按钮换歌、暂停/继续、音频缓冲后揭晓。
- Lilith2、OK、月光卡片点击播放与暂停；音乐卡和专辑音乐互斥播放。
- 三个白色圆钮均约为各自背景框高度的50%，透明点击范围至少44px。
- 折叠工具内返回拼贴、保存SVG/PNG、资料来源和本地追加音乐。

所有网页资源使用相对路径，可部署在 GitHub Pages 的仓库子路径。不要修改资源文件夹名或只上传HTML。

## 本地预览

在本文件夹打开终端，运行：

```sh
python -m http.server 8000
```

浏览器打开 `http://localhost:8000/`；关闭终端即可停止服务。此方法需要已安装 Python。

## 素材与数据

KV、专辑封面和音乐均来自原项目提供的素材。本包未额外附加开放许可。原有主要KV排版使用图片切片，交互控制使用HTML/CSS/JavaScript；不是逐字可编辑的KV矢量稿。

浏览器追加的本地歌曲仅保存在该浏览器的 IndexedDB。更换到 GitHub Pages 地址后，不会迁移原地址的个人追加歌曲；打包的11首内置音乐可直接播放。

本包保留原稿的活动地点和 `2026 / COMING SOON` 文案，没有替换成新的活动公告。专辑静态导出继续保留原版，不包含整个KV的新增矢量导出。
