# Personal Brand Website｜個人品牌網站

一個以 HTML、Tailwind CSS 與 JavaScript 建置的個人品牌網站，採用現代化、響應式的網頁設計，呈現個人專業形象、服務項目與職涯經歷，並提供聯絡表單，方便訪客進行合作或業務諮詢。

## 📌 專案介紹

本專案為個人品牌網站（Personal Portfolio），透過簡潔的視覺設計與互動式網頁元件，建立專業且易於瀏覽的個人形象展示平台。

網站採用單頁式架構（Single Page Website），使用者可透過導覽列快速瀏覽不同區塊，並透過聯絡表單傳送訊息。

## ✨ 功能特色

### 1. 個人介紹（About Me）
- 個人品牌首頁與專業介紹。
- 個人形象展示區。
- 提供快速聯絡與服務導覽入口。

### 2. 核心服務（Services）
展示個人專業服務與能力，包含：

- 策略規劃與顧問
- 專案與團隊管理
- 創新技術整合

### 3. 專業經歷（Experience）
- 以時間軸卡片呈現職涯歷程。
- 展示工作職稱、經歷及專案成果。
- 支援後續擴充更多職涯與專案內容。

### 4. 聯絡表單（Contact Form）
- 提供姓名、稱呼、Email 與訊息欄位。
- 表單資料透過 Google Apps Script Web App 傳送至 Google 試算表。
- 提供訊息傳送提示視窗（Modal）。
- 顯示目前瀏覽器執行期間的聯絡紀錄。

### 5. 響應式網頁設計（Responsive Web Design）
- 支援桌面、平板及行動裝置。
- 桌面版提供水平導覽列。
- 行動裝置提供下拉式選單。
- 使用 Tailwind CSS 建立響應式版面。

## 🛠️ 使用技術

| 技術 | 用途 |
|---|---|
| HTML5 | 網頁結構與內容 |
| Tailwind CSS | 響應式版面與 UI 樣式 |
| JavaScript | 網頁互動、表單處理與動態內容 |
| Font Awesome 6.4.0 | 網頁圖示 |
| Google Fonts - Inter | 網頁字體 |
| Google Apps Script | 聯絡表單資料傳送與 Google 試算表整合 |

## 📂 專案目錄結構

```text
personal-brand-website/
│
├── index.html          # 網站主要頁面
├── README.md           # 專案說明文件
│
└── assets/             # 可自行擴充圖片、圖示與其他靜態資源
```

目前網站主要功能集中於 `index.html`，不需要額外安裝前端套件即可執行。

## 🚀 快速開始

### 方法一：直接開啟

1. Clone 或下載本專案。
2. 使用瀏覽器開啟 `index.html`。
3. 即可瀏覽個人品牌網站。

### 方法二：使用 VS Code

建議使用 Visual Studio Code 搭配 Live Server。

1. 使用 VS Code 開啟專案資料夾。
2. 安裝 Live Server 擴充套件。
3. 在 `index.html` 上按右鍵。
4. 選擇 `Open with Live Server`。
5. 瀏覽器將自動開啟網站。

## 🌐 GitHub Pages 部署

本專案為靜態網站，可使用 GitHub Pages 免費部署。

### 部署步驟

1. 將專案上傳至 GitHub Public Repository。
2. 進入 GitHub Repository。
3. 點選 `Settings`。
4. 在左側選單找到 `Pages`。
5. 在 `Build and deployment` 設定中選擇：
   - Source：`Deploy from a branch`
   - Branch：`main`
   - Folder：`/ (root)`
6. 點選 `Save`。
7. 等待 GitHub Pages 完成部署。

部署完成後，網站網址通常為：

```text
https://<github-username>.github.io/<repository-name>/
```

請將 `<github-username>` 與 `<repository-name>` 替換成實際的 GitHub 帳號及 Repository 名稱。

## ⚙️ 聯絡表單設定

網站使用 Google Apps Script Web App 作為聯絡表單的資料接收端。

### 設定方式

1. 建立 Google 試算表，作為聯絡資料儲存位置。
2. 建立 Google Apps Script 專案。
3. 撰寫接收表單資料的後端程式。
4. 將 Apps Script 部署為 Web App。
5. 將取得的 Web App URL 設定於 `index.html`。

目前程式碼透過以下欄位設定 Web App URL：

```html
<input
    type="hidden"
    id="gasUrlInput"
    value="YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL"
>
```

請將 `YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL` 替換成實際部署後的 Web App URL。

表單會傳送以下資料：

| 欄位 | 說明 |
|---|---|
| fullName | 聯絡人姓名 |
| title | 聯絡人稱呼 |
| email | 聯絡人 Email |
| message | 聯絡訊息 |
| timestamp | 傳送時間 |

> 注意：目前前端使用 `fetch()` 搭配 `mode: 'no-cors'` 傳送資料。此模式無法讀取伺服器的實際回應，因此前端顯示成功訊息並不代表 Google 試算表一定已成功寫入資料。

## 🔒 注意事項

- 本專案使用 Tailwind CSS CDN、Font Awesome CDN 與 Google Fonts，使用時需要網路連線。
- 聯絡表單依賴 Google Apps Script Web App，需另外設定資料接收端。
- 目前聯絡紀錄儲存在 JavaScript 記憶體中，重新整理頁面後會清除。
- 網站中的個人介紹、服務項目、經歷及成果目前為示範內容，部署前應替換成真實資訊。
- GitHub Public Repository 的程式碼會公開給所有人檢視，請避免提交個人敏感資料、密碼、API Key 或其他機密資訊。
- 若需要正式對外使用，建議進一步加入表單驗證、垃圾訊息防護及後端資料驗證。

## 📄 License

本專案目前尚未指定正式授權條款。

如需允許其他開發者使用、修改或散布本專案，建議依照實際需求新增 `LICENSE` 文件。

---

**Personal Brand Website**

建立個人專業形象，展示專業能力、職涯經歷與合作機會。
