# Overview: K-Pop 爆紅的資料科學與音樂資訊檢索（MIR）全貌

本總覽頁綜合了知識庫中 5 篇核心文獻的發現，回答一個核心問題：**「從資料科學與音樂學角度來看，一首 K-Pop 為什麼會紅？」**

## 核心演進脈絡（The Compounding Thesis）

1. **聲學基礎（Acoustic Baseline — [[sources/paper-01-hss]]）**：
   流行歌曲在聲學特徵上並非隨機分布，高 `Danceability`、高 `Energy`、高 `Loudness` 與低 `Acousticness` 構成了現代流行樂的「入場門檻」。然而，僅靠音訊表格特徵預測熱門度存在明顯天花板（回歸 $R^2$ 僅 20.2%，分類 AUC 0.74）。
2. **結構創新（Structural Hook — [[sources/paper-02-kpop-structure]]）**：
   K-Pop 突破歐美線性結構，採用 **15–20 秒切換一次曲風的「多段式拼接」**、**Anti-Drop 反高潮**，以及**高重複度雙語音節 Hook**，在資訊密度上遠超傳統流行樂，持續刺激聽眾的多巴胺預期。
3. **演算法重塑（Short-Form Compression — [[sources/paper-03-tiktok-effect]]）**：
   隨著 TikTok / Reels / Shorts 與 Spotify 30 秒計費機制主導市場，2015 至 2026 年間 K-Pop 經歷劇烈「時間壓縮」：平均歌長從 **3:32 縮短至 2:38**，前奏從 **14.5 秒壓縮至 4.2 秒**，超過 55% 歌曲採用 **Chorus-First** 或 35 秒內進副歌，並大幅刪減 Bridge 以誘導自動重播。
4. **市場分眾（Cross-Cultural Divergence — [[sources/paper-04-cross-cultural]]）**：
   「紅」在不同市場有截然不同的聲學定義。韓國本土 **Melon** 偏好高情緒正向度（Valence 0.62）與清亮旋律（Easy-Listening）；全球 **Spotify** 則偏好極高能量（Energy 0.79）、低正向度（Valence 0.46）的重拍舞曲。
5. **多模態融合（Multimodal Synergy — [[sources/paper-05-multimodal]]）**：
   K-Pop 是高度視覺化的產業。當模型將 **音訊頻譜 + 英文歌詞佔比（38–45%） + 適合直式螢幕的上半身 Point 編舞特徵** 結合後，爆紅預測 AUC 從純音訊的 **0.74 躍升至 0.91**。

## 跨文獻核心數據對照表

| 維度 / 指標 | 傳統 / 早期基準 (2015) | 現代短影音時代 (2024–2026) | 資料來源 |
| :--- | :--- | :--- | :--- |
| **平均歌曲總長** | 3 分 32 秒 (212 秒) | 2 分 38 秒 (158 秒) | [[sources/paper-03-tiktok-effect]] |
| **平均前奏長度** | 14.5 秒 | 4.2 秒（超過 55% 副歌前置） | [[sources/paper-03-tiktok-effect]] |
| **本土 Melon 偏好** | 高 Valence (0.62)、中高 Acousticness (0.28) | 延續 Easy-Listening 與樂團曲風優勢 | [[sources/paper-04-cross-cultural]] |
| **全球 Spotify 偏好** | 高 Energy (0.79)、高 Danceability (0.76) | 偏好重低音、小調與高舞蹈能量 | [[sources/paper-04-cross-cultural]] |
| **熱門曲英文佔比** | 約 15%–25%（集中於副歌單字） | 38%–45%（降低全球跟唱門檻） | [[sources/paper-05-multimodal]] |
| **預測模型效能** | 純音訊回歸 $R^2 = 20.2\%$ / AUC = 0.74 | 多模態融合模型 AUC = **0.91** | [[sources/paper-01-hss]], [[sources/paper-05-multimodal]] |
