# 金龍AI-Pro 官方介紹網站

手機上的全能 AI 助理 —— 不只會回答問題，還會真的把事情做完。

- 純單檔靜態網站（`index.html`，約 1,142 行），**零外部依賴**，離線也能開
- 介面樣式參考 Material Design（主色 `#1a73e8`，深色模式）
- 開場動畫：Google One 式四色環（幾何取自實機 Google One APK：畫布 64、圓心 (32,32)、外徑 29.33 / 內徑 25.29）
  - 四色 `#4285F4` `#EA4335` `#FBBC05` `#34A853`，順時針依序畫出（綠 → 黃 → 紅 → 藍）
  - 可點擊／按鍵／滾輪略過；`prefers-reduced-motion` 時完全不播
- 其他功能：4 個分頁、FAQ 展開、首頁搜尋即時篩選、深色模式（`localStorage: jl-theme`）、20 個手繪 SVG 圖示、Material 漣漪

## 本機預覽

直接用瀏覽器開啟 `index.html` 即可（或 `python3 -m http.server 8080`）。

## 線上版本

https://haydenmok123-wq.github.io/Ai/

## 調整開場動畫

| 想改什麼 | 位置 |
|---|---|
| 整體長度 | JS `var T={ end:3600 }`（毫秒） |
| 四色出現間隔 | CSS `.g1-arc.a1 ~ .g1-arc.a4` 的 `animation-delay` |
| 每段弧長度 | `@keyframes g1-draw` 終點 `276`（276 = 畫出 84°） |
| 環的粗細 | `.g1-arc{stroke-width:4.04}` |
| 繪製方向 | 四條 `<path>` 的 `sweep` 旗標（`1` = 順時針、`0` = 逆時針） |
