# Paper 05: Multimodal Hit Prediction for K-Pop: Audio, Lyrics, and Choreography Cues
- **Authors**: Kang, Shin & Oh (2025), IEEE Transactions on Multimedia
- **Domain**: Multimodal Deep Learning & Cultural Analytics
- **Dataset**: 1,200 K-Pop Releases (2018–2025) with Audio Spectrograms, Multilingual Lyrics, and MV/Dance Challenge Pose Keypoints

## Abstract & Core Findings
1. **單一模態的瓶頸（Unimodal Bottleneck）**：
   - 如 Paper 01 指出，僅靠 Spotify 音訊表格特徵預測 K-Pop 熱門度，AUC 僅約 **0.74**，無法捕捉 K-Pop 作為「視聽整合產業（Audio-Visual Industry）」的核心競爭力。
2. **多模態特徵工程（Multimodal Feature Engineering）**：
   - **音訊模態（Audio Modality）**：Mel-Spectrogram（梅爾頻譜圖）搭配 CNN 提取音色變化率、副歌能量對比度（Chorus-to-Verse Energy Ratio）。
   - **歌詞模態（Lyric Modality）**：計算「英文歌詞佔比（English Ratio, 熱門曲平均達 38%–45%）」、「重複率（Lyric Repetition Compression Ratio）」與情感極性。
   - **視覺與編舞模態（Visual & Choreography Cues）**：透過 OpenPose / MediaPipe 提取副歌 15 秒舞蹈挑戰（Dance Challenge）的關節運動軌跡，計算 **「手部動作集中度（Upper-Body Gesture Ratio）」** 與 **「節拍對齊度（Beat-Movement Synchronization）」**。研究發現，上半身手勢清晰、適合直式手機螢幕拍攝的編舞（Point Choreography），其 TikTok 挑戰參與數是全身複雜走位編舞的 **3.4 倍**。
3. **模型融合與效能躍升**：
   - 結合 Audio + Lyrics + Choreography 的多模態融合模型（Multimodal Transformer），在預測「發行首月是否進入 Spotify Global 200 或產生病毒式擴散（Viral Hit）」任務上，AUC 達到 **0.91**（F1-score 0.86），較純音訊模型提升 **17 個百分點**。
