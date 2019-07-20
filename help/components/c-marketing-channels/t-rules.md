---
description: 建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。
seo-description: 建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。
seo-title: 建立行銷管道處理規則
solution: Analytics
subtopic: 行銷渠道
title: 建立行銷管道處理規則
topic: Reports & Analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 建立行銷管道處理規則

建立行銷管道處理規則，以判定訪客點按是否符合指派給管道的標準。

此程序使用電子郵件規則做為範例。此範例假設您已新增電子郵件渠道至「行銷渠道管理員」頁面上的渠道清單中。

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. 選擇一個報表套裝。

   如果報表套裝尚未定義渠道，則會顯示[!UICONTROL 「自動設定」頁面]。

   請參閱 [執行自動設定](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Processing Rules]**.

   ![步驟結果](assets/marketing_channel_rules.png)

1. From the **[!UICONTROL Add New Rule Set]** menu, select **[!UICONTROL Email]**.

   您在此處並非選擇渠道，而是選擇範本並以數個必要參數填入規則。

   ![步驟結果](assets/example_email.png)

   使用布林邏輯 (if/then 陳述式) 來設定規則。例如，在電子郵件渠道規則中，您提供下列規則陳述式中強調的設定或資訊: 

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In this example, *`<value>`* is the query string parameter that you use for your email campaign, such as *`eml`*.
1. To continue creating rules, click **[!UICONTROL Add Rule]**.
1. 若要排列規則優先順序，請將它們拖放至適當位置。
1. Click **[!UICONTROL Save.]**

>[!MORE_LIKE_THIS]
>
>* [常問問題和範例](/help/components/c-marketing-channels/c-faq.md)

