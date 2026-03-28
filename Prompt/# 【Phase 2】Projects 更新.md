# 【Phase 2】依照 Section SDD 更新單一區塊

（若有 Phase 1：單一 index.html＋HTML/CSS 插槽＋嚴禁 JS＋CSS 不用 #id，則繼續沿用）

你現在是一位「前端工程師＋教練」。

請依照下方《Section 更新規格書 v1.0》，
根據開發者在 [A] 填寫的內容，更新指定的 Section，最後產出一份「更新後完整的 index.html」。

## [A] Section SDD 區塊規格文件（只改這裡）

[A1] 本次要修改的 Section 名稱（擇一填入）：
Projects

[A2] 本次的 Section SDD 內容（請貼上完整 SDD）：

[Section SDD 開始]
區塊目標：建立一個名為「軌跡 (Trace)」的作品集展示區。

內容與文案：

- 區塊標題：「軌跡 (Trace) - 時間留下的印記」
- 引言：「每一項產出，都是一段專注時光的凝結。這裡記錄了我與不同領域碰撞出的火花，是我在多元人生中一步步留下的實踐痕跡。」
- 四大分類標籤：邏輯的軌跡、音符的軌跡、修繕的軌跡、視覺的軌跡。

版面設計希望：

- 整體架構：上方是置中的標題與引言，緊接著是 4 個分類的「藥丸型切換按鈕 (Pill-shaped Filter Buttons)」。
- 排版風格：請採用「瀑布流佈局 (Masonry Grid)」。因為作品包含直式的海報/紅包袋設計、橫式的 Python 程式碼截圖、以及正方形的修繕對比圖，瀑布流能最自然地錯落排列。
- 互動效果 (Hover State)：
  - 預設狀態下，圖片上覆蓋一層極淡的深色遮罩。
  - 當滑鼠懸停 (Hover) 在某個作品卡片上時，遮罩變深，並從卡片底部滑出該作品的「標題」與「簡短說明」（例如：『邏輯的軌跡 - 飯店自動化報表腳本』或『修繕的軌跡 - 電路板修復紀錄』）。
- 切換動畫：點擊分類標籤時，不屬於該分類的卡片要平滑淡出並縮小 (Scale down)，留下的卡片自動重新排列。
- 手機版：維持分類按鈕可橫向滑動 (Swipeable)，下方卡片改為單欄或雙欄的緊湊排列。

[Section SDD 結束]

[A3] 目前的 index.html 內容（請貼上 Phase 1 產出的完整檔案）：

[index.html 開始]

<!doctype html>
<html lang="zh-Hant">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="icon" href="icon.png" type="image/png">

    <title>晨光步調｜Life & Craft</title>
    <meta
      name="description"
      content="這是一個個人品牌網站骨架，用來介紹個人背景、技能專長、作品集與聯絡方式，提供未來逐步擴充與優化內容的基礎架構與清晰區塊插槽設計。"
    />

    <style>
      /* ===============================
           CSS:BASE-START
        =============================== */

      * {
        box-sizing: border-box;
      }

      body {
        margin: 0;
        font-family:
          system-ui,
          -apple-system,
          "Segoe UI",
          Roboto,
          "Noto Sans TC",
          sans-serif;
        line-height: 1.7;
        background-color: #faf9f6;
        color: #1a2238;
      }

      .page {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
      }

      .container {
        width: 100%;
        max-width: 1100px;
        margin: 0 auto;
        padding: 1.5rem 1rem;
      }

      img {
        max-width: 100%;
        height: auto;
        display: block;
        border-radius: 0.5rem;
      }

      .section {
        padding-top: 3.5rem;
        padding-bottom: 3.5rem;
      }

      .section-title {
        font-size: 1.6rem;
        margin-bottom: 1rem;
        border-bottom: 2px solid #e7d192;
        display: inline-block;
        padding-bottom: 0.25rem;
      }

      p {
        margin-bottom: 1rem;
      }

      .site-header {
        position: sticky;
        top: 0;
        background-color: #1a2238;
        color: #ffffff;
        z-index: 1000;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.15);
      }

      .nav {
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
      }

      .logo {
        font-weight: 600;
        font-size: 1rem;
        letter-spacing: 0.05em;
      }

      .nav-links {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
      }

      .nav-link {
        color: #ffffff;
        text-decoration: none;
        padding: 0.4rem 0.6rem;
        border-bottom: 2px solid transparent;
        transition: border-color 0.2s ease;
      }

      .nav-link:hover {
        border-color: #8b9467;
      }

      footer {
        margin-top: auto;
        background-color: #1a2238;
        color: #ffffff;
        text-align: center;
        padding: 1.5rem 1rem;
        font-size: 0.9rem;
      }

      a {
        color: #8b9467;
      }

      a:hover {
      }

      /* ===============================
           CSS:BASE-END
        =============================== */

      /* ===============================
           CSS:HERO-START
        =============================== */

      .section-hero {
        background-color: #ffffff;
      }

      .hero-layout {
        display: flex;
        flex-direction: column;
        gap: 1.5rem;
      }

      .hero-title {
        font-size: 1.9rem;
        margin-bottom: 0.75rem;
      }

      .hero-note {
        font-size: 0.95rem;
        color: #555555;
        background-color: #f1f1ec;
        padding: 0.75rem;
        border-left: 4px solid #8b9467;
      }

      /* ===============================
           CSS:HERO-END
        =============================== */

      /* ===============================
           CSS:ABOUT-START
        =============================== */

      .section-about {
        background-color: #faf9f6;
      }

      .about-layout {
        display: flex;
        flex-direction: column;
        gap: 2rem;
      }

      .about-text {
        display: flex;
        flex-direction: column;
      }

      .about-highlights {
        margin-top: 1rem;
        padding-left: 1.2rem;
      }

      .about-highlights li {
        margin-bottom: 0.5rem;
      }

      .about-actions {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
        margin-top: 1.25rem;
      }

      .about-button {
        text-decoration: none;
        padding: 0.5rem 0.9rem;
        border-radius: 0.35rem;
        font-size: 0.95rem;
        border: 1px solid #8b9467;
        color: #1a2238;
        transition: background-color 0.2s ease;
      }

      .about-button-primary {
        background-color: #8b9467;
        color: #ffffff;
      }

      .about-button-primary:hover {
        background-color: #737c55;
      }

      .about-button-secondary:hover {
        background-color: #f1f1ec;
      }

      /* ===============================
           CSS:ABOUT-END
        =============================== */

      /* ===============================
           CSS:SKILLS-START
        =============================== */

      .section-skills {
        background-color: #ffffff;
      }

      .skills-layout {
        display: flex;
        flex-direction: column;
        gap: 2rem;
      }

      .skills-text {
        display: flex;
        flex-direction: column;
      }

      .skills-list {
        padding-left: 1.2rem;
      }

      .skills-list li {
        margin-bottom: 0.75rem;
      }

      .skills-actions {
        display: flex;
        flex-wrap: wrap;
        gap: 0.75rem;
        margin-top: 1.25rem;
      }

      .skills-button {
        text-decoration: none;
        padding: 0.5rem 0.9rem;
        border-radius: 0.35rem;
        font-size: 0.95rem;
        border: 1px solid #8b9467;
        color: #1a2238;
        transition: background-color 0.2s ease;
      }

      .skills-button-primary {
        background-color: #8b9467;
        color: #ffffff;
      }

      .skills-button-primary:hover {
        background-color: #737c55;
      }

      .skills-button-secondary:hover {
        background-color: #f1f1ec;
      }

      /* ===============================
           CSS:SKILLS-END
        =============================== */

      /* ===============================
           CSS:PROJECTS-START
        =============================== */

      .section-projects {
        background-color: #faf9f6;
      }

      .projects-note {
        font-size: 0.95rem;
        color: #555555;
        background-color: #f1f1ec;
        padding: 0.75rem;
        border-left: 4px solid #8b9467;
      }

      /* ===============================
           CSS:PROJECTS-END
        =============================== */

      /* ===============================
           CSS:CONTACT-START
        =============================== */

      .section-contact {
        background-color: #ffffff;
      }

      .contact-list {
        list-style: none;
        padding: 0;
        margin: 1rem 0;
      }

      .contact-list li {
        margin-bottom: 0.5rem;
      }

      .contact-note {
        font-size: 0.95rem;
        color: #555555;
        background-color: #f1f1ec;
        padding: 0.75rem;
        border-left: 4px solid #8b9467;
      }

      /* ===============================
           CSS:CONTACT-END
        =============================== */

      /* ===============================
           CSS:RWD-START
        =============================== */

      @media (min-width: 768px) {
        .hero-layout {
          flex-direction: row;
          align-items: center;
        }

        .about-layout {
          flex-direction: row;
          align-items: center;
        }

        .skills-layout {
          flex-direction: row;
          align-items: center;
        }

        .hero-text,
        .hero-image,
        .about-text,
        .about-image,
        .skills-text,
        .skills-image {
          flex: 1;
        }

        .nav {
          flex-wrap: nowrap;
        }

        .nav-links {
          gap: 1.25rem;
        }

        .section {
          padding-top: 4.5rem;
          padding-bottom: 4.5rem;
        }
      }

      @media (min-width: 1440px) {
        .container {
          max-width: 1200px;
        }

        .hero-title {
          font-size: 2.3rem;
        }
      }

      /* ===============================
           CSS:RWD-END
        =============================== */
    </style>

  </head>

  <body>
    <div class="page">
      <header class="site-header">
        <div class="container nav">
          <div class="logo">晨光步調· Life & Craft</div>

          <nav class="nav-links" aria-label="主導覽列">
            <a class="nav-link" href="#hero">序幕</a>
            <a class="nav-link" href="#about">靈魂</a>
            <a class="nav-link" href="#skills">維度</a>
            <a class="nav-link" href="#projects">軌跡</a>
            <a class="nav-link" href="#contact">交流</a>
          </nav>
        </div>
      </header>

      <main>
        <!-- SECTION:HERO-START -->
        <section id="hero" class="section section-hero">
          <div class="container hero-layout">
            <div class="hero-text">
              <h1 class="hero-title">序幕 (Prologue) </h1>

              <p>
                生活在不同的維度間擺盪，在秩序中尋找詩意，在多元中安放靈魂。
              </p>

              <p>
                從螢幕上閃爍的程式碼，到指尖流淌的小提琴聲；從居家空間的實體修繕，到平面設計的感性轉譯。
              </p>

              <p class="hero-note">
                「在秩序中構築邏輯，在微光中拉奏詩意。」</br> Crafting order through logic, bowing poetry through light.
              </p>
            </div>

            <div class="hero-image">
              <img
                src="https://images.unsplash.com/photo-1465821185615-20b3c2fbf41b"
                alt="一位創作者在整潔的桌面前使用筆電與筆記本工作的日常畫面"
                loading="lazy"
              />
            </div>
          </div>
        </section>
        <!-- SECTION:HERO-END -->

        <!-- SECTION:ABOUT-START -->
        <section
          id="about"
          class="section section-about"
          aria-labelledby="about-heading"
        >
          <div class="container about-layout">
            <div class="about-text">
              <h2 id="about-heading" class="section-title">
                靈魂(Soul) - 關於我
              </h2>

              <p>
                當下的交織－在0與1的數位脈動裡，建構邏輯秩序；在琴弦的震動之間，尋找情感出口。提供程式開發、視覺設計與生活修繕的專業諮詢。
              </p>

              <p>
                生活不是一條直線，而是一場多維度的實踐 ————帶著職人精神感受世界，在各種角色切換中收穫最豐盛的喜悅。
              </p>

              <ul class="about-highlights">
                <li>跨維度的問題解決 (Versatile Problem Solving)</li>
                <li>理性與感性的視覺轉譯 (Aesthetic Logic)</li>
                <li>強韌的身心紀律 (Disciplined Vitality)</li>
              </ul>

              <div class="about-actions">
                <a class="about-button about-button-primary" href="#projects">
                  查看軌跡
                </a>

                <a class="about-button about-button-secondary" href="#contact">
                  與我交流
                </a>
              </div>
            </div>

            <div class="about-image">
              <img
                src="https://images.unsplash.com/photo-1477764864052-f721644f01a8"
                alt="一位專注演奏小提琴的職人形象，象徵理性與感性並存的專業精神"
                loading="lazy"
              />
            </div>
          </div>
        </section>
        <!-- SECTION:ABOUT-END -->

        <!-- SECTION:SKILLS-START -->
        <section
          id="skills"
          class="section section-skills"
          aria-labelledby="skills-heading"
        >
          <div class="container skills-layout">
            <div class="skills-text">
              <h2 id="skills-heading" class="section-title">
                維度(Demenssions) - 技能樹
              </h2>

              <ul class="skills-list">
                <li>
                  <strong>程式設計 (Code & Logic)：</strong>
                  在 0 與 1 的純粹秩序中，我以優雅的代碼建構數位世界的骨架，讓複雜的功能轉化為流暢的人機對話。
                </li>

                <li>
                  <strong>小提琴家教 (Strings & Soul)：</strong>
                  小提琴是感性的出口。在音準的嚴謹要求下，我學會了傾聽細微的震動，將情感注入每一段悠揚的旋律。
                </li>

                <li>
                  <strong>平面設計 (Design & Vision)：</strong>
                  設計是理性的溝通。我運用色彩與排版，將紛雜的資訊過濾成乾淨、直覺且具美感的視覺語言。
                </li>

                <li>
                  <strong>室內配線 (Craft & Flow)：</strong>
                  當水電管線回歸順暢，生活便重新流動。我享受雙手修復實體的踏實感，那是工程師對物理世界的溫柔照護。
                </li>

                <li>
                  <strong>健身教練 (Strength & Vitality)：</strong>
                  健身是身體的精密工程。透過科學的訓練與律己，我教導身體如何在穩定中發力，練就應對挑戰的強韌身心。
                </li>
              </ul>

              <div class="skills-actions">
                <a class="skills-button skills-button-primary" href="#projects">
                  查看軌跡
                </a>

                <a class="skills-button skills-button-secondary" href="#contact">
                  與我交流
                </a>
              </div>
            </div>

            <div class="skills-image">
              <img
                src="https://images.unsplash.com/photo-1581092335397-9583eb92d232"
                alt="一位專注工作的職人形象，象徵技能、專業與身體力行的實踐精神"
                loading="lazy"
              />
            </div>
          </div>
        </section>
        <!-- SECTION:SKILLS-END -->

        <!-- SECTION:PROJECTS-START -->
        <section
          id="projects"
          class="section section-projects"
          aria-labelledby="projects-heading"
        >
          <div class="container">
            <h2 id="projects-heading" class="section-title">
              作品與軌跡（之後會用 Section SDD 替換）
            </h2>

            <p>
              這裡目前是 Projects 區的占位內容，
              未來會展示你的代表作品、專案案例或人生重要里程碑，
              並附上圖片與說明。
            </p>

            <p class="projects-note">
              之後會用 Section SDD 的 Prompt 產生新的 section， 請把新的 section
              程式碼整段貼在這兩個註解中間， 完全取代現在這一區。
            </p>
          </div>
        </section>
        <!-- SECTION:PROJECTS-END -->

        <!-- SECTION:CONTACT-START -->
        <section
          id="contact"
          class="section section-contact"
          aria-labelledby="contact-heading"
        >
          <div class="container">
            <h2 id="contact-heading" class="section-title">
              聯絡與交流（之後會用 Section SDD 替換）
            </h2>

            <p>
              這裡目前是 Contact 區的占位內容， 未來會放上
              Email、電話、社群連結或合作邀請資訊。
            </p>

            <ul class="contact-list">
              <li>
                電子郵件：
                <a href="mailto:hello@example.com"> hello@example.com </a>
              </li>
              <li>
                聯絡電話：
                <a href="tel:+886900000000"> +886 900-000-000 </a>
              </li>
              <li>
                GitHub：
                <a href="https://github.com/yourname">
                  https://github.com/yourname
                </a>
              </li>
              <li>
                LinkedIn：
                <a href="https://www.linkedin.com/in/yourname">
                  https://www.linkedin.com/in/yourname
                </a>
              </li>
            </ul>

            <p class="contact-note">
              之後會用 Section SDD 的 Prompt 產生新的 section， 請把新的 section
              程式碼整段貼在這兩個註解中間， 完全取代現在這一區。
            </p>
          </div>
        </section>
        <!-- SECTION:CONTACT-END -->
      </main>

      <footer>
        <div class="container">
          © 2026 Quiet Rhythm · Life & Craft
          ｜在穩定的節奏裡，慢慢完成自己的人生作品。
        </div>
      </footer>
    </div>

  </body>
</html>
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
