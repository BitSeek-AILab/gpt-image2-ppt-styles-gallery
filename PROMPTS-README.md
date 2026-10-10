# 提示词总目录（prompts.html）

**页面：** `prompts.html` — 公开来源提示词的只读浏览页：按源筛选 / 关键词搜索 / 看正文 / 一键复制。
**数据：** `prompts-data/`（`manifest.js` + `tables.js` + `idx-NN.js` + `txt-NNN.js`），全部由脚本生成，不要手改。

| | |
| --- | --- |
| 数据行数 | 19,582（合并后已跨源去重，行数 = 唯一文本数） |
| 唯一文本（按全文 sha256 去重） | 19,582 |
| 源 | 15 个（含 `shuixian-archive` / `shuixian-archive-modern`） |
| 正文总字数 | 15,757,589 |
| 有作者署名的行 | 12,846 |
| 有配图的行 | 17,897 |
| 数据指纹 | `catalog.jsonl` sha256 = `7386faef8d8157e355f68ff232071953e555e8b5498273ded3bc7013d73d93bb` |

## 这个页面是什么

把全项目的提示词底表（`.cache/prompt-catalog/catalog.jsonl`）做成了一个**纯静态、可离线打开**的浏览页。
它和同目录的 `index.html`（画廊页，展示成品效果与设计规范）是**两个独立页面**，互不影响：

- `index.html` — 139 套 PPT 风格的成品图与配色/字体规范，**不含提示词正文**。
- `prompts.html` — 提示词**正文**底表，可搜可复制，用于「看提示词、跑新设计」。

每条卡片显示：**源 / 类型 / 标题 / 分类 / 作者 / 字数 / 语言 / 文本指纹 / `id` / `origin_id` / 来源链接 / origin_file**，
点「看正文」按需载入该条所在分片，「复制正文」直接进剪贴板。

`id` 是全项目合并后的顺序号（`p000001`…），`origin_id` 是**它在原来源里的原始编号**（如 `shuixian-archive:13440`），
两者都显示出来便于回查原来源。

## 怎么用

| 操作 | 说明 |
| --- | --- |
| 按源筛选 | 顶部源名胶囊（13 个源，各自行数） |
| 按类型筛选 | 风格 / 案例 / 模板 |
| 关键词搜索 | 搜索框即时匹配 **标题 / 分类 / 作者 / 源 / origin_file**（回车确认） |
| 全文搜索 | 点「在全部正文中搜索」：按需载入全部分片后在**正文**里做子串匹配，带命中片段 |
| 只看有配图 | 勾选后只留 `image_urls` 非空的行 |
| 只看唯一文本 | 按 12 位文本指纹去重（当前数据已 100% 唯一，勾了等于没变化，留着以防未来出现重复行） |
| 看 / 复制正文 | 每条卡片上的两个按钮，复制走 `navigator.clipboard`（失败自动降级 `execCommand`） |
| 深链 | 支持 URL 参数（`?` 或 `#` 皆可）：`q` `src` `kind` `img=1` `uniq=1` `page` `open=<行号>` `full=1` `selftest=1` |

示例：`prompts.html#src=shuixian&q=%E6%B5%B7%E6%8A%A5`、`prompts.html#open=42`、`prompts.html#selftest=1`（页面内自测：随机 5 条能否被搜到）。

## 数据从哪来

`catalog.jsonl` 是 T7/T9 归一合并后的总目录，15 个公开来源：

| 源 | 行数 | 唯一文本 | 有配图 | 有作者 | 原始仓库 / 站点 |
| --- | ---: | ---: | ---: | ---: | --- |
| [shuixian-archive](https://github.com/BaYue-SYJ/Awesome-shuixian-prompts-archive) | 10,055 | 10,055 | 10,039 | 10,055 | https://github.com/BaYue-SYJ/Awesome-shuixian-prompts-archive |
| [shuixian](https://github.com/BaYue-SYJ/shuixian-prompts) | 5,233 | 5,233 | 5,233 | 0 | https://github.com/BaYue-SYJ/shuixian-prompts |
| [Vieeeeeee](https://github.com/Vieeeeeee/skills-gallery)（按目录名推得） | 1,298 | 1,298 | 0 | 999 | https://github.com/Vieeeeeee/skills-gallery |
| [freestylefly](https://x.com/akokoi1/status/2045693939584516441) | 517 | 517 | 517 | 517 | https://x.com/akokoi1/status/2045693939584516441 |
| [BigPengSays](https://promptgather.io/prompts/gpt-image-2) | 517 | 517 | 517 | 517 | https://promptgather.io/prompts/gpt-image-2 |
| [shuixian-archive-modern](https://github.com/BaYue-SYJ/Awesome-shuixian-prompts-archive) | 448 | 448 | 448 | 0 | https://github.com/BaYue-SYJ/Awesome-shuixian-prompts-archive |
| [T8mars](https://x.com/Kashiko_AIart/status/2046154976159035613) | 432 | 432 | 392 | 197 | https://x.com/Kashiko_AIart/status/2046154976159035613 |
| [xiaoxiaodong](https://github.com/nevertoday/xiaoxiaodong) | 423 | 423 | 423 | 0 | https://github.com/nevertoday/xiaoxiaodong |
| [xianyu110](https://youmind.com/gpt-image-2-prompts?id=30753) | 243 | 243 | 243 | 243 | https://youmind.com/gpt-image-2-prompts?id=30753 |
| [xxd-panel](https://github.com/nevertoday/xxd-panel-001) | 233 | 233 | 0 | 233 | https://github.com/nevertoday/xxd-panel-001 |
| [ToseaAI](https://tosea.ai/prompts/gpt-image-2#01-a-photorealistic-capture-of) | 58 | 58 | 58 | 58 | https://tosea.ai/prompts/gpt-image-2#01-a-photorealistic-capture-of |
| [xiaoxiaodong-articles](https://vip.xiaoxiaodong.ai/tools/article/x-draft-2056277870830645248) | 53 | 53 | 0 | 0 | https://vip.xiaoxiaodong.ai/tools/article/x-draft-2056277870830645248 |
| [spsrx](https://github.com/spsrx000000-crypto/awesome-gpt-image-2)（按目录名推得） | 32 | 32 | 19 | 19 | https://github.com/spsrx000000-crypto/awesome-gpt-image-2 |
| [XZXY-AI](https://github.com/XZXY-AI/awesome-gpt-image-2-playground)（按目录名推得） | 32 | 32 | 0 | 0 | https://github.com/XZXY-AI/awesome-gpt-image-2-playground |
| [SurgePix](https://surgepix.ai/resources/gpt-image-2-prompts) | 8 | 8 | 8 | 8 | https://surgepix.ai/resources/gpt-image-2-prompts |

## 版权 / 署名（**必读**）

- 提示词来自公开来源，**版权归原作者**；页面与文档仅用于个人研究与风格对比。
- 每条卡片保留来源与出处（`id` / `origin_id` / `origin_file`）与作者署名，未做任何抹除。
- **非商业使用需保留出处与链接**（见上表「原始仓库 / 站点」列）；**商用需联系原作者授权**。
- `shuixian-archive` / `shuixian-archive-modern` 来自
  [BaYue-SYJ/Awesome-shuixian-prompts-archive](https://github.com/BaYue-SYJ/Awesome-shuixian-prompts-archive)，
  该仓库按 **署名使用** 条款发布（非商业可自由使用，须保留出处并链接回原仓库）。
- 表里标「按目录名推得」的链接，是源数据里没有 URL、按下载目录约定 `Owner__Repo` 补的（该约定在
  shuixian / freestylefly / SurgePix 三个源上被源文件自身的 URL 验证过）；其余链接直接取自源数据。

## 怎么重新生成

**改数据后只需跑这一条**（读 `catalog.jsonl`，重写 `prompts.html` + `prompts-data/` + 本文件）：

```powershell
E:\miniconda3\python.exe E:\AIAgent\Artist\.scratch\tools\build_prompt_site.py --build
```

其他模式：

```powershell
# 只看体积/分片方案，不写文件
E:\miniconda3\python.exe ...\build_prompt_site.py --plan
# 回读产物自检：分片覆盖性、id/origin_id 一致性、正文逐条比对、页面体积、是否引用外部资源
E:\miniconda3\python.exe ...\build_prompt_site.py --verify
# 写到别处（本机沙箱对 gallery-site 无写权限时先用暂存目录，再整目录拷进去）
E:\miniconda3\python.exe ...\build_prompt_site.py --build --out E:\AIAgent\Artist\.cache\prompt-site
```

脚本确定性：不使用时间戳/随机数，`gzip.compress(..., mtime=0)`，同样的 `catalog.jsonl` 产出逐字节相同的分片。

`--verify` 还会在站点目录下写 `_verify/domcheck.mjs`（Node 版 DOM 自检桩）：它把 `prompts.html` 里的**真实页面脚本**
在 Node + 极简 DOM 桩里跑一遍（真加载分片、真 gunzip、真走「在全部正文中搜索」那条代码路径），用来在没有浏览器时做端到端验证：

```powershell
node _verify\domcheck.mjs --root="<站点目录>" --mode=default                                   # 索引载入 + 统计 + 首屏卡片 + 筛选计数
node _verify\domcheck.mjs --root="<站点目录>" --mode=default --hash="#src=shuixian-archive&img=1" # 按源 + 只看有配图
node _verify\domcheck.mjs --root="<站点目录>" --mode=needles --needles="_verify\needles.json"   # 5 条随机关键词全文搜索
node _verify\domcheck.mjs --root="<站点目录>" --mode=selftest --hash="#selftest=1"              # 页面内自测（应 5/5）
node _verify\domcheck.mjs --root="<站点目录>" --mode=expand --k=10022                           # 展开一条正文（走分片 + gunzip）
```

## 实现要点（为什么长这样）

1. **不能用 `fetch`**：页面要能用 `file://` 双击打开，而 Chromium 对 `file://` 的 fetch/XHR 一律按 CORS 拒绝。
   所以分片全部是 `.js`，靠动态注入 `<script src>` 载入（script 标签不受 CORS 限制），
   数据入口是 `PC.idx(i, base, rows)` / `PC.txt(i, b64)`。
2. **首屏体积**：`prompts.html` 只有 23.3 KB，**不含任何正文**；`manifest.js` 14.1 KB + `tables.js` 179.6 KB。
   索引分片 16 个（后台顺序载入，累计约 2,071 KB），正文分片 127 个（gzip 后约 12,706 KB），
   **正文只在点「看正文 / 复制正文 / 全文搜索」时才下载**。分片是按**累计字节**切的，不按源切，
   所以 `shuixian-archive`（1 万多条）会自然摊到多个分片里，不会出现单个超大 JSON。
3. **索引瘦身**：`source / category / author / language / origin_file / source_url / kind` 做字符串内联表，
   行数据用数组而不是对象，省掉重复 key；`id` 是 `p000001` 顺序号，直接由行号推导、索引里不存；
   行的全局序号即它在 `catalog.jsonl` 里的顺序，所以索引里也不需要存「正文分片指针」——
   正文分片有自己的 `base` 区间表，前端二分查找。
4. **无外部依赖**：页面不引用任何 CDN / 字体 / 图片；`gzip` 解压用的是浏览器原生 `DecompressionStream`。
5. **XSS 安全**：所有数据经 `esc()` 或 `textContent` 落地，提示词正文里的 `<` `>` 不会破坏 DOM。

## 已知边界

- 全文搜索是**客户端逐分片子串匹配**，首次会下载全部分片（约 12,706 KB gzip），本地很快；之后分片进内存缓存，再搜就快了。
- `id` 由行号推导（要求 `catalog.jsonl` 的 id 是 `p000001` 顺序号）；上游一旦改 id 规则，`--build` 会直接报错而不是静默标错编号。
- 「只看唯一文本」用的 12 位文本指纹（`text_sha256` 前 12 位），构建期已校验无碰撞（见 `--verify`）；
  当前合并结果本身已 100% 唯一，所以这个开关目前不改变结果。
- 卡片里的 `origin_file` 是**源文件相对路径**（相对项目根 `E:\AIAgent\Artist`），用于回溯；
  不同源的 `source_url` 口径见 `.scratch\catalog\CATALOG.md` 第 9 节。
- `image_urls` 里不少是源站相对路径，本站**不加载图片**，只标注「有配图」并给来源链接（避免死图）。
- 本页**不 push**：是否发布到 `bitseek-ailab.github.io` 由项目负责人决定（数据体积见上表）。
