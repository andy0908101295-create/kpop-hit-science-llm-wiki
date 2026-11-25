# AGENTS.md — K-Pop Hit Song Science LLM Wiki Schema

## 1. 專案願景與三層架構 (Architecture)
本知識庫採用 Andrej Karpathy 的 **LLM Wiki** 設計模式，針對「K-Pop 音樂特徵、曲風結構與熱門歌曲預測（Music Information Retrieval & Hit Song Science）」建立持久化、複利成長的結構化知識庫。

- **`raw/`（原始資料層 — Immutable）**：存放 5 篇研究論文與文獻摘要，作為單一真實來源（Source of Truth），AI 僅可讀取，嚴禁修改。
- **`wiki/`（知識庫層 — LLM Owned）**：由 AI 維護的結構化 Markdown 知識網絡，包含：
  - `wiki/index.md`：內容導向總目錄（Catalog），每次 Ingest 後必須更新。
  - `wiki/log.md`：時間序操作日誌（Append-only Log），記錄所有 Ingest、Query 與 Lint 動作。
  - `wiki/overview.md`：跨文獻綜合論點（Evolving Synthesis）與核心發現。
  - `wiki/sources/`：單篇論文精讀筆記（每篇對應 `raw/` 中的一篇資料）。
  - `wiki/concepts/`：跨論文的核心概念頁（如：[[hit-song-science]]、[[kpop-song-structure]]、[[tiktok-effect]]、[[cross-cultural-preference]]、[[multimodal-hit-prediction]]）。
  - `wiki/entities/`：關鍵指標、模型與曲風實體頁（如：[[spotify-audio-features]]、[[smp-style]]）。
- **`slides/`（應用輸出層）**：基于 `wiki/` 知識庫產生的互動式教學 HTML 簡報（`slides/index.html`）。
- **`report/`（作業流程與反思報告）**：完整記錄 Loop / Graph 設計與執行反思（`report/workflow-and-reflection.md`）。

## 2. 操作規範 (Operations & Loop Rules)
1. **Ingest（攝取與編譯）**：
   - 讀取 `raw/` 新文件後，不可僅做片段摘要，必須建立 `wiki/sources/` 筆記。
   - 同步更新或建立相關的 `wiki/concepts/` 與 `wiki/entities/` 頁面，建立雙向 Wiki 連結（`[[page-name]]`）。
   - 更新 `wiki/overview.md` 中的綜合結論，並標註新舊文獻間的演進或矛盾（例如：純音訊特徵預測力有限 vs. 多模態/藝人聲量加入後的提升）。
   - 更新 `wiki/index.md` 與附加紀錄至 `wiki/log.md`。
2. **Query & Slide Generation（查詢與簡報生成）**：
   - 製作簡報或回答問題時，**優先讀取 `wiki/index.md` 與 `wiki/overview.md`**，再深入對應的概念頁，嚴禁繞過 Wiki 直接憑空捏造數據。
   - 產出簡報前必須執行 **事實與引用檢查（Verification Gate）**，確認每個圖表數字、論文結論皆可追溯至 `wiki/sources/`。
3. **Lint（知識庫健康檢查）**：
   - 檢查是否存在孤島頁面（Orphan pages）、斷裂的 `[[連結]]`、或跨論文數據衝突（如歌長縮短趨勢的年份與秒數定義），並於 `wiki/log.md` 留下紀錄。
