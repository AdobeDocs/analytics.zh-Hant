---
title: 用戶端提示
description: 進一步了解用戶端提示將逐漸取代使用者代理程式成為裝置資訊的來源。
source-git-commit: 9dfeb0f5cc3bb488fa28fb0d21c6969dfdfc9ef6
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 100%

---


# 用戶端提示總覽和常見問題

用戶端提示指有關使用者裝置的個別資訊。上述提示會透過 Google Chrome 和 Microsoft Edge 之類的 Chromium 瀏覽器提供。對於這些瀏覽器，用戶端提示將逐漸取代使用者代理程式成為裝置資訊的來源。Adobe Analytics 將更新其裝置查找流程，以便使用除使用者代理程式以外的用戶端提示來確定裝置資訊。

Google 將使用者代理程式用戶端提示分為兩種類別：低平均資訊量和高平均資訊量提示。

* **低平均資訊量**&#x200B;提示包含較多關於裝置的一般資訊。這些提示會由 Chromium 瀏覽器自動供應。

* **高平均資訊量**&#x200B;提示包含較多詳細資訊。這些提示則只能透過請求取得。AppMeasurement 和 Web SDK 都可設定為請求高平均資訊量提示。依預設，兩種資料庫都&#x200B;**不會**&#x200B;請求高平均資訊量提示。

>[!NOTE]
>
>從 2023 年 1 月中旬開始，客戶提示將被納入 Analytics 裝置查詢流程。AppMeasurement 和 Web SDK 目前都支援收集提示資料，但在 1 月中旬之前不會用於裝置查詢。這是為了避免在關鍵的年終期間對報告的潛在干擾。如下所述，作業系統版本將從 10 月開始凍結，但由於是逐步推出和大多數使用者代理將凍結到正確的作業系統版本，我們估計這將影響不到 3% 的 Chrome 訪客。

>[!NOTE]
>
>從 2022 年 10 月開始，新版本的 Chromium 瀏覽器將開始「凍結」使用者代理字串中表示的作業系統版本。作業系統版本是一種高平均資訊量提示，因此為了在您的報告中維持作業系統版本的準確性，有必要設定您的收藏集資料庫來收集這些高平均資訊量提示。一段時間後，使用者代理程式的裝置資訊將被凍結，需要用戶端提示來維持裝置報告的準確性。

>[!NOTE]
>
>AAM 需要收集高平均資訊量提示以保留完整功能。如果您使用的是 [伺服器端轉送至 AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=zh-Hant)，那麼您可能想要啟用高平均資訊量提示收集功能。

## 常見問題集

+++**我可以在何處進一步瞭解用戶端提示？**

這篇 [Google 部落格文章](https://web.dev/user-agent-client-hints/)是很好的參考資料和起點。

+++

+++**我如何才能啟用用戶端提示的收藏集？**

低平均資訊量提示會由瀏覽器自動提供，並擷取衍生裝置和瀏覽器資訊。較新版本的 Web SDK (從 2.12.0 開始) 和 AppMeasurement (從 2.23.0 開始) 可以設定為透過各自標籤擴充或直接透過設定選項收集高平均資訊量提示。請參閱 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=zh-Hant#enabling-high-entropy-client-hints) 和 [AppMeaurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=zh-Hant) 的說明。

對於這兩個資料庫，高平均資訊量提示的收藏集會&#x200B;**預設為停用**。

+++

+++**我可以選擇收集哪些高平均資訊量提示嗎？**

目前不可以。您可以選擇收集所有的高平均資訊量提示或不收集。

+++

+++**什麼是各種用戶端提示值？**

下表會說明截至 2022 年 10 月的用戶端提示。

| 提示 | 說明 | 高或低平圴資訊量 | 範例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 瀏覽器和重要版本 | 低 | 「Google Chrome 84」 |
| Sec-CH-UA-Mobile | 行動裝置 (true 或 false) | 低 | TRUE |
| Sec-CH-UA-Platform | 作業系統/平台 | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | 網站架構  | 高 | 「arm」 |
| Sec-CH-UA-Bitness | 架構位元 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | 瀏覽器的完整版本 | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | 品牌及其版本的清單 | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | 裝置型號 | 高 | 「Pixel 3」 |
| Sec-CH-UA-Platform-Version | 作業系統/平台版本 | 高 | 「10」 |

+++

+++**Analytics 中的裝置報告是否會有任何變更？**

可供報告的裝置欄位將不會變更。為這些欄位擷取的資料可能會因不同欄位以及您為用戶端提示設定收藏集的方式而發生變更。

+++

+++**哪些 Analytics 報表欄位衍生自使用者代理程式？**

這些欄位直接衍生自使用者代理程式，但使用者代理程式可用於協助推導出其他裝置相關欄位的值 (視裝置詳細資料而定)。

* [瀏覽器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=zh-Hant)
* [瀏覽器類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=zh-Hant)
* [作業系統](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=zh-Hant)
* [作業系統類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=zh-Hant)
* [行動裝置和行動裝置類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=zh-Hant)

+++

+++**從使用者代理程式中會移除哪些部分以及何時移除？**

請參閱 [Google 發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。這可能會隨時變更。

+++

+++**哪些 Analytics 報表欄位衍生自儲存在高平均資訊量提示中的值？**

這將隨著時間的推移而改變，因為 Google 會「凍結」使用者代理程式的更多部分。第一個直接受影響的欄位是「作業系統」，其中包括作業系統版本。根據 Google 發布的「凍結」使用者代理程式提示的時間表，從 2022 年 10 月下旬開始凍結作業系統版本 Chromium 版本 107。在那時，使用者代理程式中的作業系統版本在某些情況下會不準確。

若要了解使用者代理程式其他部分的凍結時間，請參閱 [Google 發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。

+++

+++**Adobe 將如何使用用戶端提示來導出裝置資訊？**

Adobe 會使用協力廠商 Device Atlas，該協力廠商將使用用戶端提示和使用者代理程式來導出裝置資訊。

+++

+++**哪些瀏覽器會受用戶端提示的影響？**

用戶端提示僅適用於 Google Chrome 和 Microsoft Edge 之類的 Chromium 瀏覽器。對於來自其他瀏覽器或行動應用程式的資料不會產生任何變更。

+++

+++**用戶端提示在不安全連線時是否受到支援？**

否。用戶端提示只能透過安全的 HTTP 連線 (例如 HTTPS) 收集。

+++

+++**使用 API 提交時如何包含用戶端提示資料？**

請參閱文件以透過[大量資料插入 API](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/) 包含這些內容。

+++

+++**透過 Adobe Source Connector 傳送到 AEP 和 CJA 的資料中是否提供用戶端提示？**

Adobe 計劃在 2023 年上半年透過 Adobe Source Connector 在資料中包含用戶端提示。

+++

+++**在 XDM 中會如何表示用戶端提示？**

請參閱 Adobe Experience Platform 中的[結構描述文件](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)。

+++

+++**AAM 伺服器端轉送是否支援用戶端提示？**

是。客戶端提示將包含在轉送至 AAM 的資料中。請注意 AAM 需要收集高平均資訊量提示以保留完整功能。如果您使用的是 [伺服器端轉送至 AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html)，那麼您可能想要啟用高平均資訊量提示收集功能。

+++

