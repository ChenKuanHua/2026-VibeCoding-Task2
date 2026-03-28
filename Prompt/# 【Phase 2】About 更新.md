# 【Phase 2】依照 Section SDD 更新單一區塊

（若有 Phase 1：單一 index.html＋HTML/CSS 插槽＋嚴禁 JS＋CSS 不用 #id，則繼續沿用）

你現在是一位「前端工程師＋教練」。

請依照下方《Section 更新規格書 v1.0》，
根據開發者在 [A] 填寫的內容，更新指定的 Section，最後產出一份「更新後完整的 index.html」。

## [A] Section SDD 區塊規格文件（只改這裡）

[A1] 本次要修改的 Section 名稱（擇一填入）：
About

[A2] 本次的 Section SDD 內容（請貼上完整 SDD）：

[Section SDD 開始]
我想做一個「關於我」區塊

內容是：

- 上面一個標題，文字是「靈魂(Soul) - 關於我」。
- 兩小段文字：
  - 當下的交織－在0與1的數位脈動裡，我建構邏輯的秩序；在琴弦的震動之間，我尋找情感的出口。現在的我，正穿梭於數位與實體世界，提供程式開發、視覺設計與生活修繕的專業諮詢。對我而言，生活不是一條直線，而是一場多維度的實踐 ————既是精密的工程師、亦是感受細微的音樂人，在每一個角色切換中，收穫最豐盛的喜悅。
  - 來自於對「底層邏輯」的著迷。無論是修復秀逗的電器、調整一組深蹲的發力、或是優化一段程式效能，我深信萬物皆有其運作的旋律。做事風格如同演奏樂器: 極度專注、追求精準、且帶著一份不隨 意妥協的職人美學。在深沉的穩定中，用冷靜的眼光看見問題，用溫暖的手法包容修復。
- 一個重點列表（約 3 點）：跨維度的問題解決 (Versatile Problem Solving)、理性與感性的視覺轉譯 (Aesthetic Logic)、強韌的身心紀律 (Disciplined Vitality)。

版面希望：

- 手機版：文字在上，下面放一張示意照片。
- 平板以上：左邊是文字，右邊是照片，兩欄排版。

照片用 Unsplash，找「水電職人、或小提琴演奏、健身教練」這種感覺

最後加兩個按鈕（就好）：

- 「查看軌跡」連到 #projects
- 「與我交流」連到 #contact

[Section SDD 結束]

[A3] 目前的 index.html 內容（請貼上 Phase 1 產出的完整檔案）：

[index.html 開始]
（在這裡貼上目前完整的 index.html）
[index.html 結束]

━━━━━━━━━━━━━━━━━━

# Section 更新規格書 v1.0

（Section Update Spec）

一、前置條件與全域規則

1. index.html 來源
   - 檔案為單一 `index.html`。
   - `<head>` 內只有一個 `<style>`，所有 CSS 皆寫在其中。

2. HTML 結構與插槽註解
   - HTML 內包含以下 SECTION 註解插槽，名稱固定：
     - `SECTION:HERO-START / SECTION:HERO-END`
     - `SECTION:ABOUT-START / SECTION:ABOUT-END`
     - `SECTION:SKILLS-START / SECTION:SKILLS-END`
     - `SECTION:PROJECTS-START / SECTION:PROJECTS-END`
     - `SECTION:CONTACT-START / SECTION:CONTACT-END`

3. CSS 結構與插槽註解
   - CSS 內包含以下 Slot 區塊註解，名稱固定：
     - `CSS:BASE`
     - `CSS:HERO`
     - `CSS:ABOUT`
     - `CSS:SKILLS`
     - `CSS:PROJECTS`
     - `CSS:CONTACT`
     - `CSS:RWD`

4. 全域風格與限制（沿用 Phase 1 規格）
   - 禁止使用任何 JavaScript：
     - 不得出現 `<script>`、`onclick`、`addEventListener` 等。
   - CSS 禁用 ID 選擇器：
     - 不得出現任何 `#something` 的 CSS 選擇器。
   - 圖片來源：
     - `<img>` 的 `src` 皆為 Unsplash 相關 URL，且具備合理且非空的 `alt` 屬性。
   - 標題層級：
     - 全站僅有一個 `<h1>`，位於 Hero 區。
   - RWD 策略：
     - 採用手機優先（mobile-first），在 320px / 768px / 1440px 寬度下不應產生水平捲動（依 CSS 設計推估）。

二、更新目標

1. 依據 [A1] 指定的 Section 名稱（Hero / About / Skills / Projects / Contact），
2. 使用 [A2] 提供的 Section SDD（單一區塊規格），
3. 在不破壞「前置條件與全域規則」的前提下，只更新該 Section 的：
   - 對應 HTML 區段（SECTION 插槽中的 `<section>...</section>`）
   - 對應 CSS Slot（以及必要時在 CSS:RWD 中新增/調整對應樣式）。

三、可修改範圍

1. HTML：只修改對應 SECTION 插槽內的 `<section>...</section>`

- 若 [A1] = `Hero`：
  - 修改範圍：
    - `<!-- SECTION:HERO-START -->`
    - `<!-- SECTION:HERO-END -->` 之間的 `<section>...</section>`

- 若 [A1] = `About`：
  - 修改範圍：
    - `<!-- SECTION:ABOUT-START -->`
    - `<!-- SECTION:ABOUT-END -->` 之間的 `<section>...</section>`

- 若 [A1] = `Skills`：
  - 修改範圍：
    - `<!-- SECTION:SKILLS-START -->`
    - `<!-- SECTION:SKILLS-END -->` 之間的 `<section>...</section>`

- 若 [A1] = `Projects`：
  - 修改範圍：
    - `<!-- SECTION:PROJECTS-START -->`
    - `<!-- SECTION:PROJECTS-END -->` 之間的 `<section>...</section>`

- 若 [A1] = `Contact`：
  - 修改範圍：
    - `<!-- SECTION:CONTACT-START -->`
    - `<!-- SECTION:CONTACT-END -->` 之間的 `<section>...</section>`

HTML 必須遵守以下原則：

- SECTION 註解本身（START / END）必須保留，名稱與位置不變。
- 註解中間需包含一個完整的 `<section>...</section>` 結構。
- `section` 的 `id` 預設維持原本命名（hero / about / skills / projects / contact），除非 Section SDD 明確要求變更。
- 非 Hero 區的更新不得新增額外 `<h1>` 元素。

2. CSS：只修改對應 CSS Slot ＋ 必要時的 RWD 區塊

- 若 [A1] = `Hero`：
  - 主要修改範圍：`/* CSS:HERO-START */` ~ `/* CSS:HERO-END */`

- 若 [A1] = `About`：
  - 主要修改範圍：`/* CSS:ABOUT-START */` ~ `/* CSS:ABOUT-END */`

- 若 [A1] = `Skills`：
  - 主要修改範圍：`/* CSS:SKILLS-START */` ~ `/* CSS:SKILLS-END */`

- 若 [A1] = `Projects`：
  - 主要修改範圍：`/* CSS:PROJECTS-START */` ~ `/* CSS:PROJECTS-END */`

- 若 [A1] = `Contact`：
  - 主要修改範圍：`/* CSS:CONTACT-START */` ~ `/* CSS:CONTACT-END */`

如需針對該 Section 設計 RWD 行為（例如桌機版左右雙欄、調整間距等），  
可在 `/* CSS:RWD-START */` ~ `/* CSS:RWD-END */` 之間，新增或調整對應的 `@media` 區塊。

CSS 必須遵守以下原則：

- 僅使用元素選擇器與 class 選擇器，不得新增或保留任何 `#id` 選擇器。
- 其他 Section 對應的 CSS Slot（非本次 [A1] 指定者）不做修改。
- 新增樣式應以該 Section 的 class（如 `.section-hero`、`.section-about` 等）為主。

四、輸出內容要求

1. 在更新完成後，須輸出「更新後完整的 `index.html`」內容：
   - 可直接覆蓋原始 `index.html` 使用。
   - 建議放在單一程式碼區塊中，無需額外說明文字。

2. 在輸出 `index.html` 前，應整理一份簡短的變更摘要（3～8 點）：
   - 說明本次更新針對該 Section 做了哪些修改，例如：
     - 更新 About 文案內容
     - 新增一張 Unsplash 圖片與說明文字
     - 調整桌機版為左右雙欄排版
     - 增加按鈕與 hover 效果等。

五、自我檢查清單（Section 更新後）

更新並輸出 `index.html` 前，需確認以下事項：

1. 標題與結構
   - [ ] 全站仍然只有一個 `<h1>`，位於 Hero 區。
   - [ ] 所有 SECTION 插槽註解（HERO / ABOUT / SKILLS / PROJECTS / CONTACT）名稱完整保留。

2. CSS 結構
   - [ ] 所有 CSS Slot 註解（BASE / HERO / ABOUT / SKILLS / PROJECTS / CONTACT / RWD）完整保留。
   - [ ] 新增或修改的 CSS 選擇器皆未使用 `#id`。

3. 連結與圖片
   - [ ] 新增或修改的 `<a>`，`href` 皆為非空，且不是單純的 `#`。
   - [ ] 新增或修改的 `<img>`：  
          - `src` 來源為 Unsplash。  
          - `alt` 內容合理且非空。

4. RWD 與版面
   - [ ] 依更新後的 CSS 推估，在 320px / 768px / 1440px 下不會產生水平捲動。
   - [ ] 更新後的 Section 排版與 Section SDD 的需求一致（例如欄數、對齊方式、重點資訊呈現）。

━━━━━━━━━━━━━━━━━━

請根據以上《Section 更新規格書 v1.0》，
使用 [A1] / [A2] / [A3] 提供的資訊，只更新指定的 Section，
並輸出更新後完整的 `index.html`。
