# GitHub Pages 網站

靜態網站，用於介紹 **離線智能助手**（FlightMode AI）。

## 頁面

| 檔案 | 說明 |
|------|------|
| `index.html` | 首頁：架構、五種模式、裝置需求 |
| `privacy.html` | 私隱政策 |
| `terms.html` | 使用條款（含甜故模式 18+） |
| `contact.html` | 聯絡與支援 |
| `styles.css` | 共用樣式 |

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

## 更新聯絡電郵

將 `contact.html` 中的 `support@flightmode-ai.example.com` 改為你的真實信箱。
