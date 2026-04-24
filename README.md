# NCT_VIEW

<p align="center">
  <strong>No Conversion Therapy API 的最生動可視化演示</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Vue.js-4FC08E?style=for-the-badge&logo=vue.js&logoColor=white" alt="Vue3">Vue3
  <img src="https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white" alt="Cloudflare">CLOUDFLARE
</p>

`NCT_VIEW` 是一個基於 Vue 3 開發的前端項目，旨在為 **NO CONVERSION THERAPY** 提供的數據接口提供直觀、感性的交互式展示。它不僅是一個演示工具，更是一個可以直接使用的開發模板。

## ✨ 特性

* **高性能渲染**：利用 Vue 3 的組合式 API 進行數據管理與視圖更新。
* **開發者友好**：標準的 Vue 項目結構，支持快速 Fork 與二次開發。
* **一鍵部署**：支持 Cloudflare Pages、Vercel 等主流無服務器平台。

## 🛠️ 技術棧

* **框架**: Vue 3 (Vite)
* **部署**: GitHub Actions + Cloudflare Pages

## 🚀 快速開始

### 0. API食用指南

#### 後端架構

首先受害者的表單會通過Google Forms傳送到Google Sheets，在這裏和牧鳶整理的數據進行混合，並通過Google App Script和Google map將每一條數據標記上經緯度，並計算出各個統計數據的值。

Google App Script將統計數據和所有表單打包封裝進Json裏，這是第一層api。

[NCT_API](https://github.com/NO-CONVERSION-THERAPY/NCT_API)項目將第一層api進行清洗后，形成第二層api，並供下游項目使用。

請前往[NCT_API README](https://github.com/NO-CONVERSION-THERAPY/NCT_API)查看api的具體使用指南。

### 1. 克隆項目
```bash
git clone https://github.com/NO-CONVERSION-THERAPY/NCT_VIEW.git
cd NCT_VIEW
```

### 2. 安裝依賴
```bash
npm install
# 或者
pnpm install
```

### 3. 本地開發
```bash
npm run dev
```

### 4. 構建與部署
```bash
npm run build
```
構建完成後的 `dist` 目錄即可部署至任何靜態託管平台。

## 🤝 貢獻

這是一個開放的項目，非常歡迎你：
* **Fork** 本項目並開發自己的版本。
* 提交 **Pull Request** 來改善現有的可視化邏輯。
* 開啟 **Issue** 反饋發現的 Bug 或功能建議。

## 📄 開源協議

基於 [Apache2.0License](LICENSE) 開源。