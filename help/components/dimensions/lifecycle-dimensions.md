---
title: 行動生命週期維度
description: 以使用行動SDK收集的資料為依據的維度。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# 行動生命週期維度

>[!BEGINSHADEBOX]

*此頁面參考了經常透過Adobe Experience Platform Mobile SDK追蹤的資料。 如需使用使用者代理程式的行動裝置資訊，請參閱[行動查詢維度](mobile-dimensions.md)。 如需使用行動SDK追蹤的量度，請參閱[行動生命週期量度](../metrics/lifecycle-metrics.md)。*

>[!ENDSHADEBOX]

| 生命週期維度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| **[!UICONTROL 首次啟動日期]** | 應用程式安裝或重新安裝後首次執行的日期（以`M/d/yyyy`格式）。 | `a.InstallDate` |
| **[!UICONTROL 裝置名稱(SDK)]** | SDK收集的裝置名稱。 | `a.DeviceName` |
| **[!UICONTROL 作業系統版本(SDK)]** | SDK收集的作業系統名稱和版本。 | `a.OSVersion` |
| **[!UICONTROL 解析度(SDK)]** | 裝置的熒幕解析度（以畫素為單位），例如寬度x高度。 | `a.Resolution` |
| **[!UICONTROL 贏取Source]** | 應用程式贏取促銷活動的原始反向連結，例如電子報或社群媒體網路。 | `a.referrer.campaign.source` |
| **[!UICONTROL 應用程式ID]** | 應用程式名稱和版本，格式為`AppName BundleVersion (app version code)`。 例如，`MyAppName 1.1(1)`。 | `a.AppID` |
| **[!UICONTROL 贏取Medium]** | 應用程式贏取促銷活動的行銷媒體，例如橫幅或電子郵件。 | `a.referrer.campaign.medium` |
| **[!UICONTROL 贏取詞語]** | 與應用程式贏取促銷活動相關聯的付費關鍵字或其他詞語。 | `a.referrer.campaign.term` |
| **[!UICONTROL 贏取內容]** | 顯示應用程式贏取連結之內容的名稱或ID。 | `a.referrer.campaign.content` |
| **[!UICONTROL 贏取名稱]** | 應用程式贏取促銷活動的名稱。 | `a.referrer.campaign.name` |
| **[!UICONTROL 位置 (10 公里以內)]** | 訪客的經緯度，精確到小數點後的第一位。 例如，`040.9` `-111.9`。 | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL 位置 (100 公尺以內)]** | 訪客的經緯度，精確至小數點後的第三位。 例如，`040.932` `-111.931`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL 位置 (1 公尺以內)]** | 訪客的經緯度，精確到小數點後的第五位。 例如，`040.93231` `-111.93152`。 | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL 興趣點名稱]** | 裝置所在之地標(POI)的名稱。 當您使用[Places擴充功能](https://developer.adobe.com/client-sdks/solution/places/)時，此值是Places區域名稱。 | `a.loc.poi` |
| **[!UICONTROL 至興趣點中心的距離]** | 裝置與裝置所在地標中心之間的距離。 | `a.loc.dist` |
| **[!UICONTROL 啟動次數]** | 應用程式啟動或移出背景的次數。 | `a.Launches` |
| **[!UICONTROL 首次使用後間隔天數]** | 自應用程式首次執行以來的天數。 | `a.DaysSinceFirstUse` |
| **[!UICONTROL 動作名稱]** | 在`trackAction`呼叫中傳送的動作名稱。 | `a.action` |
| **[!UICONTROL 期限值(evar)]** | 使用者的期限值，例如期限購買、廣告檢視、視訊完成或社交分享。 | `a.ltv.amount` |
| **[!UICONTROL 主要信標]** | 裝置附近信標的主要ID。 | `a.beacon.major` |
| **[!UICONTROL 次要信標]** | 裝置附近的信標的次要ID。 | `a.beacon.minor` |
| **[!UICONTROL 信標UUID]** | 裝置附近信標的UUID。 | `a.beacon.uuid` |
| **[!UICONTROL 鄰近地區信標]** | 裝置接近信標的情形： `0` （未知）、`1` （立即）、`2` （近）或`3` （遠）。 | `a.beacon.prox` |
| **[!UICONTROL 上次使用後間隔天數]** | 自應用程式上次使用以來的天數。 | `a.DaysSinceLastUse` |
| **[!UICONTROL 小時(SDK)]** | 應用程式啟動的時間（24小時制）。 時間分段可用於判斷尖峰使用時間。 | `a.HourOfDay` |
| **[!UICONTROL 星期(SDK)]** | 應用程式在一週中的哪一天啟動。 | `a.DayOfWeek` |
| **[!UICONTROL 興趣點ID]** | 裝置所在之地標的ID。 當您使用[Places擴充功能](https://developer.adobe.com/client-sdks/solution/places/)時，此值是Places地區ID。 | `a.loc.poi.id` |

>[!NOTE]
>
>其中部分維度會由舊版Mobile Services SDK (4.x)中的方法填入，已不再支援。 Adobe Experience Platform Mobile SDK不會自動填入：
>
>* **贏取維度** （[!UICONTROL 贏取Source]、[!UICONTROL Medium]、[!UICONTROL Term]、[!UICONTROL Content]和[!UICONTROL Name]）：由行動應用程式贏取填入，行動SDK [不支援](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/)。
>* **[!UICONTROL 位置]維度和[!UICONTROL 至興趣點中心的距離]**：由4.x `trackLocation`方法填入。 行動SDK以[Places擴充功能](https://developer.adobe.com/client-sdks/solution/places/)取代此方法，此擴充功能會填入[!UICONTROL 興趣點名稱]和[!UICONTROL 興趣點ID]。
>* **[!UICONTROL 期限值(evar)]**：由4.x `trackLifetimeValueIncrease`方法填入。
>* **信標維度** （[!UICONTROL 信標Major]、[!UICONTROL Minor]、[!UICONTROL UUID]和[!UICONTROL Proximity]）：由4.x `trackBeacon`方法填入。 若要使用行動SDK傳送信標資料，請參閱[追蹤信標](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/)。
>
>如需詳細資訊，請參閱[Adobe Mobile Library (v4)移轉至Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/)。
