# 【Phase 1 】建立個人網站骨架

（單一 index.html，嚴禁 JS ＋使用 Unsplash 圖庫＋HTML/CSS 皆預留插槽＋CSS 禁用 ID 選擇器）

你現在是一位「前端工程師＋教練」，  
任務是幫我建立一個個人網站的「環境與骨架」，全部寫在單一 index.html 檔案裡，並且要幫開發者預留好「HTML 區塊插槽」與「CSS 區塊插槽」，方便之後用其他 Prompt 來替換。

請依照以下所有規格，產出一個完整的 index.html。

━━━━━━━━━━━━━━━━━━

# 全站環境規格書 v1.0

一、技術限制（必須嚴格遵守）

1. 僅能使用 HTML + CSS：
   - 禁止任何 JavaScript。
   - 不可以出現：
     - <script> 標籤
     - 任何 onclick、onchange 等事件屬性
     - 任何 addEventListener、console.log 或其他 JS 語法。

2. 禁止外部資源：
   - 不可以使用 <link rel="stylesheet">。
   - 不可以使用任何外部 JS 或 CSS CDN（包含 Google Fonts、Bootstrap 等）。

3. CSS 必須全部寫在 <head> 裡「單一的」 style 標籤內。

4. 語系與文字：
   - <html lang="zh-Hant">
   - 內容全部使用繁體中文（台灣用語）。

5. RWD 策略：
   - 採用手機優先（mobile-first）。
   - 保證在 320px、768px、1440px 寬度下不會產生水平捲動（依照你的 CSS 設計推估）。

6. 不要向我提問：
   - 不可以要求我補資料或確認。
   - 如有不明確處，請你自行填入合理預設值並直接產出結果。

7. CSS 禁用 ID 選擇器（非常重要）：
   - 在整份 CSS 中「禁止」使用任何 ID 選擇器（例如 #hero、#about 等）。
   - 所有樣式請一律使用：
     - 元素選擇器（例如 body、img）
     - 類別選擇器（例如 .section-hero、 .nav-link）
     - 或巢狀組合（例如 .section-hero h1）
   - HTML 中仍可使用 id 作為錨點，但只能掛在元素上（例如 <section id="hero" …>），且只用在 href="#hero" 這類跳轉。

━━━━━━━━━━━━━━━━━━
二、輸出格式規定（非常重要）

1. 只輸出「一個完整的 index.html 檔案內容」。
2. 必須是合法的 HTML 文件結構，包含：
   - <!DOCTYPE html>
   - <html lang="zh-Hant">
   - <head> … </head>
   - <body> … </body>

━━━━━━━━━━━━━━━━━━
三、專案資訊與網站結構

1. 專案基本資訊
   - 網站名稱（左上角 Logo 文字）：請幫我取一個中性、適合斜槓個人品牌的名稱，例如「Your Name · Joyful Life」。
   - 網站用途：個人品牌網站，用來：
     - 介紹自己
     - 展示技能
     - 放上作品集
     - 提供聯絡方式

2. 網站主要區塊與錨點名稱

   導覽列會透過 href="#hero" 這種方式捲動到對應區塊。  
   錨點 id 名稱固定如下，**請直接掛在 section 上**：
   - Hero 區 → <section id="hero" …>
   - About 區 → <section id="about" …>
   - Skills 區 → <section id="skills" …>
   - Projects 區 → <section id="projects" …>
   - Contact 區 → <section id="contact" …>

   同時在 section 上加上語意化的 class，例如：
   - class="section section-hero"
   - class="section section-about"
   - class="section section-skills"
   - class="section section-projects"
   - class="section section-contact"

   CSS 只能使用 class（例如 .section-hero），不能寫 #hero。

3. <body> 建議結構：

   <body>
     <div class="page">
       <header>…導覽列…</header>
       <main>
         …Hero / About / Skills / Projects / Contact…
       </main>
       <footer>…版權資訊…</footer>
     </div>
   </body>

━━━━━━━━━━━━━━━━━━
四、導覽列 Nav 規格

1. 導覽列內容：
   - 左側：網站名稱（純文字 Logo）。
   - 右側：導覽連結項目（使用 <a>），對應各區塊。

2. 導覽連結規則（href 必須是錨點，不可以是 # 或空字串）：
   - 序幕 → href="#hero"
   - 靈魂 → href="#about"
   - 維度 → href="#skills"
   - 軌跡 → href="#projects"
   - 交流 → href="#contact"

3. 樣式建議（CSS 使用 class，禁止用 ID）：
   - header 使用 .site-header。
   - 導覽列容器用 .nav。
   - 連結使用 .nav-link。
   - 導覽列固定在頁面頂部（position: sticky; top: 0）。
   - 有簡單的背景色與底線或陰影，方便與內容區分。

━━━━━━━━━━━━━━━━━━
五、風格方向（骨架階段）

1. 整體風格關鍵字：
   - 乾淨、簡單、詩意穩定系(Visual Harmony)。

2. 顏色設定：
   - 主色：請選擇「午夜深藍(Midnight Blue) #1A2238 」，比純黑更深邃更有故事感，代表理性穩定的情緒。
   - 點綴色(用在重點元素:按鈕、標題強調、連結 hover 等)：請選擇「灰橄欖綠(Olive Tint) #8b9467:平靜充滿生命力」 以及 「香檳金 #E7d192:象徵生命中點綴的喜悅和光芒，僅用於極小細節（如底線、邊框）」。
   - 背景：以亞麻白 (linen White) #FAF9F6 為主，像是一張未經漂白的畫紙，溫潤不刺眼，給人極大的包容感。

3. 排版：
   - 使用系統字型（system UI 字型族）。
   - 行距偏舒適，適合閱讀履歷與作品描述。
   - 適當留白

━━━━━━━━━━━━━━━━━━
六、各 Section 的「占位內容」要求

之後會用第二階段「Section SDD」針對單一區塊產生正式內容。  
Phase 1 只需要「清楚的占位內容」，但要讓開發者看得懂「之後會被替換」。

1. Hero 區（section id="hero" class="section section-hero"）
   - 結構示意：
     <section id="hero" class="section section-hero">
       …Hero 區內容…
     </section>
   - 必須包含全站唯一的一個 h1。
   - 內容建議：
     - 一個簡短主標題（說明這是個人網站的主視覺區）。
     - 1～2 段 <p> 說明未來會放：
       - 一句話自我介紹Slogan(例如 在秩序中尋找詩意，在多元中安放靈魂 Finding poetry in order, placing the soul in diversity.)
       - 核心職稱 / 角色（例如 A Lover Of Life）
       - 行動呼籲（例如 瀏覽作品集、下載履歷）
     - 一句提示文字給開發者：
       「之後會用 Section SDD 的 Prompt 產生正式文案與版面，再把整個 section 貼回來取代這一區。」

2. About / Skills / Projects / Contact 區
   - 每個區塊至少需要：
     - 一個 h2 作為區塊主標。
     - 一到兩段 p 說明：
       - 這裡目前是占位內容。
       - 未來會用 Section SDD 產生更完整的內容。
       - 開發者要把新的 section 程式碼「整段」貼回來，覆蓋註解之間的內容。

   - 結構示意（以 About 為例）：

```
     <section id="about" class="section section-about" aria-labelledby="about-heading">
       <div class="container">
         <h2 id="about-heading" class="section-title">關於我（之後會用 Section SDD 替換）</h2>
         <p>這裡目前是 About 區的占位內容，之後會用另一個 Prompt 產生正式內容，請把新的 section 程式碼整段貼回來，取代這一區。</p>
       </div>
     </section>

   - Skills / Projects / Contact 可使用類似 class 命名：
     - <section id="skills"   class="section section-skills">
     - <section id="projects" class="section section-projects">
     - <section id="contact"  class="section section-contact">
```

━━━━━━━━━━━━━━━━━━
七、HTML 區塊插槽規則（Section HTML Slot，簡版）

目的：讓開發者之後可以「整段替換某一個區塊」，而不用思考要貼到哪裡。

1. 每個主要區塊都要有一組固定格式的註解插槽，放在 <main> 裡，名稱固定為：
   - Hero 區：SECTION:HERO-START / SECTION:HERO-END
   - About 區：SECTION:ABOUT-START / SECTION:ABOUT-END
   - Skills 區：SECTION:SKILLS-START / SECTION:SKILLS-END
   - Projects 區：SECTION:PROJECTS-START / SECTION:PROJECTS-END
   - Contact 區：SECTION:CONTACT-START / SECTION:CONTACT-END

2. 每一區的 HTML 結構統一為「註解包住一整個 section」，示意：

   Hero 區：
   <!-- SECTION:HERO-START -->
   <section id="hero" class="section section-hero">
     …Hero 區占位內容…
   </section>
   <!-- SECTION:HERO-END -->

   About 區：
   <!-- SECTION:ABOUT-START -->
   <section id="about" class="section section-about" aria-labelledby="about-heading">
     …About 區占位內容…
   </section>
   <!-- SECTION:ABOUT-END -->

   Skills / Projects / Contact 比照辦理，只需對應修改：
   - 註解名稱：SECTION:SKILLS / SECTION:PROJECTS / SECTION:CONTACT
   - section 的 id：skills / projects / contact
   - section 的 class：section-skills / section-projects / section-contact

3. 請在各區占位文字中，用一句話明講給開發者聽：
   「之後會用 Section SDD 的 Prompt 產生新的 section，請把新的 section 程式碼整段貼在這兩個註解中間，完全取代現在這一區。」

━━━━━━━━━━━━━━━━━━
八、CSS 區塊插槽規則（CSS Slot，簡版＋禁止用 ID 選擇器）

目的：讓之後的 Prompt 可以「只針對某一區 CSS 做覆蓋」，同時維持 class-based 的寫法。

請在 head 裡的 style 中，用 CSS 註解切出以下 7 個區塊，名稱要固定不變，且區塊內只能使用元素 / class 選擇器，不能使用任何 #id：

1. 全站基底樣式（CSS:BASE）

   /_ CSS:BASE-START _/
   …全站共用設定（box-sizing、body、.page、.container、img 等）…
   /_ CSS:BASE-END _/

2. Hero 區樣式（CSS:HERO）

   /_ CSS:HERO-START _/
   …所有與 Hero 區相關的樣式，例如 .section-hero、.hero-title…
   /_ CSS:HERO-END _/

3. About 區樣式（CSS:ABOUT）

   /_ CSS:ABOUT-START _/
   …所有與 About 區相關的樣式，例如 .section-about…
   /_ CSS:ABOUT-END _/

4. Skills 區樣式（CSS:SKILLS）

   /_ CSS:SKILLS-START _/
   …所有與 Skills 區相關的樣式，例如 .section-skills、.skill-list…
   /_ CSS:SKILLS-END _/

5. Projects 區樣式（CSS:PROJECTS）

   /_ CSS:PROJECTS-START _/
   …所有與 Projects 區相關的樣式，例如 .section-projects、.project-card…
   /_ CSS:PROJECTS-END _/

6. Contact 區樣式（CSS:CONTACT）

   /_ CSS:CONTACT-START _/
   …所有與 Contact 區相關的樣式，例如 .section-contact、.contact-list…
   /_ CSS:CONTACT-END _/

7. RWD 媒體查詢（CSS:RWD）

   /_ CSS:RWD-START _/
   …至少一個 @media (min-width: 768px) {...} 之類的手機優先 RWD 設定…
   /_ CSS:RWD-END _/

再次強調：在這 7 個 Slot 裡的任何 CSS 選擇器，都不可以使用「#something」，一律改用 class。

━━━━━━━━━━━━━━━━━━
九、SEO 與結構規則

1. 基本結構：
   - 必須包含 <!DOCTYPE html>。
   - 必須有 <html>、<head>、<body>，巢狀正確。
   - <html> 必須帶有 lang="zh-Hant"。

2. <head> 內必須包含：
      - meta charset="UTF-8"
      - meta name="viewport" content="width=device-width, initial-scale=1.0"
      - 一個非空的 title，內容與「個人品牌網站」相關。
     - 一個 meta name="description" content="..."
    - content 長度約 50～160 個字元。
    - 使用自然的繁體中文描述：這是用來介紹個人背景、技能、作品集與聯絡方式的網站。

3. 標題層級：
   - 全站只能有一個 h1（在 Hero 區）。
   - 其他區塊主標使用 h2。
   - 如有需要，可以在區塊內使用 h3 作為小標題，但不要過度複雜。

4. 連結規則（這裡要特別注意 href 合法性）：
   - 所有 <a> 的 href 必須是「非空」且「不是單純的 #」：
     - 錨點連結一律使用明確 id，例如 href="#hero"、href="#about"。
     - 導覽列全部使用這種錨點寫法。
   - 其他類型連結也必須給出合理的 href，不可以留空或寫成 #，例如：
     - Email：href="mailto:hello@example.com"
     - 電話：href="tel:+886900000000"
     - GitHub：href="https://github.com/yourname"
     - LinkedIn：href="https://www.linkedin.com/in/yourname"
   - 不可以使用 javascript: 開頭或任何明顯無效的 href。

━━━━━━━━━━━━━━━━━━
十、圖片規則（必須使用 Unsplash 圖庫）

1. 所有 <img> 的 src 必須來自 Unsplash，例如：
   - https://images.unsplash.com/...
   - 或 https://source.unsplash.com/800x600/?aesthetic,workspace,zenlife 之類的關鍵字 URL。

2. 每一個 <img> 必須：
   - 有非空的 alt 文字，描述圖片內容（例如：「陽光灑在小提琴上的局部照、健身時揮汗後的微距照、手握板手修理東西時旁邊放著咖啡杯的日常畫面」）。
   - 建議加上 loading="lazy"。
   - 在 CSS 中適用：
     - img { max-width: 100%; height: auto; display: block; }

3. 建議在 Hero 或 About 區放一張示意形象照（開發者、筆電、辦公桌相關）。

━━━━━━━━━━━━━━━━━━
十一、RWD 具體要求

1. 手機優先：
   - 預設樣式以小螢幕（320px）為基準。
   - 各區塊預設為單欄排版。

2. 在寬度較大（例如 min-width: 768px）時：
   - 可以將 About 或 Projects 改成左右雙欄。
   - 但仍須避免水平捲動。

3. 建議設定：
   - body { margin: 0; }
   - 統一使用 .container 控制內容最大寬度與左右 padding。

━━━━━━━━━━━━━━━━━━
十二、自我檢查清單（請在產出前自行確認，含插槽與 href）

1. 結構與 SEO

- [ ] 有 <!DOCTYPE html>、<html lang="zh-Hant">、<head>、<body>。
- [ ] <meta charset> 與 <meta name="viewport"> 已設定。
- [ ] 有 <title> 與 <meta name="description">，描述長度約 50～160 字元。
- [ ] 全站只有一個 <h1>，在 Hero 區。

2. 連結與圖片

- [ ] 所有 <a> 的 href 都是非空、不是 #：- 導覽列用 href="#hero" 這類錨點。- 其他連結（GitHub / Email / LinkedIn 等）使用 mailto:、tel: 或完整 https URL。
- [ ] 所有 <img> 來源皆為 Unsplash，且有合理的 alt 文本。
- [ ] 圖片有透過 CSS 保證不會造成水平捲動。

3. HTML 插槽（Section Slot）

- [ ] <main> 裡的 Hero / About / Skills / Projects / Contact 各有一組 SECTION:XXX-START / SECTION:XXX-END 註解。
- [ ] 每組註解中間包住「一整個 section」，且 section 自身帶有對應的 id（hero / about / skills / projects / contact）。
- [ ] 各占位區塊文字都有清楚寫出：之後會用 Section SDD 產生新的 section，請開發者「整段貼在兩個註解中間」來替換。

4. CSS 插槽（CSS Slot）

- [ ] <style> 裡有 CSS:BASE / CSS:HERO / CSS:ABOUT / CSS:SKILLS / CSS:PROJECTS / CSS:CONTACT / CSS:RWD 等註解區塊。
- [ ] 各區塊內的選擇器皆使用元素或 class，不使用 ID。

5. CSS 禁用 ID 選擇器

- [ ] 確認整份 CSS 沒有任何 #xxx 選擇器。
- [ ] 所有區塊樣式都以 .section-hero、.section-about 等 class 為主。

6. 版面與 RWD

- [ ] 採用手機優先設計，在 320px、768px、1440px 寬度下理論上不會水平捲動。
- [ ] 各區塊有清楚的占位文案，提醒未來會用 Section SDD 來替換。
