# 交通監控系統 (Traffic Surveillance System)

這是一個即時交通監控的網頁應用程式，整合了台灣多個重要地區（如陽明山、內湖、八里、豐原）的即時路況攝影機畫面。使用者可以透過直覺的介面，快速查看各地的交通狀況與天氣情形。

## 🌟 功能特色

*   **多地點整合**：集中管理多個區域的監控畫面，包含：
    *   陽明山地區
    *   內湖科學園區及周邊
    *   八里左岸及聯外道路
    *   豐原地區
*   **即時串流播放**：支援 HLS (HTTP Live Streaming) 技術，可直接在瀏覽器播放高畫質即時影像。
*   **自動更新快照**：針對僅提供靜態圖片的攝影機，具備點擊或自動重新整理機制。
*   **響應式設計 (RWD)**：介面適配各種螢幕尺寸，無論是桌機或手機都能輕鬆瀏覽。
*   **現代化介面**：使用 CSS 變數與動畫效果，提供舒適的視覺體驗。

## 🛠 技術實現方式

本專案為純前端網頁應用 (Static Web Application)，未使用後端資料庫或伺服器邏輯。

*   **核心語言**：HTML5, CSS3, JavaScript (Vanilla JS)
*   **樣式設計**：
    *   使用原生 CSS Variables (變數) 管理主題色彩。
    *   CSS Grid 與 Flexbox 進行排版。
    *   Keyframes 動畫增加互動感（如載入動畫、呼吸燈效果）。
*   **影像串流**：
    *   整合 **[hls.js](https://github.com/video-dev/hls.js/)** 函式庫，以支援在所有現代瀏覽器中播放 `.m3u8` 格式的串流影片。
    *   部分訊號來源透過 `<iframe>` 嵌入 Youtube 或政府公開網頁。
*   **圖示設計**：使用 SVG 技術繪製輕量且清晰的 Favorith Icon (favicon)。

## 🚀 如何執行 (How to Run)

由於這是靜態網頁專案，您不需要安裝任何複雜的環境或依賴套件。

1.  **下載專案**：將專案檔案下載至您的電腦。
2.  **開啟網頁**：直接雙擊 `cctv.html` 檔案，或將其拖曳至瀏覽器（建議使用 Chrome, Edge, Firefox, Safari 等現代瀏覽器）即可開始使用。

## 📦 如何部署 (Deployment)

本專案可以部署至任何支援靜態網頁的託管服務，完全免費且快速。

### 推薦部署平台：
1.  **GitHub Pages**：
    *   將代碼上傳至 GitHub Repository。
    *   在 Repository Settings -> Pages 中設定 Source 為 `main` branch 即可。
2.  **Vercel / Netlify**：
    *   連結您的 GitHub 帳號。
    *   選擇此 Repository 進行匯入，Build Command 留空，Publish Directory 設為根目錄 (或 `.` ) 即可。
3.  **一般 Web Server**：
    *   將所有 HTML 與 SVG 檔案上傳至 Nginx, Apache 或 IIS 的網頁根目錄即可運作。

## 📂 檔案結構

*   `cctv.html`: 專案首頁 (入口)。
*   `home_to_yangming_cctv.html`: 陽明山地區監控頁面。
*   `home_to_neihu_cctv.html`: 內湖地區監控頁面。
*   `home_to_bali_cctv.html`: 八里地區監控頁面。
*   `home_to_fengyuan_cctv.html`: 豐原地區監控頁面。
*   `favicon.svg`: 網站圖示。

---
&copy; 2025 BensonCho Designed
