# Wiki Operation Log

記錄所有 `ingest`、`query`、`lint` 與 `build` 操作的不可變時間軸。

## [2026-11-25] init | 初始化 K-Pop Hit Song Science LLM Wiki 架構
- 建立 `AGENTS.md` schema 規範與 `raw/`、`wiki/`、`slides/`、`report/` 目錄結構。

## [2026-11-25] ingest | Paper 01: Hit Song Science & Acoustic Features
- 新增 `wiki/sources/paper-01-hss.md`。
- 建立概念頁 `wiki/concepts/hit-song-science.md` 與實體頁 `wiki/entities/spotify-audio-features.md`。
- 記錄關鍵基準數據：純音訊特徵分類準確率 85–88%，回歸解釋力 $R^2=20.2\%$。

## [2026-11-25] ingest | Paper 02: Musical Structure and Hook Theory in K-Pop
- 新增 `wiki/sources/paper-02-kpop-structure.md`。
- 建立概念頁 `wiki/concepts/kpop-song-structure.md` 與實體頁 `wiki/entities/smp-and-anti-drop.md`。
- 連結 [[hit-song-science]]，補充 K-Pop 與西洋線性流行樂的結構差異（每 15–20 秒切換音色）。

## [2026-11-25] ingest | Paper 03: The "TikTok Effect" on K-Pop Song Structure
- 新增 `wiki/sources/paper-03-tiktok-effect.md` 與概念頁 `wiki/concepts/tiktok-effect.md`。
- 更新 [[kpop-song-structure]]：補充 2015–2026 歌長從 3:32 降至 2:38、前奏縮至 4.2 秒、Bridge 刪減等時間軸演化數據。

## [2026-11-25] ingest | Paper 04: Cross-Cultural Music Perception (Melon vs. Spotify)
- 新增 `wiki/sources/paper-04-cross-cultural.md` 與概念頁 `wiki/concepts/cross-cultural-preference.md`。
- 連結 [[spotify-audio-features]]，標註跨文化矛盾點：Melon 偏好高 Valence (0.62) 與原聲感；Spotify Global 偏好高 Energy (0.79) 與低 Valence (0.46)。

## [2026-11-25] ingest | Paper 05: Multimodal Hit Prediction for K-Pop
- 新增 `wiki/sources/paper-05-multimodal.md` 與概念頁 `wiki/concepts/multimodal-hit-prediction.md`。
- 更新 [[hit-song-science]] 與 [[overview]]：解決單一音訊模態 AUC 僅 0.74 的瓶頸，加入英文歌詞佔比 (38–45%) 與上半身手勢編舞特徵後 AUC 提升至 0.91。

## [2026-11-25] lint | 執行全庫一致性與孤島頁面健康檢查
- 檢查所有 12 個 Markdown 頁面之雙向連結，確認無孤島頁面（Orphan pages）。
- 統一時間單位格式（同時標註「分:秒」與「總秒數」以便簡報視覺化對比）。
- 解決跨論文張力：將 Paper 01 的「純音訊解釋力局限」與 Paper 05 的「多模態突破」建立因果演化連結。

## [2026-11-25] query & build | 生成教學型 HTML 簡報 (`slides/index.html`)
- 讀取 `wiki/index.md` 與 `wiki/overview.md` 進行內容規劃，產出 10 頁互動式教學簡報，涵蓋基礎概念、數據圖表、演化時間軸與多模態模型解析。
