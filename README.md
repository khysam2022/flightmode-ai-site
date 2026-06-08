# GitHub Pages 網站

靜態網站，用於介紹 **機上檔 / FlightMode AI**。

## 語言

- 支援 **English**、**简体中文**、**繁體中文**、**日本語**
- 首次造訪會依瀏覽器／手機語言自動選擇（`ja` → 日文；`zh-TW`/`zh-HK` → 繁中；其餘 `zh` → 簡中；`en` → 英文；其他 → 英文）
- 右上角語言按鈕可手動切換；選擇會存入 `localStorage`

## 頁面

| 檔案 | 說明 |
|------|------|
| `index.html` | 首頁：架構、五種模式、裝置需求 |
| `privacy.html` | 私隱政策 |
| `terms.html` | 使用條款（含甜故模式 18+） |
| `contact.html` | 聯絡與支援 |
| `styles.css` | 共用樣式 |
| `i18n.js` | 多語言字串與切換邏輯 |

## 部署（GitHub Pages）

1. 推送 `docs/` 至 GitHub
2. Repository **Settings → Pages**
3. **Build and deployment → Source**: Deploy from a branch
4. **Branch**: `main` / folder **`/docs`**
5. 儲存後等待數分鐘，站點網址通常為 `https://<username>.github.io/<repo>/`

## 本地預覽

```bash
cd docs
python3 -m http.server 8080
# 開啟 http://localhost:8080
```

## 聯絡電郵

支援與私隱洽詢：**skyhkgapp@gmail.com**
