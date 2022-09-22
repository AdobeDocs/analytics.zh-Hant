---
title: 客戶端提示
description: 了解
source-git-commit: b99852f4b8e0a3034ea8965e5646b1ab2f1a8c4c
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# 客戶端提示概述和常見問題集

客戶端提示是有關用戶設備的單個資訊。 由Chromium瀏覽器提供，例如Google Chrome和Microsoft Edge。 對於這些瀏覽器，客戶端提示將逐漸取代用戶代理作為設備資訊的源。 Adobe Analytics會更新其裝置查閱程式，以便除使用者代理外，還使用用戶端提示來判斷裝置資訊。

Google將使用者代理用戶端提示分為兩類：低熵和高熵提示。

* 低熵提示對設備有更通用的資訊。 這些提示由Chromium瀏覽器自動提供。

* 高熵提示有更詳細的資訊。 這些提示僅可通過請求獲得。 AppMeasurement和Web SDK都可設定為要求高熵提示。 依預設，兩個程式庫都會執行 **not** 請求高熵提示。

>[!NOTE]
>
>從2022年10月開始，新版Chromium瀏覽器將開始「凍結」使用者代理字串中代表的作業系統版本。 這表示隨著時間推移，使用者代理中所呈現的作業版本資訊將變得不那麼精確。 作業系統版本是高熵提示，因此若要在報表中維持作業系統版本的準確性，必須設定您的收集程式庫以收集這些高熵提示。 隨著時間的推移，用戶代理的其他設備資訊將被凍結，需要客戶端提示來保持設備報告的準確性。

## 常見問答

+++**如何啟用客戶端提示的集合？**

瀏覽器會自動提供低熵提示，並包含在Adobe的裝置資訊處理程式中。 較新版本的AppMeasurement（起始TBD）和Web SDK（起始TBD）可設定來收集高熵提示。 對於這兩個程式庫，高熵提示的集合為 **預設為停用**. 如需實作此項目的詳細資訊，請參閱這裡。

+++**我可以選擇收集的高熵提示嗎？**

現在不行。 您可以選擇收集所有高熵提示或無。

+++**Analytics中的裝置報表是否會有任何變更？**

可用於報告的裝置欄位不會變更。 為這些欄位捕獲的資料可能會根據欄位以及配置客戶端提示收集的方式而改變。

+++**哪些Analytics報表欄位衍生自使用者代理？**

* [瀏覽器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [瀏覽器類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [作業系統 ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [作業系統類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [行動裝置與行動裝置類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* 資料摘要(請注意，使用者必須更新才能擷取這些欄位。 此外，還有相依性，無法公開行動ID與裝置資訊。)
* Analytics來源連接器（未就緒）

+++**哪些Analytics報表欄位是從儲存在高熵提示中的值衍生而來？**

自2022年9月起，Google發佈的凍結User-Agent提示時間表表示作業系統版本將自2022年10月起停止更新。 若沒有高熵值提示作業系統版本的準確度，Analytics的「作業系統」維度也會逐漸降低。

請參閱 [Google發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) 查看凍結用戶代理的時間。

+++**哪些瀏覽器受客戶端提示影響？**

用戶端提示僅適用於Chromium瀏覽器，例如Google Chrome和Microsoft Edge。 來自其他瀏覽器或行動應用程式的資料沒有變更。

+++**Adobe如何使用客戶端提示來獲取設備資訊？**

Adobe使用第三方Device Atlas,Device Atlas將同時使用客戶端提示和用戶代理來獲取設備資訊。

+++**資料摘要中是否提供用戶端提示？**

是。 請參閱檔案（待審）。

+++**透過Adobe來源連接器傳送至AEP和CJA的資料中是否會提供用戶端提示？**

我們計畫在2023年上半年通過Adobe源連接器將客戶端提示納入資料中。

+++**XDM中如何呈現用戶端提示？**

請參閱 [綱要檔案](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) 在Adobe Experience Platform。

+++**我可以在何處了解有關客戶端提示的更多資訊？**

此 [Google部落格貼文](https://web.dev/user-agent-client-hints/) 是很好的參考和起點。

+++**各種提示欄位是什麼？ 哪些會影響裝置報告？**

下表介紹了自2022年9月起的客戶端提示。

| 提示（標題） | 提示 | 高或低熵 | 範例 | Analytics報表欄位 |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | 瀏覽器和重要版本 | 低 | Google Chrome 84 | [瀏覽器](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) 和 [瀏覽器類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | 行動裝置（true或false） | 低 | TRUE | [行動裝置與行動裝置類型](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform | 作業系統/平台 | 低 | Android | [作業系統 ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | 網站架構 | 高 | &quot;arm&quot; | 無? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | 高 |  | 無? |
| Sec-CH-UA-Full-Version | 瀏覽器的完整版本 | 高 | 「84.0.4143.2」 | 無? |
| Sec-CH-UA-Full-Version-List | ??? | 高 | ??? | 無? |
| Sec-CH-UA-Model | 裝置型號 | 高 | &quot;Pixel 3&quot; | 無? |
| Sec-CH-UA-Platform-Version | 作業系統/平台版本 | 高 | &quot;10&quot; | [作業系統 ](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**如何捕捉高熵提示？**

可以配置高熵提示

* 直接使用AppMeasurement [連結至實作指南中的標幟項目]
* 在「標籤分析」擴充功能中
* 在Web SDK中。

+++**正在從用戶代理中刪除哪些資料？**

請參閱 [Google發佈的時間表](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). 這可能會有所變更。

+++