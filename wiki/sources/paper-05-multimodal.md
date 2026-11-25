# Source 05: Multimodal Hit Prediction for K-Pop: Audio, Lyrics, and Choreography Cues

- **原始檔案**：`raw/paper_05_multimodal_hit_prediction.md`
- **相關概念**：[[concepts/multimodal-hit-prediction]]、[[concepts/hit-song-science]]、[[concepts/tiktok-effect]]

## 核心摘要
針對 1,200 首 K-Pop 發行曲目建立多模態深度學習框架，整合音訊頻譜、雙語歌詞統計與舞曲挑戰（Dance Challenge）的骨骼關鍵點動態，突破純音訊預測的瓶頸。

## 關鍵數據與發現
1. **雙語歌詞指標**：現代熱門 K-Pop 的英文歌詞佔比平均高達 **38%–45%**，配合高重複率（Compression Ratio）大幅降低全球受眾的記憶門檻。
2. **編舞視覺指標（Point Choreography）**：利用姿態估計模型分析副歌 15 秒編舞，發現 **上半身手部動作集中度高、且與重拍高度對齊** 的編舞，在 TikTok 舞蹈挑戰中的用戶生成內容（UGC）參與度是複雜全身走位編舞的 **3.4 倍**。
3. **預測效能躍升**：結合 Audio + Lyrics + Choreography 的 Multimodal Transformer 模型，在病毒式爆紅預測上的 AUC 達到 **0.91**（F1-score 0.86），遠超純音訊模型的 **0.74**。
