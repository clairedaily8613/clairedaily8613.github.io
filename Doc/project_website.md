---
name: project-website
description: Claire Daily 網站架構、品牌色、導覽結構、檔案說明與待辦清單
metadata: 
  node_type: memory
  type: project
  originSessionId: 2eed4438-361b-48ad-9d6c-9737be1f0b2f
---

# Claire Daily 網站建置進度

**Why:** 個人網站，公開每週電子報內容，部署於 GitHub Pages（clairedaily.com），用 Jekyll 靜態生成。

**How to apply:** 每次繼續開發前先確認目前架構與待辦狀態。

---

## 品牌色

> **已於 2026-08-05 換成 The Knowledge Seeker 配色。**
> 權威來源：`Vault/00_CreationSystem/Brand/Characters/the-knowledge-seeker/website-palette.md`
> 實作：`style-seeker.css`；規則寫在 `.claude/skills/clairedaily-website/SKILL.md`。
> 下表為**舊配色，已停用**，僅保留作為歷史紀錄。

| 變數 | 色碼 | 用途 | 比例 |
|------|------|------|------|
| ~~`--bg`~~ | ~~`#FBF7EF`~~ | 頁面底色 | 70% |
| ~~`--primary`~~ | ~~`#2F4A45`~~ | 主要文字、深色元素 | 20% |
| ~~`--accent`~~ | ~~`#C86B4A`~~ | 強調、hover、CTA | 4% |
| ~~`--muted`~~ | ~~`#7E8F9A`~~ | 次要文字、說明文 | 3% |
| ~~`--gold`~~ | ~~`#D8B56D`~~ | 年份標籤、點綴 | 3% |
| `--surface` | `#FFFFFF` | 卡片背景 | — |
| ~~`--border`~~ | ~~`#E8E2D8`~~ | 線條、分隔 | — |

字型未變：Lora（標題serif） + Plus Jakarta Sans（內文sans-serif），Google Fonts。

---

## 網站架構

```
clairedaily8613.github.io/
├── index.md          → 首頁（Hero + 最新文章 + 社群連結）
├── archive.md        → 旅途紀錄（文章列表，按年份分組）
├── _posts/           → 27 篇電子報文章（Jekyll 格式）
├── _layouts/
│   ├── default.html  → 共用外框（header / footer / nav）
│   └── post.html     → 文章頁（繼承 default）
├── style.css         → 完整 CSS design system
├── _config.yml       → Jekyll 設定（permalink: /posts/:year/:slug/）
├── CNAME             → clairedaily.com
├── Drafts/           → 原始草稿（未加入 git，非 _posts 來源）
└── .gitignore        → 排除 .DS_Store、._*、.claude/、.codex/
```

---

## 導覽結構

- 左上 Logo：**Claire Daily** → 連結首頁 `/`
- 右上 Nav：**旅途紀錄** `/archive/` ｜ **訂閱電子報** `https://newsletter.clairedaily.com/landingpagef`

---

## 社群連結

- 電子報：`https://newsletter.clairedaily.com/landingpagef`
- Instagram：`https://www.instagram.com/clairedaily868/`
- Threads：`https://www.threads.com/@clairedaily868`
- Facebook：`https://www.facebook.com/ClaireDaily868`

---

## _posts 說明

- 共 27 篇，來自 `Drafts/2025/`（5篇）與 `Drafts/2026/`（22篇）
- Frontmatter 格式：
  ```yaml
  ---
  layout: post
  title: "2026 Week22 爬山、發燒、然後躺平的一週"
  date: 2026-06-01
  week: "Week22"
  ---
  ```
- Permalink 格式：`/posts/:year/:slug/`
- 全部文章為完整電子報全文（全部公開）

---

## 各頁面說明

### 首頁 (index.md)
- Hero 大標：「Claire 踏上新的旅途」+ 簡介
- 最新一篇文章預覽卡（自動抓 `site.posts.first`，截斷 40 字）
- 社群連結區（電子報、Instagram、Threads、Facebook）

### 旅途紀錄 (archive.md) — 路徑 `/archive/`
- 按年份分組（`group_by_exp`，年份倒序）
- 每篇顯示：標題、摘要前 12 字、月/日

### 文章頁 (_layouts/post.html)
- `← 旅途紀錄` 返回連結
- Week tag + 標題 + 日期
- 完整文章內文
- 訂閱電子報 CTA（深色底卡片）
- 上一篇 / 下一篇導覽

---

## 待辦

- [ ] 本地預覽（`bundle exec jekyll serve` → `localhost:4000`）
- [ ] 推上 GitHub（確認後執行 git add / commit / push）
- [ ] 確認 GitHub Pages build 成功、clairedaily.com 正常顯示
- [ ] 決定是否保留 `Drafts/` 資料夾（目前未被 .gitignore 排除，會上傳）
