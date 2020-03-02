---
description: 'null'
title: 演算法歸因
uuid: bb345642-4f45-4fb8-82d0-803248dd52ea
translation-type: tm+mt
source-git-commit: b5418e6321b09ddbab36e0052f75f36067086e3e

---


# 演算法歸因

![演算法](assets/algorithmic.png)

分析工 [作區中的演算法歸因模型](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html#attribution-models) ，與歸因IQ中的其他模型不同，它使用統計技術在報表或自由表格的維度值間分配評分。 和分析工作區中的所有其他歸因模型一樣，它可用於任何維度或度量，並支援無限制的分段和劃分，並將100%的轉換分發至表格中的維度（也稱為「分數」歸因）。

基於合作博弈論的Harsanyi Danyis算法用于歸因。 哈薩尼派息是對沙普利價值解（以諾貝爾經濟學獎得主勞埃德·沙普利命名）的概括，即在一場對結果貢獻不均的遊戲中，在玩家之間分配信用。

在高層面上，每個觸點的轉換信用的歸因計算將回顧窗口內的每個營銷觸點視為必須公平分配盈餘的玩家聯盟。 每個聯盟的盈餘分配是根據每個子聯盟先前建立的盈餘（或先前參與的維度值）遞歸決定。 如需詳細資訊，請參閱John Harsanyi和Lloyd Shapley的原稿：

* 沙普利，勞埃德·S。「n人遊戲的價值。」 對博弈論的貢獻2.28(1953):307-317。

* Harsanyi, John C.「n人合作博弈的簡化談判模式。」 《國際經濟評論》 4.2(1963):194-220。

*注意：演算法歸因的結果只有在特定回顧視窗中存在多個觸點時，才會與其他模型不同。 例如，只有單一觸點時，無論選取的歸因模型為何，都會將100%的評分分配給該值。*