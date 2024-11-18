---
description: 警報可讓您精細地控制通知，並整合異常偵測。
title: 警報概觀
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: e5f832bcedfa1c483fb31f5cff733bad4ed85be1
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 32%

---

# 警報概觀

Adobe Analytics中的警報可讓您根據變更的百分比或特定資料點收到通知。

視您的Adobe Analytics套件而定，您也可以使用要根據異常臨界值觸發的警報。 這些警報（也稱為「智慧型警報」）提供與[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)整合的精細控制項，在您最需要時觸發。

警示可讓您：

* 預覽警報觸發的頻率
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結
* 建立在單一警報中擷取多個量度的「堆疊」警報
* 根據異常（90%、95%、99%、99.75%和99.9%臨界值；%變更；以上/以下）建立警報(僅適用於擁有Select、Prime或Ultimate套件的Adobe Analytics客戶)

下列影片教學課程提供警示的基本概觀： [警示](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## 警報的異常回顧

>[!NOTE]
>
>使用具有異常偵測的警報（也稱為&#x200B;_智慧型警報_）僅適用於具有Adobe Analytics Prime或Ultimate套件的組織。

如果警報使用異常偵測，訓練期會依您為警報選擇的粒度而有所不同。

* 每月粒度：15 個月 + 去年的相同範圍
* 每週粒度：15 週 + 去年的相同範圍
* 每日粒度：35 天 + 去年的相同範圍
* 每小時粒度：336小時

如需詳細資訊，請參閱[異常偵測所使用的統計技術](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在Adobe Analytics中建立警示的資訊，請參閱[建立警示](/help/components/c-alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe建議對警報使用非時間戳記資料。

## 管理警報

您可以在「警報管理員」中管理現有警報。 您可以對警示執行各種管理工作，例如標籤、重新命名、刪除等等。

如需有關如何在Adobe Analytics中管理現有警示的詳細資訊，請參閱[管理警示](/help/components/c-alerts/alert-manager.md)。
