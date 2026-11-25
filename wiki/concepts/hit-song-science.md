# Concept: 熱門歌曲科學 (Hit Song Science, HSS)

**熱門歌曲科學（Hit Song Science, HSS）** 是音樂資訊檢索（MIR）領域的重要分支，旨在透過機器學習與訊號處理技術，於歌曲正式發行前，從音訊特徵與結構中預測其未來的商業成功機率。

## 核心理論與假設
- **聲學群聚假設（Acoustic Clustering Hypothesis）**：人類大眾的聽覺審美在特定時期具有統計規律性，熱門歌曲會在 [[entities/spotify-audio-features]] 構成的多維空間中聚集於特定區域。
- **效能與局限（見 [[sources/paper-01-hss]]）**：
  - 在「進榜 vs. 未進榜」二元分類中，機器學習模型可達 **85%–88%** 準確率。
  - 然而，音樂消費深受社群演算法、藝人知名度與視覺文化影響，純音訊特徵對串流量的回歸解釋力僅有 **$R^2 = 20.2\%$**。因此，針對 K-Pop 這類高度視覺化的產業，必須進一步結合 [[concepts/kpop-song-structure]] 與 [[concepts/multimodal-hit-prediction]]。
