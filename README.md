# 古籍文档理解 – GitHub Pages 项目页

这是一个可直接用于 **GitHub Pages** 的静态站点模板，布局风格参考了常见的论文项目主页（Hero 区 + 摘要 + 动机 + 方法 + 实验 + BibTeX）。

## 使用方法（最快 3 步）
1. 新建仓库并上传本项目所有文件（或解压 zip 后 `git init && git add . && git commit -m "init"`）。
2. 打开 **Settings → Pages**，将 Source 设为 `Deploy from a branch`（通常 `main`/`master`）。
3. 访问 `https://<你的 GitHub 用户名>.github.io/<仓库名>/` 即可。若使用 `username.github.io` 命名主站，则直接访问根域名。

## 自定义
- 修改 `index.html` 中的标题、作者、按钮链接、摘要与图文路径。
- 将你的图片替换进 `assets/` 目录（保持文件名或同步修改 HTML 路径）。
- 样式集中在 `css/style.css`。如需完全仿 EAFormer，可调色彩、圆角与卡片阴影。

## 许可
本模板以 **MIT License** 开源，你可自由修改与分发。若本页对你有帮助，欢迎在页脚或 README 中致谢。