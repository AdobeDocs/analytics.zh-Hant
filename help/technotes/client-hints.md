---
title: 客戶端提示
description: 了解客戶端提示如何逐漸取代用戶代理作為設備資訊的源。
source-git-commit: cd8370f6c19e79e1a8a506e772db390708e96a44
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---


# 客戶端提示概述和常見問題集

客戶端提示是有關用戶設備的單個資訊。 由Chromium瀏覽器提供，例如Google Chrome和Microsoft Edge。 對於這些瀏覽器，客戶端提示將逐漸取代用戶代理作為設備資訊的源。 Adobe Analytics會更新其裝置查閱程式，以便除了使用者代理程式外，還使用用戶端提示來判斷裝置資訊。

Google將User-Agent客戶端提示分為兩類：低熵和高熵提示。

* 低熵提示對設備有更通用的資訊。 這些提示由Chromium瀏覽器自動提供。

* 高熵提示有更詳細的資訊。 這些提示僅可通過請求獲得。 AppMeasurement和Web SDK都可設定為要求高熵提示。 依預設，兩個程式庫都會執行 **not** 請求高熵提示。

>[!NOTE]
>
>從2022年10月開始，新版Chromium瀏覽器將開始「凍結」User-Agent字串中表示的作業系統版本。 當使用者升級其裝置時，使用者代理中的作業系統將不會變更。 因此，隨著時間推移，User-Agent中表示的操作版本資訊將變得不那麼準確。 作業系統版本是高熵提示，因此若要在報表中維持作業系統版本的準確性，必須設定您的收集程式庫以收集這些高熵提示。 隨著時間的推移，用戶代理的其他設備資訊將被凍結，需要客戶端提示來保持設備報告的準確性。

## 常見問答

+++**我可以在何處了解有關客戶端提示的更多資訊？**

此 [Google部落格貼文](https://web.dev/user-agent-client-hints/) 是很好的參考和起點。

+++

+++**如何啟用客戶端提示的集合？**

低熵提示由瀏覽器自動提供並包含在Adobe導出設備和瀏覽器資訊的過程中。 較新版本的AppMeasurement(從2.23.0開始)和Web SDK(從2.12.0開始)可設定來收集高熵提示。 對於這兩個程式庫，高熵提示的集合為 **預設為停用**.

+++

+++**如何捕捉高熵提示？**

高熵提示可透過Web SDK和AppMeasurement程式庫的個別標籤擴充功能來設定，或直接透過collectHighEntropyUserAgentHints標幟來設定。

+++

+++**我可以選擇收集的高熵提示嗎？**

現在不行。 您可以選擇收集所有高熵提示或無。

+++

+++**Analytics中的裝置報表是否會有任何變更？**

可用於報告的裝置欄位不會變更。 為這些欄位捕獲的資料可能會根據欄位以及配置客戶端提示收集的方式而改變。

+++

+++**哪些Analytics報表欄位衍生自使用者代理？**

* [瀏覽器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [瀏覽器類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [作業系統 ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [作業系統類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [行動裝置與行動裝置類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [資料摘要](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=zh-Hant)

+++

+++**哪些Analytics報表欄位是從儲存在高熵提示中的值衍生而來？**

自2022年9月起，Google發佈的「凍結」User-Agent提示時間表指示作業系統版本將自2022年10月起停止更新。 當使用者升級其作業系統時，使用者代理程式中的作業系統版本將不會更新。 若沒有高熵值提示，Analytics「作業系統」維度中包含的作業系統版本的準確度將逐漸降低。

請參閱 [Google發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) 查看凍結用戶代理的其他部分的時間。

+++

+++**Adobe如何使用客戶端提示來獲取設備資訊？**

Adobe使用第三方Device Atlas,Device Atlas將同時使用客戶端提示和User-Agent來獲取設備資訊。

+++

+++**哪些瀏覽器受客戶端提示影響？**

用戶端提示僅適用於Chromium瀏覽器，例如Google Chrome和Microsoft Edge。 來自其他瀏覽器或行動應用程式的資料沒有變更。

+++

+++**透過Adobe來源連接器傳送至AEP和CJA的資料中是否會提供用戶端提示？**

我們計畫在2023年上半年通過Adobe源連接器將客戶端提示納入資料中。

+++

+++**XDM中如何呈現用戶端提示？**

請參閱 [綱要檔案](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) 在Adobe Experience Platform。

+++

+++**各種提示欄位是什麼？ 哪些會影響裝置報告？**

下表介紹了自2022年9月起的客戶端提示。

| 提示 | 說明 | 高或低熵 | 範例 |
| --- | --- | --- | --- | 
| Sec-CH-UA | 瀏覽器和重要版本 | 低 | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | 行動裝置（true或false） | 低 | TRUE |
| Sec-CH-UA-Platform | 作業系統/平台 | 低 | &quot;Android&quot; |
| Sec-CH-UA-Arch | 網站架構 | 高 | &quot;arm&quot; |
| Sec-CH-UA-Bitness | 架構位元 | 高 | &quot;64&quot; |
| Sec-CH-UA-Full-Version | 瀏覽器的完整版本 | 高 | 「84.0.4143.2」 |
| Sec-CH-UA-Full-Version-List | 品牌清單及其版本 | 高 | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | 裝置型號 | 高 | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | 作業系統/平台版本 | 高 | &quot;10&quot; |

+++



+++**使用者代理程式的哪些部分會「凍結」，以及何時？**

請參閱 [Google發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). 這可能會有所變更。

+++
