# Source 01: Hit Song Science (HSS) & Acoustic Features in Popular Music

- **原始檔案**：`raw/paper_01_hss_acoustic_features.md`
- **相關概念**：[[concepts/hit-song-science]]、[[entities/spotify-audio-features]]、[[concepts/multimodal-hit-prediction]]

## 核心摘要
本研究奠定了音樂資訊檢索（MIR）中「熱門歌曲科學（Hit Song Science）」的量化基礎，利用 Spotify API 提取的聲學特徵分析數萬首進榜與未進榜歌曲。

## 關鍵數據與發現
1. **流行樂的聲學特徵畫像**：
   - `Danceability`（可舞性）與 `Loudness`（響度，通常達 -6 至 -4 dB）與進榜機率高度正相關。
   - `Acousticness`（原聲程度）呈顯著負相關，顯示電子合成音色是當代流行樂的主流。
2. **模型表現與天花板**：
   - 隨機森林（Random Forest）在「是否進入 Billboard Hot 100」的二元分類上可達 **85%–88%** 準確率。
   - 但在預測連續串流熱門度分數（0–100）時，純音訊特徵的解釋力 $R^2$ 僅為 **20.2%**（AUC 約 0.74）。
3. **對本知識庫的意義**：
   - 證實音訊特徵能過濾出「具備商業製作水準」的歌曲，但無法單獨解釋病毒式爆紅，直接引出了 [[sources/paper-02-kpop-structure]] 的結構分析與 [[sources/paper-05-multimodal]] 的多模態融合需求。
