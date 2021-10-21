---
title: 不重複裝置
description: 不重複裝置數量。
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 93%

---

# 不重複裝置

「不重複裝置」量度指計算獨特、未識別裝置和獨特虛擬裝置的「[跨裝置分析](../cda/overview.md)」量度。未識別裝置指產生匿名點擊的裝置。獨特的虛擬裝置指依裝置識別的不同使用者。

## 此量度的計算方式

針對每個裝置，將所有與其相關聯的不同使用者 (如果裝置包含非拼接點擊，則包括匿名) 相加。

請注意，該量度並不等於非 CDA 報表套裝中的[不重複訪客](unique-visitors.md)。例如，單一裝置由 3 個不同的帳戶共用。如果所有 3 個帳戶都在報表時段中造訪您的網站，則所產生的報告將顯示 CDA 中的 3 個不重複裝置。CDA 之外的相同資料將顯示 1 個不重複訪客。

## 範例

1. Bob 透過廣告從他的手機造訪您的網站，但未登入。
1. Bob 想要進行購物，但比較希望在家用電腦上下單，因為他已經從那裡登入了。在家用電腦上，他完成了購物。
1. 第二天，他在手機上查看訂單和進行身份驗證。
1. Bob 的妻子 Alice 從這台家用電腦登入她的帳戶時瀏覽了您的網站。
1. Bob 的弟弟 Charles 從同一台家用電腦登入他的帳戶時也瀏覽了您的網站。

![不重複裝置計數](/help/components/metrics/assets/Unique_Devices_Count.png)

先前在CDA虛擬報表套裝中檢視此資料 [重播](/help/components/cda/replay.md) 未驗證的點擊可能會顯示：

* **5 個不重複裝置**：1 個來自未經驗證的 Bob + 2 個來自 Bob + 1 個來自 Alice + 1 個來自 Charles
* **4 個[使用者](people.md)**：1 個[未識別的使用者](unidentified-people.md) + 3 個[已識別的使用者](identified-people.md)。
