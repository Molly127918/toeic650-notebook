# 多益暖暖筆記本

一個陪你衝上**多益 650 分**的學習講義網站。內容依職場情境分課，每課都有核心單字、文法重點、題型技巧和小測驗。版面走溫暖手帳風。

- 技術：純 HTML + CSS（只用了 Google Fonts，沒有 JavaScript）
- 部署：GitHub Pages（全站使用相對路徑）
- 完整規則：請看 [AGENTS.md](AGENTS.md)

## 資料夾結構

```
toeic650-notebook/
├── AGENTS.md                  # AI 協作規則（唯一規則來源）
├── CLAUDE.md                  # 指向 AGENTS.md
├── README.md                  # 本檔
├── index.html                 # 首頁：網站介紹＋課程目錄
├── lessons/                   # 所有課程頁
├── templates/
│   └── lesson-template.html   # 新課程空白範本
└── assets/css/style.css       # 全站共用樣式
```

## 如何新增一課

1. 到 `AGENTS.md` 第 8 章的課程總表查這一課的主題、文法和題型 Part。
2. 把 `templates/lesson-template.html` 複製到 `lessons/`，依格式 `lesson-兩位數編號-英文關鍵字.html` 改名，例如 `lesson-01-office.html`。
3. 把範本裡所有【…】佔位文字換成正式內容。8 個區塊的順序不能改，也不能新增區塊。
4. 在 `index.html` 裡把這一課的卡片從 `<div class="lesson-card is-wip">` 改成 `<a class="lesson-card" href="lessons/檔名.html">`，「製作中」標籤換成「已完成」。
5. 同時檢查前一課與後一課：前一課若已完成，把它的「下一課製作中」改成連到新的這一課；後一課若已完成，把它的「上一課製作中」改成連到新的這一課。
6. 把 `AGENTS.md` 課程總表裡這一課的狀態改為「已完成」。
7. 照 `AGENTS.md` 第 12 章的檢查清單逐項確認。

> 樣式只能寫在 `assets/css/style.css`，頁面裡不要寫 `<style>` 或 inline style。
