# GPT-Image-2 风格库站

**在线访问：**

| 页面 | 内容 | 地址 |
| --- | --- | --- |
| 风格画廊 `index.html` | 124 套 PPT 视觉风格的实测出图 | https://bitseek-ailab.github.io/gpt-image2-ppt-styles-gallery/ |
| 提示词总目录 `prompts.html` | 19,582 条唯一提示词，可搜 / 可筛 / 可复制 | https://bitseek-ailab.github.io/gpt-image2-ppt-styles-gallery/prompts.html |

---

# 风格画廊（index.html）

124 套演示文稿视觉风格，每套都用 gpt-image-2.5-flare 渲染了**完全相同的两页内容**
（同一份演示稿的封面页与中间页），所以页面之间唯一的变量就是风格本身。

点任意一张图可以看大图，支持 `←` `→` 翻页、`Esc` 关闭。

---

## 这个页面是什么

| | |
| --- | --- |
| 风格数 | 124 套 |
| 分类 | 12 类（编辑极简 / 数据密集 / 暗色科技 / 学术出版 / 复古手绘 / 品牌系统 / 数字与潮流 / 行业场景 / 东方与艺术 / 模板设计语言 / 配色主题 / 叙事主题） |
| 实测出图 | 248 张（124 × 2 页） |
| 生成模型 | `gpt-image-2.5-flare`，输出 1672×941（16:9） |
| 质检 | 视觉模型逐图按固定 rubric 打分，均分 4.2 / 5 |

每张风格卡片显示：**风格名 / 风格 ID / 分类 / 配色色块 / 字体规范 / 质检分数 / 素材来源链接**。

---

## 关于提示词（口径已于 2026-10-10 更正）

> **更正说明**：本文件此前写「本页不包含提示词正文……提示词模板正文保留在私有仓库中」。
> 自 `prompts.html` 上线后这句话已不成立，此处更正，避免两处口径互相矛盾。

- **`index.html`（本页）：不包含提示词正文。** 只展示成品效果与设计规范（配色、字体、质检结论）。
- **`prompts.html`：公开提示词正文。** 19,582 条唯一提示词来自 15 个**公开来源**，
  按各来源的协议**署名转发**——每条都保留来源名、作者署名（12,846 条有）、原始出处与来源链接。

**使用条件**：提示词版权归各自原作者。本站为**非商业**的个人研究与风格对比用途；
转发遵守各来源协议，其中 `shuixian-archive` 系按**署名使用**转载并回链原仓库。
**商业使用需先联系原作者授权。**

---

## 素材来源

风格提示词来自对 87 个公开风格源（38 个 GitHub 仓库 + 49 个网站/文档站）的整理，
主要包括：

- [xdx888999/xdx-lab-design-skill](https://github.com/xdx888999/xdx-lab-design-skill) — 50 套具名设计语言
- [zarazhangrui/beautiful-html-templates](https://github.com/zarazhangrui/beautiful-html-templates) — 34 套模板设计语言
- [lewislulu/html-ppt-skill](https://github.com/lewislulu/html-ppt-skill) — 36 套主题
- [rohitg00/awesome-claude-design](https://github.com/rohitg00/awesome-claude-design) — 按美学家族分类的 DESIGN.md
- [simonlin1212/SDesign](https://github.com/simonlin1212/SDesign) · [irenerachel/visual-style-ppt-skill](https://github.com/irenerachel/visual-style-ppt-skill) · [software-ai-life/Awesome-PPT-Design-Skills](https://github.com/software-ai-life/Awesome-PPT-Design-Skills) · [1weiho/open-slide](https://github.com/1weiho/open-slide) · [alingowangxr/guizang-ppt-skill](https://github.com/alingowangxr/guizang-ppt-skill) · [topmindspace/tms-skills](https://github.com/topmindspace/tms-skills)
- 以及 Nature 插图规范、Datawrapper 配色规则等公开文档

每个风格卡片底部的「素材来源」链接指向该风格的具体来源页。

---

## 说明

- 页面为纯静态 HTML + JPEG，无外部依赖，可直接下载离线查看。
- 预览图是网页压缩版（宽 1400px）；原始渲染为 1672×941 PNG。
- 风格模板中**不含任何品牌名**——实测在提示词里写品牌名，模型会在画面上画出该品牌的 logo 与字标，
  因此模板只保留设计语言本身（色值、字体性格、版式规则、禁止项），品牌名一律替换为通用描述。
