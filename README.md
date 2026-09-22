# 上週有人這樣做

每週二出刊的 AI 落地案例報告。翼馳行銷 Adolph(豆腐)。

網站:https://adolph-ceo.github.io/Yichih_Ai_info_forYixin/

## 第一次設定(只做一次)

1. 在 GitHub 建立一個新的 public repository,名字取 `weekly`
2. 把這個資料夾裡的所有檔案推上去(或直接用網頁介面拖曳上傳)
3. 進 repo 的 Settings → Pages,Source 選 `Deploy from a branch`,Branch 選 `main` / `root`,存檔
4. 等 1 到 2 分鐘,網址就會活起來
5. 把所有檔案裡的 `adolph-CEO` 換成你的 GitHub 帳號名稱。這串出現在 `index.html`、每期的 `index.html` 與本檔,是社群預覽圖與網址用的絕對路徑,不換的話貼連結出去不會跑出預覽圖

## 每期的檔案結構

```
weekly/
├── index.html              # 彙整頁,列出所有期數
├── assets/
│   └── og-YYYY-MM-DD.png   # 該期的社群預覽圖,1200x630
└── YYYY-MM-DD/
    └── index.html          # 該期報告
```

每期的網址是 `https://adolph-ceo.github.io/Yichih_Ai_info_forYixin/YYYY-MM-DD/`

## 每期出刊要做的事

1. 產出報告 HTML(放在專案的 `reports/`)
2. 產生社群預覽圖:`python3 config/make_og.py site/assets/og-YYYY-MM-DD.png "YYYY / MM" "主標第一行\n主標第二行" "標籤1|數值1" "標籤2|數值2" "標籤3|數值3"`
3. 把報告複製到 `site/YYYY-MM-DD/index.html`,並在 `<title>` 前插入 OG meta 標籤(標題、描述、圖片網址)
4. 在 `index.html` 的第一則位置插入新的 `<article class="issue">` 區塊
5. 推上 GitHub,1 到 2 分鐘後生效

## 貼連結出去會長什麼樣

貼到 Facebook、LINE、Threads 時,會顯示 1200x630 的預覽圖(米色底、深咖啡標題、下方三組關鍵數字),加上標題與描述文字。描述寫的是該期最有力的幾個數字,不是泛泛的介紹 - 目的是讓人在動態牆上滑過去時,先被數字擋下來。
