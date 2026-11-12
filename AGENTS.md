# 多益暖暖筆記本｜AI 協作規則（AGENTS.md）

> 本文件是本專案的唯一規則來源。任何 AI 或協作者在新增、修改頁面前，都必須先完整讀完本文件，並嚴格依照以下規則執行。

---

## 1. 專案目的

- 本網站是一份**多益 650 分學習講義網站**，依「職場情境主題」分課，每課包含：單字、文法、題型技巧與小測驗。
- **讀者**：目標多益 650 分的學生。
- 目標：讓讀者每一課都能用同一套節奏學習，且所有課程頁的結構、風格一致。

---

## 2. 技術限制

- 只使用**純 HTML 與 CSS**，不使用任何 JavaScript 框架或外部函式庫（**Google Fonts 除外**）。
- 測驗答案一律使用 HTML 的 `<details>` 與 `<summary>` 製作，**不需要也不可使用 JavaScript**。
- 網站部署於 **GitHub Pages**，所有路徑必須使用**相對路徑**，**禁止以 `/` 開頭**。
- CSS 引用路徑：
  - 課程頁（`lessons/` 內）：`../assets/css/style.css`
  - 首頁（`index.html`）：`assets/css/style.css`
- 每一頁都必須具備：
  - `<html lang="zh-Hant">`
  - viewport meta：`<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  - `<title>` 格式：`第 XX 課｜主題｜多益暖暖筆記本`（例：`第 01 課｜辦公室日常｜多益暖暖筆記本`）
- 手機版需正常顯示（**響應式設計**）。

---

## 3. 視覺風格：溫暖手帳風

### 3.1 配色（禁止使用表外顏色）

| 用途 | 名稱 | 色碼 |
|---|---|---|
| 網頁背景 | 米白紙張 | `#FBF6EE` |
| 卡片背景 | 白色 | `#FFFFFF` |
| 主要文字 | 深咖啡 | `#4A3B32` |
| 次要文字 | 淺咖啡 | `#8A7565` |
| 主色（標題、按鈕） | 奶茶棕 | `#B98A5E` |
| 強調色（重點單字、提醒） | 珊瑚橘 | `#E8956B` |
| 輔助色（正確答案） | 鼠尾草綠 | `#8FAE8B` |
| 便條紙（重點整理區） | 便條黃 | `#FFF1B8` |
| 邊框、分隔線 | 奶油灰 | `#E6D9C6` |

### 3.2 字型

- 標題：**Huninn（粉圓體）**
- 內文：**Noto Sans TC**
- 兩者皆由 **Google Fonts** 載入。

### 3.3 裝飾

- **區塊標題**：做成斜貼的「紙膠帶」樣式。
- **區塊容器**：每個區塊放在白色圓角卡片內，並帶淡陰影。
- **重點整理**：做成微傾斜的黃色便條紙。

### 3.4 首頁版面

- 所有課程以**卡片格狀**排列。
- **已完成**的課：卡片可點擊，連到該課頁面。
- **未完成**的課：顯示灰色「**製作中**」標籤，且**不可點擊**（不加連結）。
- 手機版改為**單欄**排列。

---

## 4. 資料夾結構

```
toeic650-notebook/
├── AGENTS.md                      # AI 協作規則（本文件）
├── CLAUDE.md                      # 內容僅一行：@AGENTS.md
├── README.md                      # 專案說明
├── index.html                     # 首頁：網站介紹＋課程目錄
├── lessons/                       # 所有課程頁
├── templates/
│   └── lesson-template.html       # 新課程空白範本
└── assets/
    └── css/
        └── style.css              # 全站共用樣式
```

---

## 5. 檔案命名規則

- 格式：`lesson-兩位數編號-英文關鍵字.html`
- 全小寫，單字之間用連字號 `-` 連接。
- **禁止中文與空格**。
- 第 1～10 課檔名：

| 課 | 檔名 |
|---|---|
| 01 | `lesson-01-office.html` |
| 02 | `lesson-02-meeting.html` |
| 03 | `lesson-03-phone-email.html` |
| 04 | `lesson-04-business-trip.html` |
| 05 | `lesson-05-restaurant.html` |
| 06 | `lesson-06-shopping.html` |
| 07 | `lesson-07-hiring.html` |
| 08 | `lesson-08-marketing.html` |
| 09 | `lesson-09-finance.html` |
| 10 | `lesson-10-logistics.html` |

---

## 6. 課程頁固定結構

每一課固定 **8 個區塊**，**順序不可更動，不可新增未定義的區塊**。

### ① 課程標題
- 格式：`第 01 課｜辦公室日常 Office Life`
- 標題下方放**一句情境介紹**。

### ② 📌 學習目標
- 2～3 條。
- 每條以「**能…**」開頭。

### ③ 📝 核心單字
- **固定 10 個**單字。
- 表格欄位：`單字｜詞性｜中文｜例句`
- 詞性縮寫只能使用：`n.` `v.` `adj.` `adv.` `prep.` `phr.`
- 例句格式：英文一句，下一行附中文翻譯。
- 該單字在例句中以**珊瑚橘粗體**標示。

### ④ ✏️ 文法重點
- 每課 **1 個**文法重點，順序固定為：
  1. 白話說明
  2. 句型公式
  3. 2 個例句（附中譯）
  4. 常見錯誤：一句錯誤、一句正確，以「**錯誤**」「**正確**」文字標籤區分

### ⑤ 🎯 題型技巧
- 對應**一個**多益 Part，順序固定為：
  1. 這個 Part 考什麼（一句話）
  2. 3 個解題技巧
  3. 1 題示範題與解題步驟

### ⑥ ❓ 小測驗
- **固定 3 題**四選一，選項標示為 `(A)` `(B)` `(C)` `(D)`。
- 題目須使用本課的單字或文法。
- 每題以 `<details>` / `<summary>` 製作，summary 文字為「**點擊看答案**」，展開後顯示正確答案與中文解析。

### ⑦ 🌟 本課重點整理
- 3～5 條，每條一句。
- 寫在黃色便條紙樣式上。

### ⑧ 導覽
- 提供「上一課／下一課」連結。
- **第 1 課**沒有「上一課」。
- 若**上一課尚未完成**，「上一課」改為**不可點擊的灰色「上一課製作中」**（用 `<span class="nav-btn nav-prev nav-disabled">上一課製作中</span>`，不加連結）。
- **編號最大的課**（以第 8 章課程總表為準，不論其他課是否完成）的「下一課」改為「**回到目錄**」（連回 `../index.html`）。
- 若**下一課尚未完成**，「下一課」改為**不可點擊的灰色「下一課製作中」**（用 `<span class="nav-btn nav-next nav-disabled">下一課製作中</span>`，不加連結）。

---

## 7. 內容撰寫規則

- 使用**繁體中文（台灣用語）**；英文使用**美式拼寫**。
- 語氣親切口語，像**學長姐寫的筆記**，稱讀者為「**你**」。
- 難度對準**多益 650 分**，選用多益高頻單字，避免過難單字。
- 所有例句與題目都必須符合**該課的職場情境**。
- 英文文法必須正確；**不可捏造官方數據或分數換算**。

---

## 8. 課程總表（新增課程時必須查此表）

| 課 | 主題 | 英文 | 文法重點 | 題型技巧 | 狀態 |
|---|---|---|---|---|---|
| 01 | 辦公室日常 | Office Life | 現在簡單式 vs 現在進行式 | Part 1 照片描述 | 已完成 |
| 02 | 會議與簡報 | Meetings & Presentations | 未來式 will / be going to | Part 3 簡短對話 | 已完成 |
| 03 | 電話與 Email | Phone & Email | 禮貌請求 Could you / Would you mind | Part 7 單篇閱讀（Email） | 已完成 |
| 04 | 出差與旅遊 | Business Travel | 時間與地點介系詞 in / on / at | Part 4 簡短獨白（廣播） | 製作中 |
| 05 | 餐廳與聚餐 | Dining Out | 可數與不可數名詞 | Part 2 應答問題 | 製作中 |
| 06 | 購物與客服 | Shopping & Customer Service | 比較級與最高級 | Part 5 句子填空 | 製作中 |
| 07 | 人事與招募 | Hiring & HR | 現在完成式 | Part 7 單篇閱讀（徵才廣告） | 製作中 |
| 08 | 行銷與廣告 | Marketing & Advertising | 被動語態 | Part 4 簡短獨白（廣告） | 製作中 |
| 09 | 財務與預算 | Finance & Budget | 連接詞 because / although | Part 5 句子填空 | 製作中 |
| 10 | 製造與物流 | Manufacturing & Logistics | 關係代名詞 who / which / that | Part 6 段落填空 | 製作中 |
| 11 | 健康與保險 | Health & Insurance | 第一條件句 If + 現在式, will + V | Part 2 應答問題 | 已完成 |

> **狀態欄**只能填「已完成」或「製作中」。每完成一課，必須把該列狀態改為「已完成」。

---

## 9. 新增一課的標準流程（SOP）

1. **查課程總表**：確認該課的主題、文法重點、題型 Part。
2. **複製範本**：將 `templates/lesson-template.html` 複製到 `lessons/`，並依第 5 章命名規則改名。
3. **填入內容**：依第 6、7 章規則填入 8 個區塊內容，HTML 結構與 class 依第 13 章。
4. **更新首頁**：在 `index.html` 中，該課卡片移除「製作中」標籤並加上連結。
5. **檢查前後課**：新增課程後，同時檢查前一課與後一課。
   - 前一課若已完成，將它的灰色「下一課製作中」改為連到新課程的「下一課」連結。
   - 後一課若已完成，將它的灰色「上一課製作中」改為連到新課程的「上一課」連結。
6. **更新總表**：將第 8 章課程總表中該課狀態改為「已完成」。
7. **執行檢查**：逐項執行第 12 章「完成前檢查清單」。

---

## 10. 延伸規則：新增第 11 課以後的主題

- 先在第 8 章**課程總表新增一列**，再製作頁面。
- 主題須為**多益常見職場情境**。
- 文法重點**不可與既有課程重複**。
- 題型 Part 盡量**平均分配**（優先選用目前使用次數較少的 Part）。
- 首頁 `index.html` 須**同步新增卡片**。
- 檔名同樣遵守第 5 章命名規則（例：`lesson-11-xxx.html`）。

---

## 11. 禁止事項

- ❌ 不可在頁面中寫 `<style>` 標籤或 inline `style` 屬性，樣式**只能寫在 `style.css`**。
- ❌ 未經使用者同意，不可修改 `style.css` 的配色與既有樣式。
- ❌ 不可刪除或改名既有課程檔案。
- ❌ 不可使用絕對路徑（包括以 `/` 開頭的路徑）。
- ❌ 不可加入 JavaScript 框架或外部函式庫。
- ❌ 不可使用第 13 章以外的 class；需要新 class 時必須先詢問使用者。
- ❌ 首頁 `index.html` 與 `README.md` 的介紹文字不可寫死課程數量（例如「分成 10 課」），以免新增課程後內容過時。

---

## 12. 完成前檢查清單

每完成一課，提交前必須逐項確認：

- [ ] 8 個區塊齊全，且順序正確
- [ ] 單字 10 個、測驗 3 題，皆附翻譯或解析
- [ ] 檔名符合命名規則
- [ ] 首頁卡片與上一課／下一課連結都能正確點擊
- [ ] CSS 路徑正確，頁面樣式正常
- [ ] 手機寬度下版面正常
- [ ] 只使用第 13 章列出的 class

---

## 13. HTML 結構與 class 對照

### 13.1 使用規則

- 新增或修改課程頁時，**只能使用本章列出的 class**。
- 若需要新的 class，**必須先詢問使用者**；使用者同意後，**同步更新本章對照表與 `style.css`**，兩者必須一致。
- 本章的 HTML 結構範例以 `lessons/lesson-01-office.html` 為準；若兩者不一致，以第 6 章規則為優先，並回報使用者。

### 13.2 class 對照表（共 56 個）

**版面與頁首頁尾（5 個）**

| class | 用途 |
|---|---|
| `container` | 內容置中容器，最大寬度 880px，左右留 16px |
| `site-header` | 頁首（下方虛線分隔） |
| `site-logo` | 頁首的網站名稱連結 |
| `header-link` | 頁首右側「回到課程目錄」連結 |
| `site-footer` | 頁尾 |

**共用元件（6 個）**

| class | 用途 |
|---|---|
| `card` | 白色圓角卡片＋淡陰影，每個區塊的外框（⑦ 除外） |
| `tape-title` | 區塊標題，斜貼紙膠帶樣式（放在 `card` 內的 `<h2>`） |
| `sub-title` | 區塊內的小標題（奶茶棕） |
| `highlight` | 珊瑚橘粗體，用於例句中的單字與重點詞 |
| `reminder` | 左側珊瑚橘線的提醒框 |
| `text-sub` | 次要文字（淺咖啡） |

**① 課程標題（4 個）**

| class | 用途 |
|---|---|
| `lesson-hero` | 課程標題區外框（置中，不用 `card`） |
| `lesson-number` | 「第 XX 課」膠囊標籤 |
| `lesson-title` | 課程主標題 `<h1>` |
| `lesson-intro` | 一句情境介紹 |

**② 學習目標（1 個）**

| class | 用途 |
|---|---|
| `goal-list` | 學習目標清單（前方綠色勾勾） |

**③ 核心單字（5 個）**

| class | 用途 |
|---|---|
| `vocab-table` | 單字表格；手機版自動轉為小卡，`<td>` 需加 `data-label` |
| `vocab-word` | 單字欄（粗體） |
| `pos` | 詞性欄（斜體、淺咖啡） |
| `example-en` | 英文例句（區塊顯示） |
| `example-zh` | 中文翻譯（例句下一行，淺咖啡小字） |

**④ 文法重點（6 個）**

| class | 用途 |
|---|---|
| `formula` | 句型公式框（虛線框、置中） |
| `example-list` | 文法例句清單 |
| `mistake` | 常見錯誤的一行（標籤＋句子） |
| `label-wrong` | 「錯誤」標籤（珊瑚橘） |
| `label-correct` | 「正確」標籤（鼠尾草綠） |
| `mistake-wrong` | 錯誤句子（刪除線） |

**⑤ 題型技巧（4 個）**

| class | 用途 |
|---|---|
| `part-badge` | 「Part X 題型名稱」外框標籤 |
| `tip-list` | 3 個解題技巧（圓形數字編號），用 `<ol>` |
| `demo-box` | 示範題的框 |
| `steps` | 示範題的解題步驟清單，用 `<ol>` |

**⑥ 小測驗（6 個）**

| class | 用途 |
|---|---|
| `quiz-item` | 一題的容器 |
| `quiz-question` | 題目文字 |
| `options` | 四個選項（電腦兩欄、手機一欄） |
| `answer` | `<details>` 本體，`<summary>` 為「點擊看答案」按鈕 |
| `answer-body` | 展開後的解析區 |
| `answer-key` | 「正確答案：(X)」文字（鼠尾草綠） |

**⑦ 本課重點整理（1 個）**

| class | 用途 |
|---|---|
| `sticky-note` | 微傾斜的黃色便條紙（本身就是外框，不再包 `card`） |

**⑧ 導覽（5 個）**

| class | 用途 |
|---|---|
| `lesson-nav` | 導覽列外框 `<nav>` |
| `nav-btn` | 導覽按鈕基本樣式 |
| `nav-prev` | 「上一課」按鈕（語意標記，無額外樣式） |
| `nav-next` | 「下一課」／「回到目錄」／「下一課製作中」按鈕（靠右） |
| `nav-disabled` | 下一課尚未完成時的灰色不可點擊狀態，搭配 `<span>` |

**首頁（13 個）**

| class | 用途 |
|---|---|
| `home-hero` | 首頁標題區 |
| `home-title` | 首頁主標題 |
| `home-subtitle` | 首頁副標題 |
| `lesson-grid` | 課程卡片格狀排列（電腦兩欄、手機單欄） |
| `lesson-card` | 課程卡片；已完成用 `<a>`，製作中用 `<div>` |
| `is-wip` | 搭配 `lesson-card`，製作中的灰色不可點擊狀態 |
| `lesson-card-number` | 卡片上的「第 XX 課」 |
| `lesson-card-title` | 卡片上的中文主題 |
| `lesson-card-en` | 卡片上的英文主題 |
| `lesson-card-meta` | 卡片上的文法與題型 |
| `badge` | 卡片右上角標籤基本樣式 |
| `badge-wip` | 「製作中」標籤（灰） |
| `badge-done` | 「已完成」標籤（鼠尾草綠） |

### 13.3 頁面骨架

```html
<header class="site-header">
  <div class="container">
    <a class="site-logo" href="../index.html">多益暖暖筆記本</a>
    <a class="header-link" href="../index.html#lessons">← 回到課程目錄</a>
  </div>
</header>

<main class="container">
  <!-- ① ～ ⑧ 依序放在這裡 -->
</main>

<footer class="site-footer">
  <div class="container">
    <p>多益暖暖筆記本｜陪你一步步走到 650 分</p>
  </div>
</footer>
```

### 13.4 課程頁 8 個區塊的 HTML 結構（以 lesson-01 為準）

重複的項目（單字列、例句、測驗題）只列一筆示範，實際頁面須補足數量。

**① 課程標題**

```html
<section class="lesson-hero">
  <span class="lesson-number">第 01 課</span>
  <h1 class="lesson-title">第 01 課｜辦公室日常 Office Life</h1>
  <p class="lesson-intro">剛進公司的第一週，影印、交文件、找主管簽名……</p>
</section>
```

**② 📌 學習目標**

```html
<section class="card">
  <h2 class="tape-title">📌 學習目標</h2>
  <ul class="goal-list">
    <li>能說出 10 個辦公室高頻單字，並看懂它們在例句中的用法</li>
    <!-- 共 2～3 條，皆以「能」開頭 -->
  </ul>
</section>
```

**③ 📝 核心單字**

```html
<section class="card">
  <h2 class="tape-title">📝 核心單字</h2>
  <table class="vocab-table">
    <thead>
      <tr>
        <th scope="col">單字</th>
        <th scope="col">詞性</th>
        <th scope="col">中文</th>
        <th scope="col">例句</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td data-label="單字" class="vocab-word">colleague</td>
        <td data-label="詞性" class="pos">n.</td>
        <td data-label="中文">同事</td>
        <td data-label="例句">
          <span class="example-en">My <span class="highlight">colleague</span> is helping me with the monthly report.</span>
          <span class="example-zh">我同事正在幫我做月報。</span>
        </td>
      </tr>
      <!-- 共 10 列 -->
    </tbody>
  </table>
</section>
```

**④ ✏️ 文法重點**

```html
<section class="card">
  <h2 class="tape-title">✏️ 文法重點</h2>
  <h3 class="sub-title">現在簡單式 vs 現在進行式</h3>

  <p>白話說明……可用 <span class="highlight">重點詞</span> 標示。</p>

  <div class="formula">現在簡單式：主詞 + V（第三人稱單數加 s / es）<br>現在進行式：主詞 + am / is / are + V-ing</div>

  <ul class="example-list">
    <li>
      <span class="example-en">Ms. Chen checks her email every morning.</span>
      <span class="example-zh">陳小姐每天早上都會收信。（習慣 → 簡單式）</span>
    </li>
    <!-- 共 2 個例句 -->
  </ul>

  <h3 class="sub-title">常見錯誤</h3>
  <p class="mistake">
    <span class="label-wrong">錯誤</span>
    <span class="mistake-wrong">Look! The manager talks on the phone now.</span>
  </p>
  <p class="mistake">
    <span class="label-correct">正確</span>
    <span>Look! The manager is talking on the phone now.</span>
  </p>
</section>
```

**⑤ 🎯 題型技巧**

```html
<section class="card">
  <h2 class="tape-title">🎯 題型技巧</h2>
  <span class="part-badge">Part 1 照片描述</span>
  <p>這個 Part 考什麼（一句話）</p>

  <h3 class="sub-title">解題技巧</h3>
  <ol class="tip-list">
    <li>技巧 1</li>
    <li>技巧 2</li>
    <li>技巧 3</li>
  </ol>

  <h3 class="sub-title">示範題</h3>
  <div class="demo-box">
    <p>題目與選項（選項之間用 &lt;br&gt; 換行）</p>
    <p><strong>解題步驟：</strong></p>
    <ol class="steps">
      <li>步驟 1</li>
      <!-- 依需要列出步驟 -->
    </ol>
  </div>
</section>
```

**⑥ ❓ 小測驗**

```html
<section class="card">
  <h2 class="tape-title">❓ 小測驗</h2>

  <div class="quiz-item">
    <p class="quiz-question">1. Mr. Park ______ the office supplies every Monday.</p>
    <ul class="options">
      <li>(A) order</li>
      <li>(B) orders</li>
      <li>(C) is ordering</li>
      <li>(D) ordering</li>
    </ul>
    <details class="answer">
      <summary>點擊看答案</summary>
      <div class="answer-body">
        <p><span class="answer-key">正確答案：(B)</span></p>
        <p>中文解析……</p>
      </div>
    </details>
  </div>
  <!-- 共 3 題 -->
</section>
```

**⑦ 🌟 本課重點整理**

```html
<section class="sticky-note">
  <h2>🌟 本課重點整理</h2>
  <ul>
    <li>重點 1</li>
    <!-- 共 3～5 條 -->
  </ul>
</section>
```

**⑧ 導覽**

```html
<nav class="lesson-nav" aria-label="課程導覽">
  <!-- 第 1 課沒有上一課，其他課加上：
  <a class="nav-btn nav-prev" href="lesson-XX-xxx.html">← 上一課</a> -->

  <!-- 上一課尚未完成（改用這行）：
  <span class="nav-btn nav-prev nav-disabled">上一課製作中</span> -->

  <!-- 下一課已完成： -->
  <a class="nav-btn nav-next" href="lesson-02-meeting.html">下一課 →</a>

  <!-- 下一課尚未完成（改用這行）：
  <span class="nav-btn nav-next nav-disabled">下一課製作中</span> -->

  <!-- 編號最大的課（改用這行）：
  <a class="nav-btn nav-next" href="../index.html">回到目錄</a> -->
</nav>
```
