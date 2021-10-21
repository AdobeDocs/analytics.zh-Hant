---
title: 使用者
description: 不重複個人 (通常使用多個裝置) 的數量。
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 80%

---

# 使用者

「使用者」量度有兩個版本。

對於未使用[跨裝置分析](../cda/overview.md)的 [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=zh-Hant) 會員，「使用者」量度指的是將報表中呈現的人數予以統計拚接後所得到的數目。 此量度等於 Device Co-op 已辨識出之訪客 ID 的數目，加上該 Co-op 未辨識出之裝置的數目。

在一個「[跨裝置分析](../cda/overview.md)」的虛擬報表套裝中，「使用者」量度並非一種統計推演的結果。反之，此量度是報表中辨識出的個人的總和，外加無法辨識出屬於哪個使用者的裝置的數量。

如果在造訪期間識別了訪客，該訪客可計為2人（1個未識別的人和1個已識別的人）。 [重播](/help/components/cda/replay.md) 根據報告視窗、重播頻率和成功率，可減少重複計數的現象。 如需詳細資訊，請參閱「[不重複裝置](unique-devices.md)」。
