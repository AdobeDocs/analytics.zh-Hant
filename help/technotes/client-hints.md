---
title: 用戶端提示
description: 進一步了解 客戶端提示如何逐漸取代用戶代理作為設備資訊的源。
source-git-commit: f2f1e64a62796b58c24e6ff652db93b21f750669
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 52%

---


# 用戶端提示總覽和常見問題

用戶端提示指有關使用者裝置的個別資訊。上述提示會透過 Google Chrome 和 Microsoft Edge 之類的 Chromium 瀏覽器提供。對於這些瀏覽器，客戶端提示將逐漸取代用戶代理作為設備資訊的源。 Adobe Analytics會更新其裝置查閱程式，以便除了使用者代理程式外，還使用用戶端提示來判斷裝置資訊。

Google將User-Agent客戶端提示分為兩類：低熵和高熵提示。

* **低熵提示** 包含更多有關設備的一般資訊。 這些提示會由 Chromium 瀏覽器自動供應。

* **高熵** 提示包含更詳細的資訊。 這些提示則只能透過請求取得。AppMeasurement和Web SDK [可設定](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) 請求高熵提示。 依預設，兩種資料庫都&#x200B;**不會**&#x200B;請求高平均資訊量提示。

>[!NOTE]
>
>從2022年10月開始，新版Chromium瀏覽器將開始「凍結」User-Agent字串中表示的作業系統版本。 當使用者升級其裝置時，使用者代理中的作業系統將不會變更。 因此，隨著時間推移，User-Agent中表示的操作版本資訊將變得不那麼準確。 作業系統版本是一種高平均資訊量提示，因此為了在您的報告中維持作業系統版本的準確性，有必要設定您的收藏集資料庫來收集這些高平均資訊量提示。隨著時間的推移，用戶代理的其他設備資訊將被凍結，需要客戶端提示來保持設備報告的準確性。

## 常見問題集

+++**我可以在何處進一步瞭解用戶端提示？**

這篇 [Google 部落格文章](https://web.dev/user-agent-client-hints/)是很好的參考資料和起點。

+++

+++**我如何才能啟用用戶端提示的收藏集？**

低熵提示由瀏覽器自動提供並包含在Adobe導出設備和瀏覽器資訊的過程中。 較新版本的AppMeasurement(從2.23.0開始)和Web SDK(從2.12.0開始)可設定來收集高熵提示。 對於這兩個資料庫，高平均資訊量提示的收藏集會&#x200B;**預設為停用**。

+++

+++**我如何才能擷取高平均資訊量提示？**

可設定高平均資訊量提示 透過其個別的「標籤」擴充功能或直接搭配collectHighEntropyUserAgentHints標幟，使用Web SDK和AppMeasurement程式庫。

+++

+++**我可以選擇收集哪些高平均資訊量提示嗎？**

目前不可以。您可以選擇收集所有的高平均資訊量提示或不收集。

+++

+++**Analytics 中的裝置報告是否會有任何變更？**

可供報告的裝置欄位將不會變更。為這些欄位捕獲的資料可能會根據欄位以及配置客戶端提示收集的方式而改變。

+++

+++**哪些Analytics報表欄位衍生自使用者代理？**

* [瀏覽器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=zh-Hant)
* [瀏覽器類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=zh-Hant)
* [作業系統](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=zh-Hant)
* [作業系統類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=zh-Hant)
* [行動裝置與行動裝置類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=zh-Hant)
* [資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)

+++

+++**哪些 Analytics 報表欄位衍生自儲存在高平均資訊量提示中的值？**

自2022年9月起，Google發佈的「凍結」User-Agent提示時間表指示作業系統版本將自2022年10月起停止更新。 當使用者升級其作業系統時，使用者代理程式中的作業系統版本將不會更新。 若沒有高熵值提示，Analytics「作業系統」維度中包含的作業系統版本的準確度將逐漸降低。

請參閱 [Google發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) 查看凍結用戶代理的其他部分的時間。

+++

+++**Adobe 將如何使用用戶端提示來導出裝置資訊？**

Adobe使用第三方Device Atlas,Device Atlas將同時使用客戶端提示和User-Agent來獲取設備資訊。

+++

+++**哪些瀏覽器會受用戶端提示的影響？**

用戶端提示僅適用於 Google Chrome 和 Microsoft Edge 之類的 Chromium 瀏覽器。對於來自其他瀏覽器或行動應用程式的資料不會產生任何變更。

+++

+++**是否通過不安全的連接支援客戶端提示？

不行。只能通過安全的HTTP連接（如HTTPS）收集客戶端提示。

+++

+++**透過 Adob&#x200B;&#x200B;e Source Connector 傳送到 AEP 和 CJA 的資料中是否會提供用戶端提示？**

Adobe計畫在2023年上半年通過Adobe源連接器將客戶端提示納入資料中。

+++

+++**在 XDM 中會如何表示用戶端提示？**

請參閱 Adobe Experience Platform 中的[結構描述文件](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121)。

+++

+++**不同的提示欄位代表什麼？哪些會影響裝置報告？**

下表會說明截至 2022 年 9 月的用戶端提示。

| 提示 | 說明 | 高或低平圴資訊量 | 範例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 瀏覽器和重要版本 | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | 行動裝置 (true 或 false) | 低 | TRUE |
| Sec-CH-UA-Platform | 作業系統/平台 | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | 網站架構  | 高 | 「arm」 |
| Sec-CH-UA-Bitness | 架構位元 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | 瀏覽器的完整版本 | 高 | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | 品牌清單及其版本 | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | 裝置型號 | 高 | 「Pixel 3」 |
| Sec-CH-UA-Platform-Version | 作業系統/平台版本 | 高 | 「10」 |

+++



+++**使用者代理程式的哪些部分會「凍結」，以及何時？**

請參閱 [Google 發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html)。 這可能會隨時變更。

+++
