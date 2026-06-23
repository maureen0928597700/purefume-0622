# AGENTS.md

## 專案概述

本專案是一個以 Bootstrap 5 製作的單頁香氛品牌網站，主檔案為 `index.html`。網站視覺參考 PUREFUME 香氛網站設計圖，使用紫色導覽列、黑色品牌字樣、白底輪播區、圓角圖片與卡片式產品模組。

## 技術規格

- HTML：單頁式靜態網頁
- CSS Framework：Bootstrap 5
- Bootstrap 引用方式：本地端檔案，不使用 CDN
- 主要樣式：寫在 `index.html` 的 `<style>` 區塊內
- JavaScript：Bootstrap bundle，本地端引用
- 語系：繁體中文
- 響應式：使用 Bootstrap grid 與自訂 media query 支援桌機、平板與手機

## 目錄與檔案

```text
website/
├── index.html
├── AGENTS.md
├── bootstrap-5.3.8-dist/
│   ├── css/
│   │   └── bootstrap.min.css
│   └── js/
│       └── bootstrap.bundle.min.js
├── css/
└── js/
```

## Bootstrap 本地引用

`index.html` 目前引用以下本地端檔案：

```html
<link rel="stylesheet" href="bootstrap-5.3.8-dist/css/bootstrap.min.css">
<script src="bootstrap-5.3.8-dist/js/bootstrap.bundle.min.js"></script>
```

維護時不要改成 CDN。若 Bootstrap 資料夾改名或搬移，需同步修改以上路徑。

## 頁面區塊順序

網站由上到下依序為：

1. 選單導覽列
2. 輪播圖，共 5 張
3. 關於我們，左圖右文
4. 產品介紹，4 個 Bootstrap card 模組
5. 葉偉資訊寒舍群連結
6. 頁尾資訊
7. 版權宣告

## 導覽與錨點

目前主要錨點：

- `#home`：首頁輪播
- `#about`：關於我們
- `#contact`：頁尾聯絡與公司資訊
- `#products`：產品介紹
- `#links`：葉偉資訊寒舍群連結

若新增導覽項目，請確認對應區塊有正確的 `id`。

## 頁尾規格

頁尾目前包含：

- 社群連結
  - Facebook
  - Instagram
  - LINE
- 公司資訊
  - 品牌服務說明
  - 公司地址
  - 營業時間
- 聯絡我們
  - 電話
  - Email
- 版權宣告

社群連結目前使用 `href="#"` 作為佔位。正式上線前需替換為實際網址。

## 圖片資源

目前圖片使用外部 Unsplash 圖片網址作為香氛與自然風格素材。若需完全離線或正式部署，建議：

1. 將圖片下載到專案內，例如 `images/` 資料夾。
2. 將 `src` 改為本地路徑，例如 `images/hero-01.jpg`。
3. 保留適當的 `alt` 文字。

## 視覺風格

主要色彩定義於 `:root`：

```css
--purple: #9f74e8;
--purple-dark: #7f55d7;
--black: #050505;
--red: #ff3a22;
--paper: #ffffff;
--soft: #f5f1ff;
--text: #242124;
```

維護時建議優先修改 CSS 變數，不要在各區塊重複寫死新色碼。

## 維護原則

- 保持 Bootstrap 5 為主要框架。
- 不使用 Bootstrap CDN。
- 新增區塊時優先沿用現有 class 與版面節奏。
- 修改圖片時同步檢查手機版是否裁切正常。
- 修改導覽列時同步檢查錨點。
- 頁尾資訊若有真實公司資料，需替換目前範例內容。
- 不建議把大量新樣式散落到 HTML 標籤的 `style` 屬性中。

## 建議後續整理

- 將自訂 CSS 從 `index.html` 抽出到 `css/style.css`。
- 建立 `images/` 資料夾並改用本地圖片。
- 將社群連結替換為正式網址。
- 補上實際公司名稱、地址、電話與 Email。
- 若網站要上線，請確認圖片授權與隱私權相關聲明。
