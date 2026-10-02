# 精神物种图鉴（INNER SPECIES）

一个可直接运行的单页人格测试网站。通过 24 个日常情境识别用户的精神栖息地与生存本能，并生成 16 种精神物种之一。

线上版本：<https://inner-species-archive.irene1227.chatgpt.site>

## 当前版本

- 24 道日常情境题
- 4 种精神栖息地 × 4 种生存本能
- 16 种完整精神物种结果
- 16 张“光线作画”透明 PNG 结果图
- 16 张 WebP 兼容回退图
- 召现动画、光雾效果与移动端适配
- 结果保存在浏览器 localStorage
- 无后端、无 API Key、无第三方运行依赖

## 项目结构

```text
.
├── .openai/
│   └── hosting.json
├── dist/
│   ├── assets/
│   │   ├── spirit-*.png   # 16 张当前结果图
│   │   └── *.webp         # 16 张加载失败回退图
│   ├── index.html         # 题目、计分、结果文案与交互
│   └── spectral.css       # 光影、雾化和召现动画
├── .gitignore
└── README.md
```

## 本地运行

克隆仓库后执行：

```bash
python3 -m http.server 8000 --directory dist
```

访问 <http://localhost:8000>。

项目没有构建步骤，也可以直接用浏览器打开 `dist/index.html`。使用本地 HTTP 服务时，分享和剪贴板功能兼容性更好。

## 部署

这是标准静态网站。部署到任意静态托管平台时：

- 构建命令：留空
- 发布目录：`dist`

`.openai/hosting.json` 保留了当前 ChatGPT Sites 项目的配置。若创建全新的 Sites 项目，请先移除其中的 `project_id` 再发布。

## 可复现性

页面运行所需的 HTML、CSS、题目、计分逻辑、16 种结果文案与全部图片都保存在本仓库中，不依赖外部图片链接或临时生成目录。

版本快照：2026-10-02
