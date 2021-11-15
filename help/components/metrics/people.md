---
title: 使用者
description: 不重複個人 (通常使用多個裝置) 的數量。
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 639897682c9a28df7dc642dd7c68ad992fde40a9
workflow-type: ht
source-wordcount: '161'
ht-degree: 100%

---

# 使用者

「使用者」量度有兩個版本。

對於未使用[跨裝置分析](../cda/overview.md)的 [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=zh-Hant) 會員，「使用者」量度指的是將報表中呈現的人數予以統計拚接後所得到的數目。 此量度等於 Device Co-op 已辨識出之訪客 ID 的數目，加上該 Co-op 未辨識出之裝置的數目。

在一個「[跨裝置分析](../cda/overview.md)」的虛擬報表套裝中，「使用者」量度並非一種統計推演的結果。反之，此量度是報表中辨識出的個人的總和，外加無法辨識出屬於哪個使用者的裝置的數量。

如果系統在訪客造訪中才將其辨識出來，則可能將該訪客計算為 2 個使用者 (1 個未識別的使用者和 1 個已識別的使用者)。[重播](/help/components/cda/replay.md)會依據報表時段、重播頻率和成功率的不同來減少這種重複計算的情況。如需詳細資訊，請參閱「[不重複裝置](unique-devices.md)」。
