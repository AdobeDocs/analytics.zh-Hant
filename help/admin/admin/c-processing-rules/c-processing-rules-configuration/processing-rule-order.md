---
description: 處理規則位於總體分析資料管道中的位置。
subtopic: Processing rules
title: 處理順序
feature: Processing Rules
exl-id: c7143527-017c-4550-b55e-09ea437d7c85
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 52%

---

# 處理順序

為了有效地使用處理規則，必須瞭解在資料收集過程中應用這些規則的時間。

![處理順序](assets/analytics_processing_order.png)

下表列出套用處理規則之前和之後通常可用的資料.

## 處理規則之前

| 維度 | 說明 |
|--- |--- |
| [動態變數](/help/implement/vars/page-vars/dynamic-variables.md) | 通過從HTTP標頭或其他變數中提取資訊動態填充的變數。 |
| [AppMeasurement](/help/implement/home.md) | 在AppMeasurement庫中使用的函式和插件在瀏覽器或客戶端應用程式中執行。 |
| [標籤實現](/help/implement/launch/overview.md) | 在Adobe Analytics擴展中定義的Adobe Experience Platform資料收集中的規則。 |
| [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/adobe-analytics/analytics-overview.html) | 通過Web SDK收集的資料會發送到Adobe Experience Edge，然後轉發到所需的報告套件。 |
| [機器人規則](/help/admin/admin/bot-removal/bot-rules.md) | 讓您刪除已知蜘蛛和機器人生成的流量。 |

## 處理規則之後

| 維度 | 說明 |
|--- |--- |
| VISTA 新增的資料 | 處理規則的套用時機早於 VISTA。 |
| 瀏覽頁碼 | 處理規則只知道當前命中中包含的資料。 瀏覽頁碼是在套用處理規則之後才進行編譯的。 |
| 若未設定頁面名稱，則會新增「簡潔 URL」作為頁面名稱 | 套用處理規則和 VISTA 後，若未設定頁面名稱，則會新增簡潔 URL 作為頁面名稱。由於此邏輯在應用處理規則後發生，Adobe建議添加一個條件以檢查頁名是否為空。  如果運行 **[!UICONTROL 站點內容]** > **[!UICONTROL 頁面]** 報告後，您會看到頁名的URL值，頁名變數可能為空。  您可以設定條件來test空頁名，或設定條件來test頁名或頁URL是否包含特定值。 接著就可以視需要設定頁面名稱。 |
| 行銷管道處理規則 | 您可以使用處理規則來準備資料，以供[「行銷管道處理規則」](https://experienceleague.adobe.com/docs/analytics/components/marketing-channels/c-rules.html)處理。 |
| GEO 查閱 | 包括訪問者狀態和訪問者ZIP/郵遞區號值。 |
| eVar 保存 | 前次點擊中包含的 eVar 在規則處理期間不會保存給每個點擊。只有設定給正在處理之目前點擊的 eVar 可供使用。 |

## 使用 VISTA 複製點擊時處理規則的套用方式

如果您有設定 VISTA 規則來複製對其他報表套裝的點擊，則會透過該報表套裝中定義的任何處理規則來傳送點擊。

如果您在原始報告套件上定義了處理規則，則這些規則可能會應用，也可能不會應用，具體取決於工程服務配置VISTA規則的方式。 若想得知，請詢問您的實作專家 VISTA 規則是複製「前」或「後」值至其他報表套裝。如果是複製「前」值，則不會套用原始報表套裝上定義的處理規則。如果是複製「後」值，則會在複製點擊之前套用處理規則。
