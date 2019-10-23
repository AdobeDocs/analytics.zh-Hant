---
description: 新的智慧型警報系統可提供更細微的警報控制能力，並可與警報系統的異常偵測整合。
seo-description: 新的智慧型警報系統可提供更細微的警報控制能力，並可與警報系統的異常偵測整合。
seo-title: 智慧型警報概觀
title: 智慧型警報概觀
uuid: b9bf75ad-bb6f-49fe-8c55-355ea3c50a71
translation-type: tm+mt
source-git-commit: ca9f1ed00295b556250894ae4e7fa377ef8a593d

---


# 智慧型警報概觀

智慧型警報可讓您更精細地控制警報，並將異常偵測與警報系統整合。

[YouTube上的智慧提醒](https://www.youtube.com/watch?v=UVH9xr_2REA) (5:34)

## 概述

Analysis Workspace 中的新「警報產生器」和「警報管理器」取代了「Reports &amp; Analytics」中的現有警報功能。智慧型警報可讓您:

* 根據異常（90%、95%、99%、99.75%和99.9%臨界值）建立警報；%變更；上／下)
* 預覽警報觸發頻率
* 透過電子郵件或簡訊傳送警報，並附上自動產生的分析工作區專案連結
* 建立「堆疊」警報，以在單一警報中擷取多個量度

取得「警報產生器」有四種方式:

* 直接前往警報產生器： 元 **[!UICONTROL 件]** &gt;警 **[!UICONTROL 報]**
* 使用工作區中的鍵盤快速鍵： `Ctrl + Shift + A` (Windows) `Cmd + Shift + A` 或(Mac)
* Selecting one or more freeform table line item/s, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**. 這會開啟警報產生器，並預先填入表格中套用的適當度量和篩選。 您可以視需要編輯警報。

   ![從選取範圍建立警報](assets/create-alert-from-selection.png)

* From within a Reports &amp; Analytics report, by going to  **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]** . 這會開啟警報產生器，並預先填入從報表套用的適當度量和篩選器。 您可以視需要編輯警報。

   ![新增警報](assets/add-alert.png)

百分比臨界值是標準差。 例如，95% = 2 標準差與 99% = 3 標準差。依您選擇的時間粒度而定，[不同模式](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md)會用於計算各資料點距離基準有多遠 (多少標準差)。如果您設定較低的臨界值（例如90%），則會比設定較高臨界值(99.75%)時出現更多異常。

> [!IMPORTANT] 使用時間戳記資料建立警報可能會造成警報觸發錯誤。 Adobe建議智慧型警報使用非時間戳記資料。

## 警報的異常回顧

如果警報使用異常偵測，則訓練期間會根據為警報選取的詳細程度而有所不同。

* 每月詳細程度：去年15個月+相同範圍
* 每週詳細程度：去年15週+相同範圍
* 每日詳細程度：去年35天+相同範圍
* 每小時詳細程度：336小時

See [Statistical techniques used in Anomaly Detection](../virtual-analyst/c-anomaly-detection/statistics-anomaly-detection.md) for more information.
