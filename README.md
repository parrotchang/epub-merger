# epub-merger

在瀏覽器內把多個 EPUB 依指定順序合併成一本的小工具。純前端、單一 HTML 檔，檔案不會上傳到任何伺服器。

A single-file, client-side tool that merges multiple EPUB files into one, in the order you choose. Nothing is uploaded.

## 使用方式

1. 用瀏覽器開啟 `index.html`（或部署到 GitHub Pages）。
2. 拖曳或選擇要合併的 `.epub`，用 ↑ ↓ 排好順序（也可按「依檔名排序」）。
3. 視需要修改書名、作者、語言，以及目錄是否依檔案分組。
4. 按「合併成一個 EPUB」，再按「下載 EPUB」。

第一次使用可按「載入範例檔」，範例順序是故意打亂的。

## 運作方式

- 每個 EPUB 的檔案原封不動放進獨立資料夾（`b1/`、`b2/`、`b3/`…），同名的章節或樣式檔不會互相覆蓋，內部連結也不必改寫。
- 重新產生 `content.opf`（清單與閱讀順序）、`nav.xhtml`（EPUB 3 目錄）與 `toc.ncx`（EPUB 2 相容目錄）。
- `mimetype` 依規範放在壓縮檔第一個且不壓縮。輸出為 EPUB 3。
- 目錄預設每個檔案一個區塊，底下保留原章節；也可攤平。

## 限制

- 不處理有 DRM 的檔案。
- 不處理固定版面（fixed-layout）的特殊設定。
- 章節內容中指向其他檔案的絕對路徑連結不會改寫。
- 只做串接，不會偵測或去除不同版本之間重複的章節。
- 建議合併後用 [epubcheck](https://github.com/w3c/epubcheck) 驗證，並以不同閱讀器各開一次確認。

## 相依套件

- [JSZip](https://stuk.github.io/jszip/) 3.10.1，從 cdnjs 載入（MIT 或 GPL-3.0 擇一授權）。
- 字型 Inter、Noto Sans TC、Space Grotesk、JetBrains Mono 由 Google Fonts 載入（SIL OFL）。離線時會退回系統字型。

## 授權

[MIT](LICENSE) © 2026 parrotchang
