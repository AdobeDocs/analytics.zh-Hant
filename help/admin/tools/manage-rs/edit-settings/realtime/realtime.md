---
description: 即時顯示網頁流量和排名頁面檢視次數。 提供可操作的資料，供您據以進行業務決策。
title: 即時報告
feature: Real-time
exl-id: 267246ba-617f-4284-aaad-d0ace0f6a8cf
TQID: https://experienceleague.adobe.com/SqFAddRYrXCrQyB-LjgsaLWoEQXMLc7hkdgcAcgUdsM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 611
ht-degree: 31%

---

# 即時報告

即時顯示網頁流量和排名頁面檢視次數。 提供可操作的資料，供您據以進行業務決策。

>[!NOTE]
>
>即時報表不需要進行額外的實施作業或標記。 它會運用您現有的 Adobe Analytics 實作。 若要設定即時報表，請參閱[即時報表設定](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)。

若要檢視即時報表，請導覽至：

**[!UICONTROL Workspace]** > **[!UICONTROL 報表]** > **[!UICONTROL 參與]** > **[!UICONTROL 即時]**。

請即時回答下列問題：我的網站有何趨勢、原因為何？ 它可讓您作為行銷人員快速回應並主動管理行銷內容和行銷活動的績效。 所報告的即時資料延遲時間少於兩分鐘，並會以分鐘為單位自動更新。

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

控制面板包含Adobe Analytics高頻量度和網站分析，以視覺化方式報告動態新聞和零售網站的流量和頁面檢視趨勢。 即時瞭解資料在收集後的數秒內從分鐘到分鐘的變化趨勢。 它會收集資料，並串流至自動更新UI中，使用即時關聯和追蹤內容及某些轉換。

以下為兩個常見的使用案例：出版商想隨著使用者活動改變而促銷/取消促銷故事；以及行銷人員想追蹤新產品線的上市。

作為管理員，您可以

* 使用現有的維度 (或分類) 與量度，為每個報告套裝建立最多 3 個即時報告。 使用次要維度來關聯主要維度（或劃分主要維度）。
* 每個報告新增3個維度（或分類） （一個主要和兩個次要），以及1個全網站量度。
* 使用任何自訂事件、購物車事件或例項。
* 檢視高達 2 小時的歷史即時資料，並修改此設定：

   * 前 15 分鐘：1 分鐘顆粒度
   * 前 30 分鐘：1 分鐘顆粒度
   * 前 1 小時：2 分鐘顆粒度
   * 前 2 小時：4 分鐘顆粒度

* 例如，比較上週的值以及去年的值（以及今天的總數）。

請記住，不支援eVar （轉換量度），因為沒有持續性的概念。 雖然您可以選取轉換量度，但只有在它們設定在與維度相同的頁面時，才能運作。 如需詳細資訊，請參閱[設定即時報表](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)中擷取的警告訊息。

設定和檢視即時報表僅限於管理員或「所有報表存取」和「進階報表」許可權群組中的任何使用者。 不過，「即時」確實會遵循許可權。 舉例來說，如果您沒有檢視收入的許可權，便無法檢視包含收入資料的即時報表。

## 由於A4T設定造成的資料延遲 {#latency}

在Adobe Target中啟用A4T整合後，您會在Adobe Analytics中遇到5至10分鐘的額外延遲。 增加此延遲可使Analytics和Target的資料透過相同的點選儲存，讓您能夠依頁面和網站區段劃分測試。

此延遲增加的現象會反映在所有 Adobe Analytics 服務和工具中 (包括即時資料流與即時報表)，且適用於下列情況：

* 對於即時資料流、即時報表和API請求，以及流量變數的目前資料，只有具有補充資料ID的點選會延遲。
* 對於轉換量度、最終完成的資料和資料摘要的目前資料，所有點選都會額外延遲5至7分鐘。

請注意，即使您尚未完全實施作業該整合，該延遲增加現象也會在您實施作業身分識別服務後開始。
