---
description: 即時顯示網頁流量和排名頁面檢視。提供可操作的資料，供您據以進行業務決策。
seo-description: 即時顯示網頁流量和排名頁面檢視。提供可操作的資料，供您據以進行業務決策。
seo-title: 即時報表概觀
solution: Analytics
title: 即時報表概觀
topic: 報表
uuid: ff832952-c507-4c63-9437-25d9c44c44d1
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 即時報表概觀

即時報告會顯示網頁流量並即時排名頁面檢視。 提供可操作的資料，供您據以進行業務決策。

>[!NOTE]
>
>即時報表不需要額外實施或標籤。 它會運用您現有的 Adobe Analytics 實施。若要設定即時報告，請參閱 [即時報告設定](/help/components/c-real-time-reporting/t-realtime-admin.md).

**[!UICONTROL 網站量度]** &gt; **[!UICONTROL 即時]**

請即時回答下列問題: 我的網站有何趨勢、原因為何? 它可讓身為行銷人員的您，迅速回應、積極管理行銷內容和促銷活動的效能。所報告的即時資料延遲不超過兩分鐘，並且每分鐘自動更新一次。

![](assets/report-realtime.png)

儀表板包含 Adobe Analytics 高頻率量度及網站分析，可將動態消息和零售網站的報告流量及頁面檢視趨勢視覺化。可讓您了解資料中每一分鐘的即時趨勢，在收集資料後幾秒鐘內即可提供。它使用即時關聯並追蹤內容與部分轉換，收集並串流資料至自動更新的 UI。

以下為兩個常見的使用案例: 出版商想隨著使用者活動改變而促銷/取消促銷故事；以及行銷人員想追蹤新產品線的上市。

身為管理員，您可以

* 使用現有的維度 (或分類) 與量度，為每個報表套裝建立最多 3 個即時報告。使用次要維度關連至 (或劃分) 主要維度。
* 每個報告新增 3 個維度 (或分類) (一個主要和兩個次要)，以及新增 1 個全網站量度。
* 可使用任何自訂事件、購物車事件或是例項。
* 檢視高達 2 小時的歷史即時資料，並修改此設定:

   * 前 15 分鐘: 1 分鐘詳細程度
   * 前 30 分鐘: 1 分鐘詳細程度
   * 前 1 小時: 2 分鐘詳細程度
   * 前 2 小時: 4 分鐘詳細程度

* 舉例來說，可以比較上週的值和去年的值 (以及今日總計)。

請記住由於沒有持續性的概念，所以不支援 eVar (轉換量度)。當您可以選取轉換量度時，必須將轉換量度設定在維度的相同頁面上，轉換量度才能運作。有關詳細資訊，請參閱 設 [定即時報表](/help/components/c-real-time-reporting/t-realtime-admin.md)。

只有管理員或「完全報告存取」和「進階報告」權限群組中的使用者才能設定和檢視即時報告。不過，即時報告遵守權限。舉例來說，如果您沒有查看收入的權利，您便無法檢視包含收入資料的即時報告。

## 因為 A4T 設定造成的資料延遲 {#section_806CE36354FC4C539A0DED9266A5C704}

After the A4T integration is enabled in Adobe [!DNL Target], you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and [!DNL Target] to be stored on the same hit, allowing you to break down tests by page and site section.

此延遲增加的現象會反映在所有 Adobe Analytics 服務和工具中 (包括即時資料流與即時報表)，且適用於下列情況:

* 若是即時資料流、即時報表和 API 請求，以及目前的流量變數資料，則僅有附帶補充資料 ID 的點擊會延遲。
* 若是目前轉換量度的資料、已完成的資料及資料摘要，則所有點擊均會額外延遲 5 至 7 分鐘。

請注意，延遲增加會在您實作Identity service後開始，即使您尚未完全實作此整合亦然。
