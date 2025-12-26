# AI 圖表生成器 (AI Chart Generator)

這是一個現代化、功能強大且純前端的網頁應用程式，能夠將您的 Excel 和 CSV 數據即時轉換為精美、互動式的圖表視覺化效果。

## 🚀 功能特色

*   **輕鬆匯入數據**：支援拖放 `.xlsx`、`.xls` 和 `.csv` 檔案。
*   **智慧解析**：自動偵測時間序列欄位和數值資料以進行繪圖。
*   **多種圖表類型**：可即時切換以下圖表：
    *   折線圖 (Line Chart - 平滑曲線)
    *   柱狀圖 (Bar Chart)
    *   區域圖 (Area Chart)
    *   散佈圖 (Scatter Plot)
    *   堆疊柱狀圖 (Stacked Bar Chart)
*   **互動式視覺化**：
    *   透過內建滑桿縮放和捲動數據。
    *   懸停提示框 (Tooltip) 顯示詳細數據點。
    *   響應式設計，適應各種螢幕尺寸。
*   **客製化主題**：內建 **深色模式 (Dark Mode)** 支援，並可自動偵測系統偏好設定。
*   **高品質匯出**：將圖表匯出為高解析度的 **PNG** 或 **JPG** 圖片。

## 🛠️ 技術堆疊

本專案使用現代 Web 標準建構，並透過 CDN 引用強大的函式庫，無需複雜的建置步驟。

*   **核心**：HTML5, Vanilla JavaScript (原生 JS)
*   **樣式**：[Tailwind CSS](https://tailwindcss.com/) (Utility-first CSS 框架)
*   **視覺化**：[Apache ECharts](https://echarts.apache.org/) (強大的圖表庫)
*   **數據處理**：[SheetJS (xlsx)](https://sheetjs.com/) (Excel 檔案解析)
*   **字體**：[Google Fonts](https://fonts.google.com/) (Inter 字體系列)

## 📦 如何執行

由於這是一個使用 CDN 連結的靜態網頁應用程式，您不需要安裝 `npm` 或 `node_modules`。

1.  **複製儲存庫** (或是下載檔案)：
    ```bash
    git clone <your-repo-url>
    ```
2.  **開啟 `index.html`**：
    直接雙擊 `index.html` 檔案，在您的預設瀏覽器中開啟。

    *注意：為了獲得最佳體驗（特別是涉及本地檔案權限時），建議使用像 VS Code "Live Server" 擴充功能這樣的輕量級本地伺服器，但直接開啟檔案通常也能運作。*

## 📖 使用說明

1.  **上傳數據**：將您的 Excel 檔案拖放到上傳區域，或點擊以瀏覽檔案。
2.  **檢視圖表**：應用程式會自動解析您的數據並產生折線圖。
3.  **自訂調整**：
    *   使用頂部的切換按鈕更改圖表類型（柱狀圖、區域圖等）。
    *   點擊「月亮/太陽」圖示切換 深色/淺色 模式。
4.  **匯出**：點擊 **Export** 按鈕並選擇格式（PNG 或 JPG）以儲存圖表。

## 🚀 部署指南

您可以將此專案免費部署在任何靜態網站託管服務上。

### 選項 1: GitHub Pages
1.  將您的程式碼推送到 GitHub 儲存庫。
2.  前往 **Settings (設定)** > **Pages**。
3.  選擇 `main` 分支和 `/ (root)` 資料夾。
4.  儲存後，您的網站就會上線。

### 選項 2: Netlify / Vercel
1.  將您的 GitHub 儲存庫連結到 Netlify 或 Vercel。
2.  由於沒有建置指令，只需使用預設設定（根目錄為 `.`）。
3.  部署！

## 📄 資料格式要求
為獲得最佳結果，請確保您的 Excel 檔案具備：
1.  **標題列**：第一列應包含欄位名稱。
2.  **日期欄位**：(選填) 一個包含日期的欄位（例如："Date", "Time", "Year"）。
3.  **數據欄位**：您想要視覺化的數值欄位。

---
由 Benson 製作
