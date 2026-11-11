# AWESOME / CRAFT

一组零依赖的单文件 Web 交互实验。每个作品就是一个 HTML，内嵌全部 CSS / JS / GLSL，丢进浏览器即可运行。

**在线预览**：<https://jetamie.github.io/awesome-craft/>

## 作品

| # | 作品 | 文件 | 说明 |
|---|---|---|---|
| 01 | 3A 大作 / Port Authority | [`3A.html`](3A.html) | 港区题材第一人称射击体验版，纯 WebGL 着色器绘制，含罗盘 HUD、任务系统与触屏操控 |
| 02 | 黑洞 · 太阳耀斑 · 太阳系 / Null Geodesics | [`black-hole.html`](black-hole.html) | 史瓦西零测地线光线追踪，实时渲染黑洞与吸积盘；可切换电影 / 真实物理模式，另有太阳耀斑、太阳系场景 |

入口页 [`index.html`](index.html) 是作品索引，悬停卡片可实时预览对应页面。

## 本地运行

用任意静态服务器起一个同源 HTTP 地址即可（实时预览依赖同源，`file://` 直接打开时预览不可用）：

```bash
python -m http.server 8000
# 打开 http://localhost:8000/
```

单个作品也可以直接用浏览器打开对应的 HTML 文件。

## 新增作品

1. 把新的 `.html` 放进仓库根目录。
2. 在 `index.html` 中复制一张 `.card`，改 `href`、`data-src`、标题、描述与封面类名。

GitHub Pages 是静态站点，无法自动列举目录文件，所以卡片列表需要手动维护。

## 部署

Push 到 `main` 后由 [`.github/workflows/pages.yml`](.github/workflows/pages.yml) 自动发布 Pages。首次使用需在仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。

若改用 *Deploy from a branch*（`main` / `/(root)`），删除该 workflow 即可；`.nojekyll` 会跳过 Jekyll 构建、保证文件原样发布。

## 目录

```
.
├── index.html                    # Pages 入口 / 作品索引
├── 3A.html                       # 作品 01
├── black-hole.html               # 作品 02
├── .nojekyll                     # 跳过 Jekyll 构建
└── .github/workflows/pages.yml   # Pages 自动部署
```
