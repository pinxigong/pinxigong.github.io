# Pinxi Gong — Minimal Academic Website

极简英文科研个人主页。**纯 HTML + CSS，没有 JavaScript、框架、动画或外部依赖。** 使用相对路径，支持 GitHub Pages 个人主页仓库和项目仓库。

## 文件说明

- `index.html` — 主页全部文字与各板块的顺序
- `styles.css` — 排版、字体、颜色、宽度
- `cv.pdf` — 简历（公开可下载）
- `figures/` — 放科研可视化图片；目前没有放任何虚构的科研结果图
- `.nojekyll` — 静态发布配置

## 上传到 GitHub Pages

1. 新建公开仓库 `USERNAME.github.io`，`USERNAME` 替换为你的 GitHub 用户名。
2. 上传这里所有文件至仓库**根目录**，不要上传压缩包本身，也不要多包一层文件夹。
3. 在 **Settings → Pages → Build and deployment** 选择 **Deploy from a branch**、`main`、`/(root)`，保存。
4. 访问 `https://USERNAME.github.io/`。如果使用另一个仓库名（如 `website`），网址则通常是 `https://USERNAME.github.io/website/`。

官方文档：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 修改文字

打开 `index.html`，找到相应段落（例如项目标题），直接编辑文字即可。GitHub 网页端：打开文件 → 点右上角铅笔图标（Edit）→ 提交（Commit changes）。

如果在本地维护：

```bash
git clone https://github.com/USERNAME/USERNAME.github.io.git
cd USERNAME.github.io
# 用 VS Code 或其他编辑器修改文件
git add index.html styles.css figures cv.pdf
git commit -m "Update academic website"
git push
```

每次推送到所选发布分支，GitHub Pages 会重新发布。修改纯文本无需 Node.js、Jekyll。

更新 CV：将新版 PDF 覆盖 `cv.pdf`，再提交更改。**注意：公开仓库的旧版本可能仍保留在 Git 历史中；不要上传不希望公开的信息。**

## 添加科研图片（最简单的方法）

**第一步**：用 Python/Matplotlib、MATLAB、R、LaTeX/TikZ 等导出自己的真实科研图片到 `figures/`，如：

```
figures/
  cp-als-convergence.png
  robust-pca-recovery.png
```

推荐静态图：PNG（适合热力图、截图）；SVG 或 PDF 转 SVG（线图、理论示意图；确保不含敏感信息）。为了浏览器兼容，可优先 PNG / SVG。高分辨率图尽量控制大小，避免页面加载太慢。

**第二步**：到 `index.html` 对应的项目段落下面加入：

```html
<figure class="research-figure">
  <img src="figures/cp-als-convergence.png"
       alt="CP-ALS reconstruction error against iterations"
       loading="lazy">
  <figcaption>Figure 1. Reconstruction error over iterations for a selected experiment.</figcaption>
</figure>
```

文件里 **CP-ALS 项目已经预留了一段被 HTML 注释隐藏的 `<figure>` 示例**。如果你上传了相应图片，可以去掉其前后的 `<!--` 和 `-->`，并修改 caption/alt 为与你的真实实验对应的描述。

图片不应写上未经证实的收敛结论，也不要公开论文审稿中的保密内容。建议直接选已有 preprint、poster 或本人实验中可公开的图片。

**第三步**：上传图片，并提交更新后的 `index.html`。样式已包含自适应排版、图片宽度控制和 caption，不需要修改 CSS。

## 该把图放在哪里？

- **CP-ALS**：一张收敛曲线或 reconstruction error 与 iteration 的关系图（须来自真实实验）
- **Robust PCA**：一张 clean / corrupted / recovered 对比图，或一张关键理论条件的简洁示意图
- **更多图片时**：为该项目建立独立页面 `projects/cp-als.html`，主页只保留摘要和链接，以免首页过长

## 关于公开性

- `USERNAME.github.io` 的 URL 暴露 GitHub 用户名；访问者可以尝试 `https://github.com/USERNAME` 打开 GitHub 主页。
- 即使用自定义域名，不能把 GitHub Pages 视为匿名托管。若不希望学术主页关联个人开发仓库，建议使用独立 GitHub 账号发布网站。
- GitHub Pages 站点通常是公开可访问的；**仓库私有不等于网站私有**。

## 本地预览

直接在浏览器打开 `index.html` 即可。或在当前文件夹执行：

```bash
python -m http.server 8000
```

访问 `http://localhost:8000`。

## 信息来源

页面内容根据 2026 年 11 月提供的 CV 整理。论文“under review”和 CP-ALS 项目“present”是会变化的状态，日后请及时更新。网页正文刻意省略 GPA 和成绩以保持简洁；但公开的 `cv.pdf` 仍包含这些信息。
