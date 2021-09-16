---
title: 不重複裝置
description: 不重複裝置數量。
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 407111f6016fe8595f1d5c3464e36dfd4d314630
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%

---

# 不重複裝置

「不重複裝置」量度是[跨裝置分析](../cda/overview.md)量度，會計算不重複未識別裝置和不重複虛擬裝置的數量。 未識別的裝置是產生匿名點擊的裝置。 不重複虛擬裝置是每個裝置所識別的不同人員。

## 此量度的計算方式

對於每部裝置，加總所有系結至該裝置的不重複人員（如果裝置包含未匯整的點擊，則包括匿名）。

請注意，此量度不等於非CDA報表套裝中的[獨特訪客](unique-visitors.md)。 例如，一個裝置由3個不同帳戶共用。 如果所有3個帳戶都在報告視窗中造訪您的網站，則產生的報告在CDA中會顯示3個不重複裝置。 CDA外的相同資料會顯示1個不重複訪客。

## 範例

1. Bob透過廣告進入您的網站，但未登入。
1. Bob想要購買，但因為他已登入家庭電腦，所以更想在家庭電腦上購買。 他在家用電腦上買東西。
1. 第二天，他用電話檢查命令，在那裡進行驗證。
1. Bob的妻子Alice在登錄家庭電腦的帳戶時瀏覽了你的網站。
1. Bob的弟弟Charles在家用電腦上登入其帳戶時，也瀏覽了您的網站。

![不重複裝置計數](/help/components/metrics/assets/Unique_Devices_Count.png)

在[重播](/help/components/cda/replay.md)之前在CDA虛擬報表套裝中檢視此資料，會顯示：

* **5個不重複裝置**:1個代表未驗證的Bob + 2個代表Bob + 1個代表Alice + 1個代表Charles
* **4 [人](people.md)**:1名 [未識別](unidentified-people.md) 者+ 3 [名已識別人員](identified-people.md)。

