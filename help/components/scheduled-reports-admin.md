---
description: 讓管理員層級使用者查看與管理組織中的排程報表。
title: 排程報告佇列
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705cid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 51%

---

# 排程報告佇列

讓管理員層級使用者查看與管理組織中的排程報表。

**[!UICONTROL Analytics]** > **[!UICONTROL 元件]** > **[!UICONTROL 所有元件]** > **[!UICONTROL 排程報表]**

「排程報表管理員」中的管理層級功能包含：

* [顯示組織中所有排程報告](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690)的選項。
* 整個組織中的[進階篩選功能](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275)。
* 新的[報告佇列](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B)索引標籤會列出在報告伺服器上排入佇列等待執行的所有報告。
* 在報表佇列介面中公開[排程ID](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1)。

## 顯示所有排程報告 {#section_3F167CAAEEC24140B476CF95B7402690}

在&#x200B;**[!UICONTROL 報表清單]**&#x200B;索引標籤上，除了您私人排程的報表，您還可以&#x200B;**[!UICONTROL 顯示組織中所有已排程報表]**。

>[!NOTE]
>
>**[!UICONTROL 報表名稱]**&#x200B;欄會顯示正在排程的報表名稱，而&#x200B;**[!UICONTROL 檔案名稱]**&#x200B;欄則會顯示您在「進階傳送選項」中所設定的所有自訂檔案名稱。 因此，如果您排程多個相同報表型別的報表，並為每個報表指定自訂名稱，則「排程報表管理員」會顯示多個報表名稱相同但檔案名稱不同的專案。 這是因為排程的後端報表是相同的，因此「報表名稱」欄除了自訂檔案名稱（如設定）之外，其他所有名稱都將具有相同的報表名稱。

![](assets/show_all_scheduled_reports.png)

## 進階篩選功能 {#section_206A52A85DE84947AAB3AD082FBF6275}

例如，如果您要篩選所有排程為每小時執行的報表，可在&#x200B;**[!UICONTROL 進階]**&#x200B;篩選器中指定&#x200B;**[!UICONTROL 頻率等於每小時]**，然後按一下&#x200B;**[!UICONTROL 套用]**：

![](assets/advanced_filtering_schedl_reports.png)

## 報表佇列 {#section_03C866115D354BB182E90BF4D52F1E0B}

此佇列可讓您管理或可能刪除佇列中「塞滿」的任何排程報告。 （通常報表會在4小時後逾時）。

![](assets/scheduled_reports_2.png)

「報表佇列」也可讓您「略過一次排程報表」。 只需按一下&#x200B;**[!UICONTROL 「管理」]**&#x200B;欄中的藍色圖示。

## 排程 ID {#section_568B70F4228C4229977CB85D2DCD53A1}

當您需要聯絡 Adobe 客戶服務來解決排程報表問題時，「報表佇列」介面中公開的&#x200B;**[!UICONTROL 排程 ID]** 可提供協助。

![](assets/schedule_id.png)
