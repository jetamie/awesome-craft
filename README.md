# AWESOME / CRAFT

一组零依赖的单文件 Web 交互实验。每个作品就是一个 HTML，内嵌全部 CSS / JS / GLSL，丢进浏览器即可运行。

**在线预览**：<https://jetamie.github.io/awesome-craft/>

## 作品

| # | 作品 | 目录 | 说明 |
|---|---|---|---|
| 01 | Saltline | [`works/port-authority/`](works/port-authority/) | 港区题材第一人称射击体验版，纯 WebGL 着色器绘制，含罗盘 HUD、任务系统与触屏操控 |
| 02 | 黑洞 · 太阳耀斑 · 太阳系 / Null Geodesics | [`works/black-hole/`](works/black-hole/) | 史瓦西零测地线光线追踪，实时渲染黑洞与吸积盘；可切换电影 / 真实物理模式，另有太阳耀斑、太阳系场景 |
| 03 | 赤龍 · Crimson Loong | [`works/crimson-loong/`](works/crimson-loong/) | 90 秒双龙电影，纯 three.js 实时生成：所有网格、纹理、着色器与音符都由代码写出，零素材、零网络请求（WebGL 2，点击开启声音） |
| 04 | 鹈鹕骑行 / Pelican Bicycle | [`works/pelican-bicycle/`](works/pelican-bicycle/) | 手绘风横版骑行跑酷，吃鱼得分、跳跃振翅越过路障、按铃赶海鸥，四段昼夜场景，支持键盘与触屏 |

入口页 [`index.html`](index.html) 是作品索引，悬停卡片可实时预览对应页面。

## 来源与致谢

- `works/crimson-loong/` 转载自 [ChetasLua/crimson-loong](https://github.com/ChetasLua/crimson-loong)，原作「赤龍 · Crimson Loong」。页面内联 three.js r180（MIT，版权横幅保留在文件中）。**上游仓库未声明整体 License**，如需二次分发或商用请先向原作者确认授权。
- 作品 01 / 02 / 04 未标注外部来源。

## 本地运行

用任意静态服务器起一个同源 HTTP 地址即可（实时预览依赖同源，`file://` 直接打开时预览不可用）：

```bash
python -m http.server 8000
# 打开 http://localhost:8000/
```

单个作品也可以直接用浏览器打开对应的 HTML 文件。

## 新增作品

1. 新建目录 `works/<slug>/`，把作品放成 `works/<slug>/index.html`（这样访问 `/works/<slug>/` 直达，且作品后续要加贴图、音频等资源时有地方放）。
2. 在 `index.html` 中复制一张 `.card`，改 `href`、`data-src`、标题、描述与封面类名，两者都指向 `works/<slug>/`。

GitHub Pages 是静态站点，无法自动列举目录文件，所以卡片列表需要手动维护。

## 部署

Push 到 `main` 后由 [`.github/workflows/pages.yml`](.github/workflows/pages.yml) 自动发布 Pages。首次使用需在仓库 **Settings → Pages → Build and deployment → Source** 选择 **GitHub Actions**。

若改用 *Deploy from a branch*（`main` / `/(root)`），删除该 workflow 即可；`.nojekyll` 会跳过 Jekyll 构建、保证文件原样发布。

## 目录

```
.
├── index.html                        # Pages 入口 / 作品索引
├── works/
│   ├── port-authority/
│   │   └── index.html                # 作品 01
│   ├── black-hole/
│   │   └── index.html                # 作品 02
│   ├── crimson-loong/
│   │   └── index.html                # 作品 03（来源见上）
│   └── pelican-bicycle/
│       └── index.html                # 作品 04
├── .nojekyll                         # 跳过 Jekyll 构建
└── .github/workflows/pages.yml       # Pages 自动部署
```
