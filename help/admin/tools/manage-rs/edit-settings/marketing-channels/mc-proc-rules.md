---
title: 行銷管道的處理規則
description: 使用規則來判斷點選所屬的行銷管道。
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# 行銷管道處理規則

_此頁面參考將行銷管道指派給點選的處理規則。 請參閱[處理規則](../general/processing-rules/pr-overview.md)，瞭解可讓您調整資料收集方式的功能。_

行銷管道處理規則可讓您建立邏輯，以決定[行銷管道](/help/components/dimensions/marketing-channel.md)和[行銷管道詳細資料](/help/components/dimensions/marketing-detail.md)維度的值。 使用[行銷管道管理員](c-channels.md)來決定您使用的行銷管道，然後使用處理規則來決定每個管道的設定方式。

![行銷管道貯體](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 行銷管道]** > **[!UICONTROL 行銷管道處理規則]**

[自動設定](/help/components/c-marketing-channels/c-getting-started-mchannel.md)執行後，會針對設定期間產生的每個管道建立規則。

![預設規則](assets/marketing_channel_rules.png)

您可以使用多個規則來定義單一行銷管道。 如果您想要根據規則條件以不同方式設定管道詳細資訊，對單一管道使用多個規則可能會有幫助。 您也可以使用多個條件來定義單一規則。

## 規則定義

每個規則都包含條件和指派：

* **[!UICONTROL 如果下列任一/所有為true]**：如果您將多個條件新增至單一規則，您可以判斷是否必須符合所有條件或符合任一條件，才能設定管道和相關值。
* **規則條件**：指定一或多個必須符合的規則條件。 通常，您會指定點選必須符合哪個維度，才能符合行銷管道的資格。
* **[!UICONTROL 然後執行下列動作]**：當規則條件符合時，設定[行銷管道](/help/components/dimensions/marketing-channel.md) （[!UICONTROL 識別管道為]）和[行銷管道詳細資料](/help/components/dimensions/marketing-detail.md) （[!UICONTROL 設定管道的值]）。

## 規則條件

設定規則條件時，可使用下列選項。

>[!NOTE]
>
>所有文字欄位均評估為&#x200B;**不區分大小寫**。 例如，如果您使用查詢字串引數`cmp`等於`abc123`的規則條件，則查詢字串引數和值都可以使用任何大寫和小寫組合。

**Adobe偵測到的條件**&#x200B;不包含任何輸入文字的選項或欄位。

| Adobe偵測到的狀況 | 說明 |
|---|---|
| **[!UICONTROL 符合付費搜尋偵測規則]** | 點選來自可識別的搜尋引擎，並符合[付費搜尋偵測規則](../general/paid-search-detection/paid-search-detection.md)。 |
| **[!UICONTROL 符合免費搜尋偵測規則]** | 點選來自於可識別的搜尋引擎，且不符合付費搜尋偵測規則。 |
| **[!UICONTROL 反向連結符合內部URL篩選器]** | 點選包含符合[內部URL篩選器](/help/components/dimensions/referrer.md)的[反向連結](../general/internal-url-filter-admin.md)。 |
| **[!UICONTROL 反向連結不符合內部URL篩選器]** | 點選包含不符合內部URL篩選器的反向連結。 |
| **[!UICONTROL 是造訪的第一次點選]** | 這是造訪中的首次點選。 |
| **[!UICONTROL 反向連結為社交網路]** | [反向連結型別](/help/components/dimensions/referrer-type.md)為「社交網路」。 |
| **[!UICONTROL 反向連結不是社交網路]** | 反向連結型別不是「社交網路」。 |
| **[!UICONTROL 反向連結為對話式AI]** | 反向連結型別為「Conversational AI」。 |
| **[!UICONTROL 反向連結不是對話式AI]** | 反向連結型別不是「Conversational AI」。 |

**點選屬性**&#x200B;可讓您指定要尋找的維度、相符運運算元和值。

| 點選屬性條件 | 說明 |
|---|---|
| **[!UICONTROL 頁面]** | [頁面](/help/components/dimensions/page.md)維度。 |
| **[!UICONTROL 頁面網域]** | url的網域。 例如，`products.example.com`。 |
| **[!UICONTROL 頁面網域和路徑]** | url的網域和路徑。 例如，`products.example.com/mens/pants/overview.html`。 |
| **[!UICONTROL 頁面根網域]** | URL的根網域。 例如，`example.co.uk`。 |
| **[!UICONTROL 頁面 URL]** | 完整頁面URL。 |
| **[!UICONTROL 查詢字串引數]** | 頁面URL中的個別查詢字串引數。 針對每個規則條件使用一個查詢字串引數。 如果您想要在規則中包含多個查詢字串引數，請使用多個規則條件。 |
| **[!UICONTROL 反向連結]** | [反向連結](/help/components/dimensions/referrer.md)維度。 |
| **[!UICONTROL 反向連結網域]** | [反向連結網域](/help/components/dimensions/referring-domain.md)維度。 |
| **[!UICONTROL 反向連結網域和路徑]** | 反向連結網域和反向連結URL路徑。 例如，`www.example.com/products/id/12345`或`ad.example.com/foo`。 |
| **[!UICONTROL 反向連結引數]** | 反向連結中的查詢字串引數。 |
| **[!UICONTROL 反向連結根網域]** | 反向連結根網域。 |
| **[!UICONTROL 搜尋引擎]** | [搜尋引擎](/help/components/dimensions/search-engine.md)維度。 |
| **[!UICONTROL 搜尋關鍵字]** | [搜尋關鍵字](/help/components/dimensions/search-keyword.md)維度。 |
| **[!UICONTROL 搜尋引擎+搜尋關鍵字]** | 搜尋引擎和搜尋關鍵字的串連。 |
| **[!UICONTROL AMO ID]** | Adobe Advertising與Advertising Analytics整合所使用的主要追蹤程式碼。 當其中一項整合啟用時，追蹤程式碼首碼可用來識別Advertising專用的管道。 以「AL」開頭的值適用於「搜尋」和「社交」。 以「AC」開頭的值用於顯示。 行銷管道中使用AMO ID時，點選/成本/曝光量度可歸因到正確的管道。 |
| **[!UICONTROL AMO EF ID]** | Adobe Advertising使用的次要追蹤程式碼。 作為將資料傳回Advertising的金鑰。 它可用來識別顯示點進次數，並將檢視點進次數顯示為兩個個別的行銷管道。 若要這麼做，對於顯示點進次數，設定「AMO EF ID」的行銷管道邏輯結尾為`:d`，或者對於顯示檢視點進次數，設定「AMO EF ID」結尾為`:i`。 如果您不想將顯示分割為兩個管道，請改用AMO ID維度。 |

**轉換變數**&#x200B;可讓您指定自訂eVar、比對運運算元以及要尋找的值。

| 轉換變數條件 | 說明 |
|---|---|
| **eVar 1-250** | 關聯的[eVar](/help/components/dimensions/evar.md)維度。 |
