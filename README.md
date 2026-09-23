# IoTMart Campaign Previewer

IoTMart Campaign Previewer 是一個可直接在瀏覽器中使用的活動頁視覺化編輯與預覽工具。它支援匯入 Magnolia Campaign Page YAML、搭配本機圖片素材即時預覽，並將編輯結果匯出為可再次編輯的 YAML、預覽 HTML 與圖片素材 ZIP。

## 功能

- 建立空白活動頁，或從完整範例開始編輯
- 匯入 `.yaml` / `.yml` 檔案或直接貼上 YAML 文字
- 選擇本機 `assets` 圖片資料夾並在瀏覽器中預覽
- 拖曳、新增、排序、隱藏與編輯 Campaign 元件
- 編輯文字、連結、圖片及元件設定
- 切換頁面主題與不同預覽尺寸
- 匯出包含 YAML、預覽 HTML 與圖片的 `.zip` 檔案
- 中英文介面
- JSZip 與 js-yaml 已內嵌，可離線使用主要功能

## 快速開始

本專案不需安裝套件或建置。

1. 下載或 clone 此 repository。
2. 使用瀏覽器開啟 `IoTMart_Campaign_Previewer.html`。
3. 選擇「開始空白頁」、「開啟完整範例」或「匯入 YAML」。
4. 編輯完成後，按下「匯出 YAML + HTML + 圖片（.zip）」。

也可以使用本機 HTTP server：

```bash
python3 -m http.server 8000
```

然後開啟 <http://localhost:8000/IoTMart_Campaign_Previewer.html>。

## 輸入格式

工具接受符合 Magnolia Campaign Page 結構的 YAML：

- YAML 頂層為單一 Campaign slug
- 頁面元件放在 `mainBody`
- 支援完整外部圖片 URL
- 使用相對圖片路徑時，可同時選擇本機 assets 資料夾

可參考 `IoTMart_Campaign_Template_URLImages.yaml`，其中包含使用線上圖片 URL 的完整範例。

## 匯出內容

匯出的 ZIP 以 Campaign slug 命名，內容包含：

- `<campaign-slug>.yaml`：可供後續編輯或匯入的頁面資料
- `<campaign-slug>-preview.html`：獨立預覽頁面
- `assets/`：此次編輯使用的本機圖片素材

## 專案結構

```text
IoTMart_Campaign_Previewer/
├── IoTMart_Campaign_Previewer.html
├── IoTMart_Campaign_Template_URLImages.yaml
└── README.md
```

- `IoTMart_Campaign_Previewer.html`：主程式，包含 UI、樣式與瀏覽器端邏輯
- `IoTMart_Campaign_Template_URLImages.yaml`：線上圖片 URL 範例

## 注意事項

- 所有 YAML 解析、頁面編輯與 ZIP 產生皆在瀏覽器端完成。
- Google Fonts 與範例中的外部圖片需要網路連線；本機素材與內嵌程式庫可離線使用。
- 匯出前請確認元件內容、連結、圖片路徑與 Campaign slug。

## License

此專案尚未指定開源授權。未經授權請勿散布或商業使用。