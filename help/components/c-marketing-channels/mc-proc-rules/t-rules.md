---
title: 建立行銷管道處理規則
description: 建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# 建立行銷管道處理規則

建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。

此程序使用電子郵件規則做為範例。此範例假設您已新增電子郵件渠道至「行銷渠道管理員」頁面上的渠道清單中。

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 選取報表套裝。

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md).

1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![步驟結果](assets/marketing_channel_rules.png)

1. 從菜單 **[!UICONTROL Add New Rule Set]** 中，選擇 **[!UICONTROL Email]**。

   您在此處並非選擇渠道，而是選擇範本並以數個必要參數填入規則。

   ![步驟結果](assets/example_email.png)

   使用布林邏輯 (if/then 陳述式) 來設定規則。例如，在電子郵件渠道規則中，您提供下列規則陳述式中強調的設定或資訊: 

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   在此範例中，*`<value>`* 是用於電子郵件促銷活動的查詢字串參數，例如 *`eml`*
1. 若要繼續建立規則，請按一下 **[!UICONTROL Add Rule]**。
1. 若要排列規則優先順序，請將它們拖放至適當位置。
1. 按一下 **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [常問問題和範例](/help/components/c-marketing-channels/mc-faq/c-faq.md)

