---
title: 演算法歸因
description: 演算法歸因模型的詳細資料。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
source-git-commit: 734eb409e7a433147c3536cebc571b38f87ce716
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 100%

---

# 演算法歸因

Analysis Workspace 中的演算法[歸因模型](models.md)與其他模型不同，因為此模型使用統計技術將評分分配給報表或自由表格中的各個維度項目。和 Analysis Workspace 中的所有其他歸因模型一樣，此模型也可用於任何維度或量度，並支援無限制的分段和劃分，且會將 100% 的轉換分送給表格中的維度 (也稱為「細節」歸因)。

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

用於歸因的演算法以合作賽局理論中的 Harsanyi 利益為基礎。Harsanyi 利益是 Shapley 值解法 (命名自諾貝爾經濟學獎得主 Lloyd Shapley) 的泛論，即在一場對結果貢獻不均等的賽局中，在玩家之間分配評分。

從高層面來看，在為每個接觸點計算轉換評分的歸因時，會將回顧期間內的每個行銷接觸點視為必須均等分配盈餘的玩家聯盟。每個聯盟的盈餘分配則根據每個子聯盟先前產生的盈餘 (或先前參與的維度項目) 遞迴決定。如需詳細資訊，請參閱 John Harsanyi 和 Lloyd Shapley 的原稿：

* Shapley, Lloyd S. (1953)。A value for n-person games。*Contributions to the Theory of Games, 2(28)*, 307-317。
* Harsanyi, John C. (1963)。A simplified bargaining model for the n-person cooperative game。*International Economic Review 4(2)*, 194-220。

>[!NOTE]
>
>只有在給定回顧期間內多個接觸點存在時，演算法歸因的結果才會與其他模型不同。無論歸因模型為何，單一接觸點的轉換都會獲得 100% 的評分。
