# 旅遊日誌 HTML 生成指南

## 專案概述
本專案使用HTML5 UP的Story模板來創建精美的旅遊日誌網頁，將您的旅行記錄轉換為視覺豐富的單頁滾動網站。Story模板特別適合時間軸敘述、照片展示和故事講述，提供響應式設計和優秀的行動裝置瀏覽體驗。

## 工作流程

### Markdown到旅遊日誌HTML轉換流程
本專案支援從旅遊日誌Markdown檔案自動生成滾動式HTML網頁的工作流程：

1. **準備旅遊日誌Markdown檔案** - 包含旅行日期、地點、活動記錄和照片
2. **內容解析與時間軸規劃** - 將旅行記錄按時間順序對應到Story模板組件
3. **元素選擇與配置** - 從story-temp資源中選擇合適的展示組件
4. **HTML生成與視覺優化** - 生成最終的旅遊日誌HTML網頁
5. **響應式測試與調整** - 確保在各種裝置上的最佳瀏覽效果

### 協作方式
- 您提供結構化的旅遊日誌Markdown檔案（含照片路徑）
- Claude分析旅行內容並建議最適合的Story組件配置
- 自動生成對應的旅遊日誌HTML代碼
- 支援照片展示、時間軸敘述和互動功能優化

## 可用資源

### 模板檔案
- `story-temp/index.html` - 主要模板檔案
- `story-temp/index-demo.html` - 互動式組件展示頁面（僅供學習參考）

### 樣式資源
- `story-temp/assets/css/main.css` - 編譯後的主要樣式
- `story-temp/assets/css/noscript.css` - 無JavaScript時的樣式
- `story-temp/assets/sass/` - SASS源碼檔案
  - `main.scss` - 主樣式檔案
  - `base/` - 基礎樣式（重置、字體、頁面）
  - `components/` - 元件樣式（banner、spotlight、gallery等）
  - `layout/` - 佈局樣式（wrapper等）

### JavaScript功能
- `story-temp/assets/js/main.js` - 主要互動功能
- `story-temp/assets/js/jquery.min.js` - jQuery庫
- `story-temp/assets/js/jquery.scrollex.min.js` - 滾動效果庫
- `story-temp/assets/js/jquery.scrolly.min.js` - 平滑滾動
- `story-temp/assets/js/browser.min.js` - 瀏覽器相容性
- `story-temp/assets/js/breakpoints.min.js` - 響應式斷點
- `story-temp/assets/js/util.js` - 工具函數

### 圖片資源
- `story-temp/images/` - 示例圖片
  - `banner.jpg` - 橫幅封面圖片
  - `spotlight01.jpg ~ spotlight03.jpg` - 重點展示圖片
  - `pic01.jpg ~ pic03.jpg` - 一般內容圖片
  - `gallery/` - 畫廊圖片資料夾
    - `fulls/` - 完整尺寸圖片（01.jpg ~ 12.jpg）
    - `thumbs/` - 縮圖（01.jpg ~ 12.jpg）

### 字體資源
- `story-temp/assets/webfonts/` - FontAwesome圖示字體檔案

## 旅遊日誌架構建議

### 1. 旅程封面結構
```html
<!-- Banner區域 - 作為旅程封面 -->
<section class="banner style1 orient-left content-align-left image-position-right fullscreen onload-image-fade-in onload-content-fade-right">
    <div class="content">
        <h1>旅行標題</h1>
        <p class="major">旅行時間和地點概述</p>
        <p>旅行摘要，包含主要亮點和感想...</p>
        <ul class="actions stacked">
            <li><a href="#first" class="button big wide smooth-scroll-middle">開始探索</a></li>
        </ul>
    </div>
    <div class="image">
        <img src="cover-trip.jpg" alt="旅程封面圖片" />
    </div>
</section>
```

### 2. 每日行程展示
```html
<!-- Spotlight區域 - 展示每日重點行程 -->
<section class="spotlight style1 orient-right content-align-left image-position-center onscroll-image-fade-in">
    <div class="content">
        <h2>第一天：抵達與探索</h2>
        <p>詳細描述當天的行程、體驗和感受...</p>
        <ul class="actions stacked">
            <li><a href="#" class="button">查看更多照片</a></li>
        </ul>
    </div>
    <div class="image">
        <img src="day1-highlight.jpg" alt="第一天重點照片" />
    </div>
</section>
```

### 3. 照片畫廊展示
```html
<!-- Gallery區域 - 旅行照片集錦 -->
<section class="wrapper style1 align-center">
    <div class="inner">
        <h2>精彩瞬間</h2>
        <p>旅程中捕捉的美好回憶...</p>
    </div>
    <div class="gallery style2 medium lightbox onscroll-fade-in">
        <article>
            <a href="images/gallery/fulls/01.jpg" class="image">
                <img src="images/gallery/thumbs/01.jpg" alt="景點照片" />
            </a>
            <div class="caption">
                <h3>景點名稱</h3>
                <p>照片描述和拍攝背景</p>
            </div>
        </article>
    </div>
</section>
```

### 4. 旅行亮點統計
```html
<!-- Items Grid區域 - 旅行統計和亮點 -->
<section class="wrapper style1 align-center">
    <div class="inner">
        <h2>旅行統計</h2>
        <div class="items style1 medium onscroll-fade-in">
            <section>
                <span class="icon style2 major fa-map-marker-alt"></span>
                <h3>造訪城市</h3>
                <p>5個城市</p>
            </section>
            <section>
                <span class="icon solid style2 major fa-camera"></span>
                <h3>拍攝照片</h3>
                <p>300+張照片</p>
            </section>
        </div>
    </div>
</section>
```

## 旅遊日誌專用樣式自定義

### 1. 時間軸導航效果
添加滾動進度指示器：
```css
/* 滾動進度條 */
.progress-bar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    background: rgba(255,255,255,0.1);
    z-index: 10000;
}

.progress-bar .progress {
    height: 100%;
    background: linear-gradient(to right, #ff6b6b, #4ecdc4);
    transition: width 0.3s ease;
}
```

### 2. 旅行日期標記
為每個 spotlight 區塊添加日期標籤：
```css
.spotlight .content::before {
    content: attr(data-date);
    display: inline-block;
    background: #ff6b6b;
    color: white;
    padding: 0.5rem 1rem;
    border-radius: 2rem;
    font-size: 0.8rem;
    margin-bottom: 1rem;
}
```

### 3. 照片懸停效果增強
```css
.gallery .image img {
    transition: transform 0.3s ease, filter 0.3s ease;
}

.gallery .image:hover img {
    transform: scale(1.05);
    filter: brightness(1.1);
}
```

### 4. 地圖區域樣式
```html
<!-- 旅行路線地圖 -->
<section class="wrapper style1 align-center">
    <div class="inner">
        <h2>旅行路線</h2>
        <div class="map-container">
            <iframe src="https://www.google.com/maps/embed?pb=..." 
                    width="100%" height="400" style="border:0;" 
                    allowfullscreen="" loading="lazy">
            </iframe>
        </div>
    </div>
</section>
```

## 互動功能增強

### 1. 滾動進度顯示
添加旅程閱讀進度指示：
```javascript
// 滾動進度計算
$(window).scroll(function() {
    var scrolled = ($(window).scrollTop() / ($(document).height() - $(window).height())) * 100;
    $('.progress').css('width', scrolled + '%');
});
```

### 2. 平滑滾動導航
Story模板內建平滑滾動，可額外加強：
```javascript
// 增強滾動體驗
$('a[href^="#"]').on('click', function(e) {
    e.preventDefault();
    var target = $(this.getAttribute('href'));
    if(target.length) {
        $('html, body').animate({
            scrollTop: target.offset().top - 50
        }, 800, 'easeInOutQuad');
    }
});
```

### 3. 照片懶載入
優化大量照片的載入效能：
```html
<!-- 使用 loading="lazy" 屬性 -->
<img src="day1-photo.jpg" loading="lazy" alt="第一天照片" />
```

### 4. 社群分享按鈕
```html
<!-- 添加分享功能 -->
<div class="share-buttons">
    <a href="#" onclick="shareToFacebook()">分享到 Facebook</a>
    <a href="#" onclick="shareToInstagram()">分享到 Instagram</a>
    <a href="#" onclick="copyLink()">複製連結</a>
</div>
```

## 旅遊日誌內容組織建議

### 1. 旅遊日誌結構範本
```
1. 旅程封面 (Banner) - 主標題、時間、封面照片
2. 旅行概況 (Spotlight) - 行程概述、交通、住宿
3. 每日記錄 (多個Spotlight) - 按日期順序展示
4. 精彩瞬間 (Gallery) - 照片集錦展示  
5. 旅行統計 (Items Grid) - 數據化回顧
6. 心得感想 (Wrapper) - 總結與推薦
7. 聯絡分享 (Contact) - 留言或社群連結
```

### 2. 內容層次結構
- 使用`<h1>`作為旅程主標題
- 使用`<h2>`作為每日標題（第X天：地點）
- 使用`<h3>`作為當日活動小標題
- 重要時刻使用引用格式突出顯示

### 3. 旅行照片使用建議
- 每日選擇1-2張代表性照片作為Spotlight展示
- 建立完整的Gallery展示旅程精華
- 封面使用最具代表性的美景照片
- 保持照片品質一致，建議統一濾鏡風格

## 部署和分享

### 1. 本地預覽
直接開啟旅遊日誌HTML檔案或設置本地伺服器：
```bash
# 使用Python簡單伺服器（推薦用於測試滾動效果）
python -m http.server 8000
# 或使用Node.js
npx serve .
# 或使用VS Code Live Server擴充功能
```

### 2. 網頁部署選項
- **GitHub Pages**：免費，適合公開分享旅遊日誌
- **Netlify**：快速部署，支援自訂網域
- **Vercel**：優秀的載入速度
- **Firebase Hosting**：Google服務整合

### 3. 分享方式
- **公開分享**：透過網址分享給朋友家人
- **私人分享**：打包為zip檔案私下傳送
- **社群媒體**：截圖重點內容分享到IG、FB
- **離線瀏覽**：所有資源本地化，支援離線觀看

## 客製化提示

### 1. 色彩主題調整
依據旅行風格調整配色：
```scss
// 在 story-temp/assets/sass/libs/_vars.scss 中修改
$color-accent: #ff6b6b;        // 海島風：珊瑚色
$color-accent: #4ecdc4;        // 清新風：薄荷綠  
$color-accent: #ffa726;        // 秋季風：橘黃色
```

### 2. 字體風格調整
在`story-temp/assets/sass/base/_typography.scss`中：
```scss
// 選擇適合的字體組合
body { font-family: 'Noto Sans TC', sans-serif; }  // 繁體中文優化
h1, h2, h3 { font-family: 'Playfair Display', serif; }  // 優雅標題字體
```

### 3. 載入動畫自訂
```css
/* 自訂進場動畫時間 */
.onscroll-fade-in { transition: opacity 0.8s ease; }
.onload-image-fade-in { transition: opacity 1.2s ease; }
```

## 常用旅遊日誌元素

### 1. 旅行亮點卡片
```html
<div class="box">
    <h3>🌸 最難忘時刻</h3>
    <p>在清水寺看到滿開的櫻花，那一刻真的覺得來日本值得了...</p>
</div>
```

### 2. 行程導航按鈕
```html
<ul class="actions stacked">
    <li><a href="#day2" class="button big wide smooth-scroll-middle">第二天行程</a></li>
</ul>
```

### 3. 照片說明格式
```html
<!-- Spotlight中的照片 -->
<div class="image">
    <img src="day1-temple.jpg" alt="淺草寺雷門" />
</div>

<!-- Gallery中的照片 -->
<article>
    <a href="gallery/fulls/01.jpg" class="image">
        <img src="gallery/thumbs/01.jpg" alt="東京塔夜景" />
    </a>
    <div class="caption">
        <h3>東京塔夜景</h3>
        <p>從六本木展望台拍攝的東京鐵塔，夜晚點燈後格外美麗</p>
    </div>
</article>
```

### 4. 實用資訊區塊
```html
<!-- 交通資訊 -->
<section>
    <h3>🚇 交通資訊</h3>
    <ul>
        <li><strong>機場到市區：</strong>成田特快N'EX，約1小時</li>
        <li><strong>市區交通：</strong>東京地鐵一日券 ¥800</li>
        <li><strong>推薦APP：</strong>Google Maps + 乘換案內</li>
    </ul>
</section>
```

## 旅遊日誌 Markdown 轉換指南

### 旅遊日誌 Markdown 檔案結構規範

#### 1. 基本結構
```markdown
# 日本關西深度遊
> 2024年春季賞櫻之旅 | 大阪·京都·奈良

<!-- trip-info -->
**旅行時間：** 2024年4月1日 - 4月7日  
**旅行天數：** 7天6夜  
**同行人數：** 2人  
**主要城市：** 大阪、京都、奈良

## 第一天：抵達大阪
<!-- day: 2024-04-01 -->
<!-- spotlight: right -->

今天終於踏上了期待已久的關西之旅！從桃園機場出發，經過2.5小時的飛行抵達關西機場。

### 今日亮點
- ✈️ 順利抵達關西機場
- 🏨 入住大阪市中心酒店
- 🍜 品嚐第一餐正宗日式拉麵

![大阪城夜景](day1-osaka-castle.jpg)

## 第二天：京都清水寺
<!-- day: 2024-04-02 -->
<!-- spotlight: left -->

清晨搭乘新幹線前往京都，漫步在清水寺的石階小徑上，感受千年古都的韻味。

### 今日行程
- 🚅 新幹線京都之旅
- ⛩️ 清水寺參拜賞櫻
- 🛍️ 三年坂二年坂購物

![清水寺櫻花](day2-kiyomizu.jpg)

## 精彩瞬間
<!-- gallery -->
### 旅程照片集錦

這次旅行拍攝了超過200張照片，以下是精選的美好瞬間：

![thumbnail](gallery/thumb01.jpg "大阪城櫻花滿開")|![fullsize](gallery/full01.jpg)
![thumbnail](gallery/thumb02.jpg "清水寺夜景")|![fullsize](gallery/full02.jpg)
![thumbnail](gallery/thumb03.jpg "奈良小鹿")|![fullsize](gallery/full03.jpg)

## 旅行統計
<!-- stats -->
### 這次旅行的數字記錄

- 📍 **造訪景點**：12個主要景點
- 📸 **拍攝照片**：200+張照片  
- 🚶 **步行距離**：平均每日8公里
- 🍽️ **品嚐美食**：15家特色餐廳
- 💰 **總花費**：NT$ 45,000
- ⭐ **滿意度**：★★★★★
```

#### 2. 特殊標記說明
- `<!-- trip-info -->` - 標記旅行基本資訊區塊
- `<!-- day: YYYY-MM-DD -->` - 指定日期，用於時間軸展示
- `<!-- spotlight: left/right -->` - 指定該日行程的展示方向
- `<!-- gallery -->` - 指定照片畫廊區塊
- `<!-- stats -->` - 指定統計資訊區塊

### 旅遊日誌元素對應表

| Markdown元素 | Story組件 | 使用場景 |
|-------------|----------|---------|
| `# 旅行標題` | Banner區塊 | 旅程封面、主標題 |
| `## 第X天：地點` | Spotlight區塊 | 每日行程展示 |
| `### 小標題` | 內容標題 | 當日重點活動 |
| `<!-- gallery -->` | Gallery組件 | 照片集錦展示 |
| `<!-- stats -->` | Items Grid | 旅行統計數據 |
| `![圖片](path)` | 各式圖片組件 | 照片展示 |
| `> 引用文字` | 引用樣式 | 重要感想、名言 |
| `**粗體**` | 強調文字 | 重點資訊 |
| `- 清單項目` | 行程列表 | 當日活動清單 |
| `連結` | 按鈕組件 | 導航、外部連結 |

### 自動轉換流程

#### 1. 內容解析階段
```
旅遊日誌解析 → 時間軸建構 → 內容分類 → 組件配置
```

#### 2. 組件對應邏輯
- **日期標記** → Spotlight區塊的順序和方向
- **照片內容** → Gallery組件或單張圖片展示
- **統計資料** → Items Grid視覺化展示
- **行程描述** → Spotlight內容區塊

#### 3. Claude輔助轉換
當您提供旅遊日誌Markdown檔案時，Claude會：
1. 分析旅行時間軸和日程安排
2. 識別照片資源和最佳展示方式
3. 建議適合的Story組件配置
4. 生成響應式的旅遊日誌HTML代碼
5. 優化行動裝置瀏覽體驗

### Story模板組件庫參考

#### 可用HTML組件清單

**主要佈局組件：**
- `Banner` - 旅程封面區塊（適合主標題和旅行概述）
- `Spotlight` - 每日行程區塊（支援左右交替展示）
- `Gallery` - 照片畫廊（支援燈箱效果）
- `Wrapper` - 一般內容包裝區塊

**功能性組件：**
- `Items Grid` - 統計資訊展示（適合旅行數據）
- `Contact Form` - 聯絡表單（適合留言或分享）
- `Actions` - 行動按鈕組（適合導航）

**特殊效果：**
- `onscroll-fade-in` - 滾動淡入動畫
- `onload-image-fade-in` - 圖片載入淡入
- `lightbox` - 照片燈箱效果
- `smooth-scroll` - 平滑滾動

### 旅遊日誌撰寫最佳實踐

#### 1. Markdown撰寫建議
- **時間順序**：按照旅行日期順序撰寫，使用「第X天」格式
- **圖片命名**：使用描述性檔名（如 `day1-osaka-castle.jpg`）
- **表情符號**：適度使用 emoji 增加視覺趣味性
- **內容平衡**：每日記錄包含行程、感想和照片

#### 2. 照片資源規劃
- **檔案格式**：JPG用於風景照，PNG用於截圖
- **圖片尺寸**：封面圖 1920x1080，一般照片 1200x800
- **檔案大小**：單張照片控制在 500KB 以下
- **目錄結構**：使用 `gallery/fulls/` 和 `gallery/thumbs/` 分類

#### 3. 響應式優化重點
- **行動優先**：確保手機瀏覽體驗流暢
- **載入速度**：壓縮圖片，優化載入時間
- **觸控友好**：按鈕大小適合手指點選
- **滾動體驗**：利用 Story 模板的滾動動畫

#### 4. 內容組織技巧
- **開場吸引**：用精彩照片或難忘瞬間作開場
- **節奏控制**：交替使用文字和圖片，避免內容過於密集
- **情感連結**：記錄個人感受和旅行心得
- **實用資訊**：適度加入交通、住宿、美食等實用資訊

### 範例：完整旅遊日誌轉換

#### 輸入：旅遊日誌 Markdown
```markdown
# 台東慢活三日遊
> 2024夏日東海岸療癒之旅

<!-- trip-info -->
**旅行時間：** 2024年8月15日 - 8月17日
**交通方式：** 火車 + 租車
**住宿地點：** 台東市區民宿

## 第一天：抵達台東
<!-- day: 2024-08-15 -->
<!-- spotlight: right -->

搭乘普悠瑪號一路向東，窗外的風景從都市高樓漸漸轉為綠野農田，心情也跟著放鬆下來。

### 今日重點
- 🚄 搭乘普悠瑪號抵達台東
- 🏠 Check-in 特色民宿  
- 🌅 鐵花村音樂聚落漫步

![台東車站](day1-taitung-station.jpg)

## 精彩瞬間
<!-- gallery -->

![鐵花村夜景](gallery/thumb01.jpg)|![完整圖片](gallery/full01.jpg)
![伯朗大道](gallery/thumb02.jpg)|![完整圖片](gallery/full02.jpg)
![太麻里日出](gallery/thumb03.jpg)|![完整圖片](gallery/full03.jpg)

## 旅行統計
<!-- stats -->

- 🚂 **交通里程**：350公里火車車程
- 📸 **照片數量**：150張美照
- 🏖️ **海灘造訪**：3個絕美海灘
- 🌅 **日出次數**：2次完美日出
```

#### 輸出：Story模板HTML
Claude會生成包含以下特色的HTML頁面：
- 全螢幕旅程封面，搭配主題照片
- 滾動式每日行程展示（左右交替）
- 互動式照片畫廊（燈箱效果）
- 視覺化旅行統計資訊
- 響應式設計，完美適配各種裝置

### 旅遊日誌類型範例

#### 🏖️ 海島度假型
適合：馬爾地夫、峇里島、沖繩等
重點：海景照片、水上活動、度假村體驗

#### 🏔️ 山林探險型  
適合：尼泊爾、瑞士、台灣高山等
重點：壯麗山景、徒步路線、挑戰記錄

#### 🏛️ 文化古蹟型
適合：義大利、希臘、埃及等
重點：歷史建築、文化體驗、藝術欣賞

#### 🍜 美食探索型
適合：日本、法國、台灣等
重點：特色料理、餐廳推薦、廚藝體驗

這個全新的旅遊日誌生成指南將Story模板的滾動敘事特性與旅行記錄完美結合，讓您的旅行回憶以最美的方式呈現。

## 子目錄專案工作流程

### 專案組織架構

本工作流程採用子目錄模式，每個旅遊日誌專案都有獨立的子目錄，以確保專案間的獨立性和檔案組織的清晰度。

#### 標準目錄結構
```
claude-log/
├── story-temp/              # 共用的模板資源
│   ├── assets/
│   │   ├── css/main.css     # 共用樣式檔案
│   │   ├── js/              # 共用JavaScript檔案
│   │   └── webfonts/        # FontAwesome字體檔案
│   ├── images/              # 模板示例圖片
│   ├── index.html           # 主要模板檔案
│   └── index-demo.html      # 互動式組件展示頁面
├── japan-trip-2024/         # 日本旅行專案
│   ├── japan-trip-2024.md   # 旅遊日誌Markdown檔案
│   ├── japan-trip-2024.html # 旅遊日誌HTML網頁
│   ├── cover-sakura.jpg     # 封面照片
│   ├── day1-osaka.jpg       # 每日照片
│   ├── day2-kyoto.jpg
│   └── gallery/             # 照片畫廊
│       ├── fulls/           # 完整尺寸照片
│       │   ├── 01.jpg
│       │   └── 02.jpg
│       └── thumbs/          # 縮圖
│           ├── 01.jpg
│           └── 02.jpg
├── taiwan-east-coast/       # 台東旅行專案
│   ├── taiwan-east-coast.md
│   ├── taiwan-east-coast.html
│   └── images...
└── CLAUDE.md               # 本指南檔案
```

### 路徑處理標準化

#### 1. CSS和JavaScript資源路徑
子目錄中的HTML檔案應使用相對路徑指向共用的story-temp資源：

```html
<!-- CSS資源 -->
<link rel="stylesheet" href="../story-temp/assets/css/main.css" />
<noscript><link rel="stylesheet" href="../story-temp/assets/css/noscript.css" /></noscript>

<!-- JavaScript資源 -->
<script src="../story-temp/assets/js/jquery.min.js"></script>
<script src="../story-temp/assets/js/jquery.scrollex.min.js"></script>
<script src="../story-temp/assets/js/jquery.scrolly.min.js"></script>
<script src="../story-temp/assets/js/browser.min.js"></script>
<script src="../story-temp/assets/js/breakpoints.min.js"></script>
<script src="../story-temp/assets/js/util.js"></script>
<script src="../story-temp/assets/js/main.js"></script>
```

#### 2. 圖片資源路徑
子目錄中的圖片檔案應使用直接檔名或相對路徑：

```html
<!-- 旅遊日誌專用圖片 -->
<img src="cover-sakura.jpg" alt="櫻花封面" />
<img src="day1-osaka.jpg" alt="大阪第一天" />
<img src="day2-kyoto.jpg" alt="京都第二天" />

<!-- 畫廊圖片使用子目錄 -->
<a href="gallery/fulls/01.jpg" class="image">
    <img src="gallery/thumbs/01.jpg" alt="縮圖" />
</a>
```

#### 3. 路徑模板
創建新旅遊日誌時，HTML檔案的路徑配置模板：

```html
<!DOCTYPE HTML>
<html>
<head>
    <title>旅行標題 - 旅遊日誌</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
    <!-- 共用CSS資源 - 使用 ../ 指向上層目錄 -->
    <link rel="stylesheet" href="../story-temp/assets/css/main.css" />
    <noscript><link rel="stylesheet" href="../story-temp/assets/css/noscript.css" /></noscript>
</head>
<body class="is-preload">
    <!-- Story模板結構 -->
    <div id="wrapper" class="divided">
        <!-- Banner封面 -->
        <section class="banner style1 orient-left content-align-left image-position-right fullscreen">
            <div class="content">
                <h1>旅行標題</h1>
                <p class="major">旅行副標題</p>
            </div>
            <div class="image">
                <!-- 使用專案內封面圖片 - 直接檔名 -->
                <img src="trip-cover.jpg" alt="旅程封面" />
            </div>
        </section>
    </div>
    
    <!-- 共用JavaScript資源 - 使用 ../ 指向上層目錄 -->
    <script src="../story-temp/assets/js/jquery.min.js"></script>
    <script src="../story-temp/assets/js/jquery.scrollex.min.js"></script>
    <script src="../story-temp/assets/js/jquery.scrolly.min.js"></script>
    <script src="../story-temp/assets/js/browser.min.js"></script>
    <script src="../story-temp/assets/js/breakpoints.min.js"></script>
    <script src="../story-temp/assets/js/util.js"></script>
    <script src="../story-temp/assets/js/main.js"></script>
</body>
</html>
```

### 專案建立標準作業程序 (SOP)

#### 步驟一：建立專案子目錄
1. 在 `claude-log/` 下創建新的子目錄
2. 目錄命名慣例：使用描述性名稱，避免空格和特殊字元
   - ✅ 好的命名：`japan-trip-2024`, `taiwan-east-coast`, `europe-backpack`
   - ❌ 避免命名：`我的旅行`, `trip 1`, `vacation!`

#### 步驟二：準備專案檔案
**必要檔案清單：**
- [ ] `{trip-name}.md` - 旅遊日誌Markdown檔案
- [ ] `{trip-name}.html` - 旅遊日誌HTML網頁
- [ ] 封面照片（如 `cover-sakura.jpg`）
- [ ] 每日重點照片（如 `day1-osaka.jpg`）
- [ ] `gallery/` 資料夾（含 `fulls/` 和 `thumbs/` 子目錄）

#### 步驟三：設置正確的路徑
**路徑檢查清單：**
- [ ] CSS路徑：確認使用 `../story-temp/assets/css/main.css`
- [ ] JavaScript路徑：確認所有JS檔案使用 `../story-temp/assets/js/`
- [ ] 圖片路徑：確認使用直接檔名或 `gallery/` 相對路徑
- [ ] noscript CSS：確認包含 `../story-temp/assets/css/noscript.css`

#### 步驟四：本地測試
1. 在瀏覽器中開啟HTML檔案
2. 檢查滾動動畫是否正常運作
3. 測試照片畫廊燈箱效果
4. 確認響應式設計在手機上的表現
5. 測試平滑滾動導航功能

#### 步驟五：部署準備
**GitHub部署檢查：**
- [ ] 確認所有旅行照片已加入專案目錄
- [ ] 確認畫廊圖片的 fulls/ 和 thumbs/ 路徑正確
- [ ] 確認CSS/JS路徑指向 `../story-temp/`
- [ ] 測試線上版本的滾動效果和互動功能

### 常見問題與解決方案

#### 問題一：旅行照片無法顯示
**原因：** 圖片路徑設置錯誤或檔案未上傳
**解決方案：**
1. 檢查照片是否已上傳到正確的專案子目錄
2. 確認HTML中的圖片路徑格式正確（直接檔名或 `gallery/` 路徑）
3. 檢查檔案名稱大小寫是否一致（特別是Linux伺服器）

#### 問題二：滾動動畫無法正常運作
**原因：** JavaScript檔案路徑錯誤或載入失敗
**解決方案：**
1. 確認使用完整的JS檔案清單（包含 scrollex, scrolly 等）
2. 檢查 `../story-temp/assets/js/` 路徑是否正確
3. 確認 `story-temp` 目錄是否存在於上層目錄

#### 問題三：照片畫廊燈箱效果失效
**原因：** Gallery組件設置不正確
**解決方案：**
1. 確認使用 `lightbox` class
2. 檢查 fulls/ 和 thumbs/ 目錄結構是否正確
3. 確認圖片連結格式：`<a href="gallery/fulls/01.jpg">`

#### 問題四：手機瀏覽體驗不佳
**解決方案：**
1. 壓縮照片檔案（建議 500KB 以下）
2. 確認圖片尺寸適中（封面 1920x1080，一般照片 1200x800）
3. 測試觸控滾動和按鈕點選的響應速度

#### 問題五：旅遊日誌專案間檔案衝突
**預防措施：**
1. 每個旅程使用獨立的子目錄
2. 照片檔案使用描述性命名（如 `day1-osaka-castle.jpg`）
3. 避免使用通用檔案名（如 `photo1.jpg`）

### 路徑診斷工具

#### 快速檢查命令
```bash
# 檢查目錄結構
ls -la claude-log/
ls -la claude-log/trip-name/

# 檢查照片檔案存在性
find claude-log/trip-name -name "*.jpg" -o -name "*.png"

# 檢查HTML中的路徑設定
grep -n "src=" claude-log/trip-name/*.html

# 檢查畫廊目錄結構
ls -la claude-log/trip-name/gallery/fulls/
ls -la claude-log/trip-name/gallery/thumbs/
```

#### 旅遊日誌路徑驗證清單
建立新旅遊日誌時，可使用此清單快速驗證：

```markdown
## 旅遊日誌路徑驗證清單

### CSS/JS 資源路徑
- [ ] `<link rel="stylesheet" href="../story-temp/assets/css/main.css" />`
- [ ] `<noscript><link rel="stylesheet" href="../story-temp/assets/css/noscript.css" /></noscript>`
- [ ] `<script src="../story-temp/assets/js/jquery.min.js"></script>`
- [ ] `<script src="../story-temp/assets/js/jquery.scrollex.min.js"></script>`
- [ ] `<script src="../story-temp/assets/js/jquery.scrolly.min.js"></script>`
- [ ] `<script src="../story-temp/assets/js/browser.min.js"></script>`
- [ ] `<script src="../story-temp/assets/js/breakpoints.min.js"></script>`
- [ ] `<script src="../story-temp/assets/js/util.js"></script>`
- [ ] `<script src="../story-temp/assets/js/main.js"></script>`

### 旅行照片路徑
- [ ] 封面照片：`<img src="cover-trip.jpg">` (直接檔名)
- [ ] 每日照片：`<img src="day1-location.jpg">` (描述性命名)
- [ ] 畫廊縮圖：`<img src="gallery/thumbs/01.jpg">` (thumbs子目錄)
- [ ] 畫廊完整圖：`<a href="gallery/fulls/01.jpg">` (fulls子目錄)

### 檔案結構檢查
- [ ] 所有旅行照片都存在於專案子目錄中
- [ ] gallery/fulls/ 和 gallery/thumbs/ 目錄已建立
- [ ] 檔案名稱大小寫一致
- [ ] 照片格式正確（JPG用於風景，PNG用於截圖）
```

### 旅遊日誌最佳實踐建議

#### 1. 照片檔案命名規範
- 使用英文和數字，避免中文檔名
- 使用連字符分隔：`day1-tokyo-tower.jpg`
- 包含日期和地點資訊：`2024-04-01-sakura-park.jpg`

#### 2. 照片優化建議
- 封面照片：1920x1080像素，JPG格式
- 每日照片：1200x800像素，檔案大小 < 500KB
- 畫廊縮圖：300x200像素，檔案大小 < 50KB
- 畫廊完整圖：1600x1200像素，檔案大小 < 800KB

#### 3. 內容組織建議
- 按時間順序組織照片和內容
- 每天記錄包含：地點、活動、感想、照片
- 適度使用emoji增加視覺趣味
- 包含實用資訊：交通、住宿、美食推薦

#### 4. 版本控制與分享
- 使用Git追蹤旅遊日誌版本
- 建立有意義的commit訊息
- 考慮使用GitHub Pages分享給朋友
- 定期備份珍貴的旅行照片

#### 5. 響應式設計考量
- 確保在手機上的閱讀體驗
- 測試滾動動畫在不同裝置上的表現
- 優化照片載入速度
- 考慮離線瀏覽的可能性

這個全新的旅遊日誌工作流程將Story模板的美學設計與旅行記錄的實用性完美結合，讓您的每一次旅行都能以最動人的方式永久保存和分享。