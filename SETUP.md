# GitHub 个人首页脚手架 — 使用说明

本仓库用于搭建 [GitHub Profile README](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-readme-profile)（个人主页顶部展示的特殊 README）。

## 快速开始

### 1. 创建仓库

1. 在 GitHub 新建仓库，**仓库名必须与你的用户名完全一致**（例如用户名是 `GlitchedReme`，仓库名也是 `GlitchedReme`）。
2. 设为 **Public**。
3. 勾选 **Add a README**，或把本脚手架内容 push 上去。

### 2. 替换占位内容

在 `README.md` 中全局搜索并替换：

| 占位 | 说明 |
|------|------|
| `GlitchedReme` | 你的 GitHub 用户名 |
| `[你的名字]` | 显示名称 |
| `your.email@example.com` | 邮箱 |
| About Me / Tech Stack / Featured Projects | 按个人情况修改 |

### 3. 启用贪吃蛇贡献图（可选）

1. 将 `.github/workflows/snake.yml` 一并提交到该仓库。
2. 打开仓库 **Settings → Actions → General**：
   - **Workflow permissions** 选 **Read and write permissions**。
3. 在 **Actions** 页手动运行 **Generate Snake**，或等待定时任务。
4. 首次运行会在 `output/` 目录生成 SVG；README 中的 `<picture>` 已指向这些文件。

若 snake 图片暂时 404，属正常：等 Actions 跑完一次即可。

### 4. 本地图片

- `images/wx.png`：微信二维码，已在 README 底部引用。
- 可继续添加 `images/banner.png` 等，并在 README 中用相对路径引用。

## 目录结构

```
.
├── README.md                 # 个人主页主内容
├── SETUP.md                  # 本说明
├── images/
│   └── wx.png                # 微信二维码等资源
└── .github/
    └── workflows/
        └── snake.yml         # 贡献贪吃蛇自动生成
```

## 常用扩展

- **动态统计卡片**： [github-readme-stats](https://github.com/anuraghazra/github-readme-stats)
- **徽章**： [shields.io](https://shields.io) · [markdown-badges](https://github.com/Ileriayo/markdown-badges)
- **打字机动画**： [readme-typing-svg](https://github.com/DenverCoder1/readme-typing-svg)
- **访客计数**： [komarev](https://github.com/antonkomarev/github-profile-views-counter)
- **最新博客 / 动态**：可用 Actions + RSS 或 [recent-blog-posts](https://github.com/gautamkrishnar/blog-post-workflow) 等工作流

## 注意事项

- Profile README **只**在「与用户名同名的公开仓库」的 `README.md` 中生效。
- 外部图片服务（如 stats、typing SVG）依赖第三方 CDN，偶发加载慢属正常现象。
- 勿在 README 中提交密钥、Token 或隐私信息。

## 发布到 GitHub

```bash
git init
git add .
git commit -m "feat: add GitHub profile README scaffold"
git branch -M main
git remote add origin https://github.com/GlitchedReme/GlitchedReme.git
git push -u origin main
```

将 `GlitchedReme` 换成你的用户名后再执行。
