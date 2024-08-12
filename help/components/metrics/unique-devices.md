---
title: 不重複裝置
description: 不重複裝置數量。
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 16a9c9a2b6692b9b1944cfdb9b5b0411d48db666
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 73%

---

# 不重複裝置

「不重複裝置」[量度](overview.md)是計算獨特、未識別裝置和獨特虛擬裝置數的[跨裝置分析](../cda/overview.md)量度。 未識別裝置指產生匿名點擊的裝置。獨特的虛擬裝置指依裝置識別的不同使用者。

## 此量度的計算方式

針對每個裝置，將所有與其相關聯的不同使用者 (如果裝置包含非拼接點擊，則包括匿名) 相加。

請注意，該量度並不等於非 CDA 報表套裝中的[不重複訪客](unique-visitors.md)。例如，單一裝置由 3 個不同的帳戶共用。如果所有3個帳戶都在報表時段中造訪您的網站，則產生的報表會在CDA中顯示3個不重複裝置。 CDA 之外的相同資料將顯示 1 個不重複訪客。

## 範例

1. Sally透過廣告透過電話造訪您的網站，但未登入。
1. Sally 想要購物，但比較希望在家中電腦上下單，因為她已經從那裡登入了。 她在家中電腦上完成了購物。
1. 第二天，她在手機上檢視訂單並進行身分驗證。
1. Bob 的妻子 Alice 從這台家用電腦登入她的帳戶時瀏覽了您的網站。
1. Bob 的弟弟 Charles 從同一台家用電腦登入他的帳戶時也瀏覽了您的網站。

![不重複裝置計數](/help/components/metrics/assets/Unique_Devices_Count.png)

在[重播](/help/components/cda/replay.md)可能拼接前，若在 CDA 虛擬報表套裝中檢視此資料，未經驗證的點擊將會顯示:

* **5 個不重複裝置**：1 個來自未經驗證的 Bob + 2 個來自 Bob + 1 個來自 Alice + 1 個來自 Charles
* **4 個[使用者](people.md)**：1 個[未識別的使用者](unidentified-people.md) + 3 個[已識別的使用者](identified-people.md)。
