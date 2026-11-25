# Paper 01: Hit Song Science (HSS) & Acoustic Features in Popular Music
- **Authors**: Pachet & Roy (2008), Askin & Mauskapf (2017), Middlebrook & Sheik (2019), Falah (2025) — Synthesized MIR Literature
- **Domain**: Music Information Retrieval (MIR) / Hit Song Science (HSS)
- **Dataset**: Spotify Web API Audio Features (27,000 Billboard Hot 100 tracks & 1.8M Spotify tracks)

## Abstract & Core Findings
1. **定義與假設**：Hit Song Science (HSS) 旨在於歌曲發行前，透過聲學訊號與音訊特徵預測其商業成功（進榜機率或串流熱門度）。核心假設為「熱門歌曲在聲學特徵空間中具有高度相似的群聚特性」。
2. **Spotify 關鍵音訊特徵（Audio Features）**：
   - **Danceability（可舞性, 0.0–1.0）**：綜合節拍穩定度（Beat Strength）、速度（Tempo）與律動規律性，對流行榜單呈顯著正相關。
   - **Energy（能量值, 0.0–1.0）**：感知強度與活躍度（響度、頻譜複雜度），流行舞曲通常落於 0.65–0.85 區間。
   - **Valence（情緒正向度, 0.0–1.0）**：高數值代表愉悅、積極；低數值代表憂鬱、暗黑。
   - **Acousticness（原聲程度, 0.0–1.0）**：與串流熱門度呈顯著負相關（現代主流流行樂高度依賴電子合成器與數位編曲）。
   - **Loudness（響度, dB）**：現代熱門歌曲普遍呈現高響度（-6 dB 至 -4 dB，俗稱 Loudness War）。
3. **機器學習模型表現與限制**：
   - 使用 Random Forest 與 SVM 分類 Billboard Hot 100 進榜與否，準確率可達 **85%–88%**（顯著優於隨機猜測）。
   - **關鍵局限（Limitation）**：若僅使用純音訊特徵進行回歸預測（如 Nijkamp, 2018），解釋力 $R^2$ 僅約 **20.2%**；一旦加入「藝人歷史聲量（Artist Popularity / Followers）」與「發行時間效應」，預測準確率與解釋力大幅躍升。這證明了「好聽的音訊結構是入場券，但非唯一決定因素」。
