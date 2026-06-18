# 🇰🇷 釜山家族行 5 日智慧行程 App

> 為 2026/6/24–28 釜山家族自由行（5 人含爸媽）打造的單頁式行程 App。手機優先、可加到桌面當 App 用、支援 AI 助理、離線檢視、即時天氣與記帳。

一個檔案搞定（`busan_2026.html`），不需後端、不需安裝、不需編譯。打開瀏覽器或加到手機桌面即可使用。

---

## ✨ 功能總覽

| 分頁 | 功能 |
|------|------|
| **行前** | 必備預約清單、打包進度條、戰利品購物清單（可新增/刪除/分享）|
| **資訊** | 今日票券聚合、匯率換算機、VISIT BUSAN PASS 說明、計程車防坑提醒、手指韓文、即時語音翻譯 |
| **記帳** | 韓幣消費紀錄、分類統計長條圖、台幣換算、匯出分享 |
| **每日行程（D1–D5）** | 時間軸行程卡、每日天氣帶、下雨室內備案、Google + Naver 雙地圖導航、計程車字卡 |

### 重點特色

- 🤖 **AI 旅遊助理（Busan Bot）**：串接 Google Gemini，能回答行程問題、推薦美食、翻譯菜單/告示/藥品（支援拍照辨識）。AI 能讀取完整行程脈絡（含已預約、PASS、雨備等），回答精準。
- 🌦️ **天氣連動穿搭與雨備**：串接 Open-Meteo，每日顯示高低溫、降雨機率（顏色分級）、穿搭建議；降雨機率 >50% 自動跳出室內備案。
- 💱 **匯率換算機**：韓幣 ⇄ 台幣雙向即時換算，匯率可自訂。
- ⏰ **不可遲到提醒**：為有預約時段的行程（Ribs of Legend、天空膠囊列車、廣安里遊艇）標記準時徽章與建議出發時間。
- 📍 **下一個行程浮動提示**：依當下時間自動顯示接下來的行程與交通。
- 🗺️ **Google + Naver 雙地圖導航**：每個景點、餐廳、購物點都提供 Google Maps 與 Naver Map 兩顆導航按鈕。Naver Map 在韓國當地資訊更完整（Google 在韓國常搜不到），兩者互補不留死角。Naver 採用 `https://map.naver.com/p/search/` 網頁連結，未裝 App 可開網頁、已裝會自動詢問跳轉 App。
- 🗣️ **手指韓文 + 即時語音翻譯**：常用韓語字卡（含計程車防坑用語），中韓雙向語音翻譯朗讀。
- 🧾 **計程車防坑功能 + Taxi Card**：一鍵顯示「請給我收據」等韓語字卡與語音；主要搭車目的地（含每天回飯店的回程）都備有 Taxi Card，顯示韓文店名與地址給司機看，可朗讀、可直接 Naver 導航。
- 💾 **本地儲存**：打包清單、記帳、設定皆存於瀏覽器 localStorage，關掉再開資料還在。
- 🕐 **時光機測試模式**：點標題可模擬任意日期時間，預覽「進行中」「下一個行程」等動態效果。

---

## 🛠️ 技術棧

純前端，所有相依套件以 CDN 載入，無建置流程：

- [Alpine.js](https://alpinejs.dev/) 3.x — 輕量響應式框架
- [Tailwind CSS](https://tailwindcss.com/) 3.x — 樣式
- [Swiper](https://swiperjs.com/) 11 — 分頁滑動
- [Phosphor Icons](https://phosphoricons.com/) — 圖示
- [Marked](https://marked.js.org/) — Markdown 渲染（AI 回覆用）
- Google Fonts（Noto Sans TC）

### 外部 API

| 用途 | 服務 | 是否需金鑰 |
|------|------|-----------|
| AI 助理 | Google Gemini API | ✅ 需自備 API Key（使用者於 App 內設定）|
| 天氣預報 | [Open-Meteo](https://open-meteo.com/) | ❌ 免費、免金鑰 |
| 即時翻譯 | [MyMemory](https://mymemory.translated.net/) | ❌ 免費、免金鑰 |
| 地圖導航 | Google Maps / [Naver Map](https://map.naver.com/) 網頁連結 | ❌ 免金鑰（純連結跳轉）|
| 語音辨識/朗讀 | 瀏覽器 Web Speech API | ❌ 瀏覽器內建 |

> ⚠️ **天氣預報限制**：Open-Meteo 免費版僅能預報未來約 16 天。出發前太早開啟會顯示「預報尚未開放」，屬正常現象，接近出發日（約行前 1–2 週）資料才會出現。

---

## 🚀 快速開始

### 直接使用

下載 `busan_2026.html`，用瀏覽器打開即可。手機建議「加到主畫面」當 App 用（見 `安裝與使用教學.md`）。

### 透過 GitHub Pages 發布（推薦，方便手機開啟）

1. 將 `busan_2026.html` 上傳到你的 GitHub repo。
2. 進入 repo 的 **Settings → Pages**。
3. **Source** 選 `Deploy from a branch`，Branch 選 `main`（資料夾 `/root`），按 Save。
4. 等待約 1 分鐘，會得到一個網址，例如：
   ```
   https://<你的帳號>.github.io/<repo名稱>/busan_2026.html
   ```
5. 把這個網址用手機打開，加到主畫面即可。

> 💡 若希望網址更短，可把檔案改名為 `index.html`，網址就會變成 `https://<你的帳號>.github.io/<repo名稱>/`

---

## 🔑 設定 AI 助理（選用）

AI 功能需要 Google Gemini API Key（免費額度足夠個人使用）：

1. 前往 [Google AI Studio](https://aistudio.google.com/apikey) 登入 Google 帳號。
2. 點 **Create API Key**，複製產生的金鑰（以 `AIza` 開頭）。
3. 在 App 中點右下角機器人按鈕 → 齒輪圖示 → 貼上 API Key → 儲存。

不設定 API Key 也能使用 App 的所有其他功能（行程、記帳、天氣、翻譯等），只有 AI 對話/拍照辨識需要金鑰。

### 模型選擇

| 模型 | 特性 | 免費額度 |
|------|------|---------|
| Gemini 2.5 Flash（預設）| 快速、支援圖片辨識 | 250 次/天 |
| Gemini 2.5 Pro | 最強推理 | 100 次/天 |
| Gemini 2.5 Flash Lite | 省額度 | 1000 次/天 |

---

## 📁 專案結構

```
.
├── busan_2026.html        # 主程式（單一檔案，包含所有 HTML/CSS/JS 與行程資料）
├── README.md              # 本說明文件
└── 安裝與使用教學.md       # 給家人看的 iPhone 安裝與操作教學
```

行程資料寫在 `busan_2026.html` 內的 `tripData()` → `daysData` 陣列，可直接修改。

---

## ✏️ 自訂行程

打開 `busan_2026.html`，找到 `const daysData = [...]`，每一天是一個物件，每個行程是 `events` 陣列中的項目。常用欄位：

```javascript
{
  time: '17:30',                    // 時間
  type: 'train',                    // 類型：flight/transport/train/food/activity/hotel
  name: '📸 天空膠囊列車 青沙浦→尾浦', // 名稱
  desc: '...',                      // 簡述
  location: '스카이캡슐 청사포',      // 地點（Google Maps & Naver Map 導航用）
  isConfirmed: true,                // 標記為「已預約」
  isPass: true,                     // 標記為「使用 VISIT BUSAN PASS」
  mustOnTime: true,                 // 標記為「不可遲到」
  leadTime: 20,                     // 建議提前出發分鐘數
  isWarn: true,                     // 標記為「注意」
  detail: '...',                    // 展開後的詳細說明（支援 HTML）
  tips: '...',                      // 小提醒
  taxi: { krName: '...', address: '...' }, // 計程車韓語字卡
  restaurants: [ { name, dish, price, queue } ], // 餐廳清單
  shopping: [ { name, items } ]     // 購物清單
}
```

雨備清單在 `rainBackup` 物件（依日期 index 對應），匯率預設值在 `fxRate`。

---

## ⚠️ 注意事項

- 本 App 為個人家族旅遊用途，行程資訊（餐廳、票價、營業時間）為製作當下整理，**實際請以官方/現場為準**。
- AI 助理對「行程外」的開放問題（如即時店家資訊）回答來自模型訓練知識，**非即時查詢**，可能過時。
- 天氣為 Open-Meteo 預報，僅供參考。
- 所有資料儲存在使用者自己的瀏覽器，不上傳雲端；清除瀏覽器資料會一併清除。

---

## 📄 授權

個人使用專案，自由取用修改。第三方套件與 API 各自遵循其授權條款。

---

*Made with ❤️ for a family trip to Busan*
