---
title: 行動生命週期量度
description: 此量度是以使用 Mobile SDK 收集之資料為基礎。
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# 行動生命週期量度

>[!BEGINSHADEBOX]

*此頁面參考了經常透過Adobe Experience Platform Mobile SDK追蹤的資料。 如需使用行動SDK追蹤的維度，請參閱[行動生命週期維度](../dimensions/lifecycle-dimensions.md)。 如需使用使用者代理程式的行動裝置資訊，請參閱[行動查詢維度](../dimensions/mobile-dimensions.md)。*

>[!ENDSHADEBOX]

| 生命週期量度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| **[!UICONTROL 首次啟動]** | 應用程式在安裝或重新安裝後首次執行的次數。 | `a.InstallEvent` |
| **[!UICONTROL 升級]** | 應用程式在升級後或版本號碼變更後的首次執行次數。 | `a.UpgradeEvent` |
| **[!UICONTROL 啟動]** | 應用程式執行的次數，包括當機和安裝後的執行次數。 在超過生命週期工作階段逾時後，應用程式從背景恢復時，也會計算啟動次數。 | `a.LaunchEvent` |
| **[!UICONTROL 當機]** | 應用程式在關閉前當機的次數。 下次啟動應用程式時就會回報當機。 | `a.CrashEvent` |
| **[!UICONTROL 工作階段長度總計]** | 應用程式工作階段持續的總秒數，根據應用程式在背景中開啟的時間長短而定。 每個啟動都會報告上一個工作階段的長度；此量度是這些值的總和。 | `a.PrevSessionLength` |
| **[!UICONTROL 動作時間總計]** | 跨工作階段計時動作開始與結束之間的總秒數（時鐘時間）。 由舊版Mobile Services SDK (4.x)中的`trackTimedAction`方法填入。 | `a.action.time.total` |
| **[!UICONTROL 應用程式中的動作時間]** | 從計時動作開始到結束期間跨工作階段在應用程式中逗留的秒數。 由舊版Mobile Services SDK (4.x)中的`trackTimedAction`方法填入。 | `a.action.time.inapp` |
| **[!UICONTROL 期限值 (事件)]** | 使用者的期限值，例如期限購買、廣告檢視、視訊完成或社交分享。 由舊版Mobile Services SDK (4.x)中的`trackLifetimeValueIncrease`方法填入。 | `a.ltv.amount` |

>[!NOTE]
>
>[!UICONTROL 動作時間總計]、[!UICONTROL 應用程式中的動作時間]以及[!UICONTROL 期限值（事件）]量度是由舊版Mobile Services SDK (4.x)中的方法填入，這些方法已不再受支援。 Adobe Experience Platform Mobile SDK不會自動填入這些量度。 如需計時動作和期限值追蹤的替代方案，請參閱[Adobe Mobile Library (v4)移轉至Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)。
