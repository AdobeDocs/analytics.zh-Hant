---
description: 閱讀最佳實務和範例，瞭解如何填入各種可為行銷渠道設定的規則。
title: 行銷渠道常見問答集和範例
translation-type: tm+mt
source-git-commit: 8d523d89119fe5e3c1490ecb4efef44f1b99868f

---


# 行銷渠道常見問答集和範例

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## 常見問題集 {#faq}

各行銷渠道規則的實施，因您的追蹤代碼而異。若要設定可提供所需結果的規則，需要一些創新的問題解決方法。

**問題**: 我的追蹤代碼不遵從模式，而我必須為我的「附屬機構」渠道指定上千個模式。

* 使用消除過程。如果「電子郵件」和「附屬機構」渠道使用相同的查詢字串參數，但您只有很少的電子郵件追蹤代碼，則可以在定義電子郵件的規則集中指定電子郵件追蹤代碼。然後使用 *`affiliates.`*
* 在您的電子郵件系統中，新增查詢字串參數至所有著陸頁面 URL，例如 *`&ch=eml`*.建立一個規則集，用於偵測 ch 查詢參數是否等於 *`eml`*。如果不包含 *`eml`*，則為附屬機構。

**問題**: 反向連結網域包含的資料多於我的預期。

* 反向連結網域可能在處理規則清單中排位過高。它應是最後的規則集或之一，因為處理順序至關重要。

**問題**: 我已經建立了符合查詢字串參數的規則，但不管用。

* 請確定已在查詢字串參數欄位中指定參數名稱 (通常是字母數字值)。此外，也請確定有在運算元後面指定參數值，如下列電子郵件規則範例所示。

   ![](assets/example_email.png)

**問題**: 為何我所有的上次接觸流量均歸屬於內部網域? 

* 您擁有符合內部流量的規則。請注意，該等規則會處理訪客在您網站上的每一次點按，而不僅是首次訪問。如果您有類似「*`Page URL exists`*」的規則，而沒有其他標準，則該渠道會符合網站上的每個後續點按，因為頁面 URL 永遠存在。

**問題**: 我如何對報表的「未識別渠道」中顯示流量進行除錯?

* 規則依順序處理。如果不符合特定標準，點按便會屬於下列三個類別之一: 

1. 無反向連結 (直接造訪)。

2. 內部反向連結，位於第一個造訪的頁面上。

3. 頁面上的處理故障。

請確保擁有針對這三種可能性的渠道。例如，建立如下規則︰

1. **[!UICONTROL Referrer]** 和 **[!UICONTROL Does Not Exist]** 和 **[!UICONTROL Is First Page of Visit]**。 (請參閱[直接](/help/components/c-marketing-channels/mc-faq/c-faq.md)。)

2. **[!UICONTROL Referrer Matches Internal URL Filters]** 與 **[!UICONTROL Is First page of Visit]**. (請參閱[內部](/help/components/c-marketing-channels/mc-faq/c-faq.md)。)

3. **[!UICONTROL Referrer]** 和 **[!UICONTROL Exists]** 和 **[!UICONTROL Referrer Does Not Match Internal URL Filters]**。

最後，建立一個擷取剩餘點按的&#x200B;*「其他」*&#x200B;渠道，如[未識別渠道](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)中所述。

## 未識別渠道 {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. 您可建立一個稱作&#x200B;*「其他」*&#x200B;的規則集，例如在處理順序的末尾，這也可識別內部流量，如下所示。

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. 注意不要建立同時識別內部流量的規則。Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

> [!NOTE] 可能還會有其他管道流量分類到「未識別管道」類別中。舉例來說: 一位訪客造訪網站並將網頁加到書籤中，在同一次造訪中會透過書籤返回該頁面。由於這不是該次造訪的第一頁，並沒有反向連結網域，因此不會分類到「直接渠道」或「其他渠道」。

## 付費搜尋 {#paid-search}

付費搜尋是指您為顯示在搜索結果中而需要向搜尋引擎付款的字詞或短語。To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). 目標 URL 符合搜索引擎的現存付費搜尋偵測規則。

For the marketing channel rule, the [!UICONTROL Paid Search] settings are as follows:

![](assets/example_paid_search.png)

如需詳細資訊，請參閱「管理員」中的[「付費搜尋偵測」](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)。

## 免費搜尋 {#natural-search}

訪客經由某個網站搜尋找到您的網站 (您不須支付排名費用，即由該搜尋引擎排名您的網站)，則為「免費」搜尋。您可以控制搜尋引擎用來連結套裝的目的地 URL。此 URL 允許分析識別搜尋是否為免費的。

分析不會偵測免費搜尋。在您設定付費搜尋偵測後，系統會知道如果某個搜尋反向連結不是付費搜尋反向連結，它一定是免費搜尋反向連結。對於免費搜尋，目標 URL 不符合該搜尋引擎的現存付費搜尋偵測規則。

對於行銷渠道規則，免費搜尋設定如下: 

![](assets/example_natural_search.png)

如需詳細資訊，請參閱「管理員」中的[「付費搜尋偵測」](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)。

## 附加產品 {#afilliates}

附屬機構規則可識別源自指定反向連結網域組的訪客。透過該規則，您可列出想要追蹤的附屬機構網域，如下所示:

![](assets/example_affiliates.png)

## 社交網路 {#social-networks}

該規則可識別源自社交網路的訪客，例如 Facebook*。設定值如下: 

![](assets/example_social.png)

## 顯示 {#display}

該規則可識別源自橫幅廣告的訪客。透過目標 URL 中的查詢字串參數來識別，本例中為    *`Ad_01`*.

![](assets/example_display.png)

## 內部 {#internal}

該規則可識別源自符合報表套裝內部 URL 篩選器的反向連結的訪客。

![](assets/example_internal.png)

## 電子郵件 {#email}

若要設定該規則，您可為電子郵件促銷活動提供查詢字串參數。在本例中，參數為    *`eml`*:

![](assets/example_email.png)

如規則包含追蹤代碼，請為每行輸入一個值，如下所示:

![](assets/tracking_code.png)

## 直接 {#direct}

該規則可識別無反向連結網域的訪客。這包括直接來到您網站的訪客，例如來自「我的最愛」連結或透過傳遞其瀏覽器中的連結。

![](assets/example_direct.png)

