---
description: 了解如何使用警報，以便對通知進行精細控制，並與異常偵測整合。
title: 警報概觀
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 96%

---

# 警報概觀

Adobe Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知。

根據您的 Adobe Analytics 套件，您還可以使用根據異常臨界值觸發的警報。這些警報 (也稱為「智慧型警報」) 提供整合[異常偵測](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md)的精細控制，可在您最需要時觸發。

警報可讓您：

* 預覽警報觸發的頻率
* 透過電子郵件或簡訊傳送警報，當中附有可自動產生 Analysis Workspace 專案的連結
* 建立在單一警報中擷取多個量度的「堆疊」警報
* 根據異常情況建置警報 (90%、95%、99%、99.75% 和 99.9% 臨界值；百分比變更；高於/低於)(僅適用於擁有 Select、Prime 或 Ultimate 套件的 Adobe Analytics 客戶)

下列影片教學課程提供警示的基本概觀： [警示](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html) (5:34)

## 警報的異常回顧

>[!NOTE]
>
>僅擁有 Adobe Analytics Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為&#x200B;_智慧型警報_)。

如果警報使用異常偵測，訓練期會依您為警報選擇的詳細程度而有所不同。

* 每月詳細程度：15 個月 + 去年的相同範圍
* 每週詳細程度：15 週 + 去年的相同範圍
* 每日詳細程度：35 天 + 去年的相同範圍
* 每小時詳細程度：336小時

如需更多資訊，請參閱[用於異常偵測統計技術](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)。

## 建立警報

如需有關如何在 Adobe Analytics 中建立警報的資訊，請參閱[建立警報](/help/components/alerts/alert-builder.md)。

>[!IMPORTANT]
>
>使用時間戳記資料建立警報，可能導致錯誤觸發警報。Adobe 建議您為警報使用非時間戳記資料。

## 管理警報

您可以在警報管理器中管理現有警報。您可以對警報執行各種管理任務，例如標記、重新命名、刪除等。

如需有關如何管理 Adobe Analytics 中現有警報的更多資訊，請參閱[管理警報](/help/components/alerts/alert-manager.md)。
