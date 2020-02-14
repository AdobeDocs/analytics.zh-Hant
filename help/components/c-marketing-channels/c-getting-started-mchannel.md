---
title: 開始使用行銷渠道
description: 瞭解行銷渠道工作流程、自動設定，以及如何將範本報表套裝設定套用至多個報表套裝。
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# 開始使用行銷渠道

「行銷渠道」常用來提供訪客如何進入您的網站的相關資訊。您可以根據所要追蹤的渠道以及追蹤方式，建立及自訂行銷渠道處理規則。

行銷渠道的中心為「首次和上次接觸」量度，這是標準轉換量度的元件。

## 行銷管道工作流程

![](assets/step1_icon.png) 根據您的業務需求定義每個渠道.

定義您使用的渠道是行銷渠道最重要的組成部分之一。定義渠道需要組織中的多人合作。以下是您需要考慮的幾個問題: 

* 您使用付費搜尋嗎?
* 您使用電子郵件促銷活動嗎? 您使用多個電子郵件促銷活動，而且想分別追蹤嗎?
* 您有附屬機構且其流量會導向至您的網站嗎? 您有想要分別追蹤的附屬機構嗎?
* 是否有有利於分別追蹤的外部促銷活動?
* 您要彙總所有社交網站，還是要分別追蹤?
* 還有其他會影響轉換而且您想追蹤的渠道嗎?

建議的渠道清單位於[常問問題和範例](/help/components/c-marketing-channels/c-faq.md)。先建立您要使用的渠道清單，當您建立渠道時，進行啟用和定義就會比較輕鬆。

![](assets/step2_icon.png) 在頁面上新增行銷 [!UICONTROL Marketing Channel Manager] 渠道。

After defining what channels to track, you enable them in **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.

請參閱[管道和規則](/help/components/c-marketing-channels/c-channels.md)，瞭解重要的必要條件和概念資訊。

請參閱[新增行銷管道](/help/components/c-marketing-channels/c-channels.md)以瞭解程序。

>[!NOTE]
>
>如果先前未設定行銷管道，則會顯示[自動設定](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。此設定提供數個預先設定好的行銷渠道，供您進行自訂。Adobe 建議您使用這些規則作為範本。不過，如果您已有確定的渠道定義，則可跳過自動設定。

![](assets/step3_icon.png) 設定或調整頁面上每個渠道的 [!UICONTROL Marketing Channel Processing Rules] 規則。

After you create channels on the [!UICONTROL Marketing Channel Manager] page, you configure the rules so that channels can retrieve and report data.

See [Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md).

如果渠道是以自動設定建立的，則這些渠道的規則已經定義好。您可修改規則以便符合您的需求。

## 行銷渠道的自動設定 {#run-auto-setup}

行銷管道報表隨附一次性設定頁面，可協助您開始使用。其中提供數個行銷渠道，您可用來追蹤。如果熟悉如何建立渠道和規則，則可跳過該設定。不過，Adobe 仍建議讓精靈替您建立渠道。自動設定可讓您觀看規則的建立方式，您也可自行編輯規則。您可隨時停用或刪除預定義渠道。

如何執行行銷管道自動設定。

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在上， [!UICONTROL Report Suite Manager]選取報表套裝。
1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   ![步驟結果](assets/wizard.png)

   >[!NOTE]
   >
   >The [!UICONTROL Marketing Channels: Auto Setup] page displays automatically when you access channel configuration applications in Admin Tools. (請參閱[行銷管道管理員](/help/components/c-marketing-channels/c-channels.md))。如果報表套裝中包含一個或多個行銷渠道，該頁面不顯示。除非選擇其他不包含行銷渠道的報表，否則無法再存取該頁面。

1. 確保選定想要建立的渠道。

   選取、 **[!UICONTROL Email]**、 **[!UICONTROL Display]**&#x200B;和 **[!UICONTROL Affiliate]** 為必填欄位。

1. 按一下 **[!UICONTROL Save]**.

## 套用範本報表套裝設定至多個報表套裝

如何將主報表套裝作為範本，以測試行銷管道設定。為節省時間，您可在大量更新中，將該範本套用至一個或多個生產報表套裝。您需為渠道和規則集分別執行該任務。

> [!NOTE] 套用規則集之前，必須先從範本套用管道。執行該程序時，所有報表套裝中的渠道必須相同。

1. 確保選定的報表套裝有啟用行銷渠道報表。此步驟由您的帳戶管理員執行。
1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. On the **[!UICONTROL Report Suite Manager]** page, select the template report suite, as well as one or more target report suites.
1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.
1. 在頁面上 **[!UICONTROL Select Master Report Suites]** ，選取範本報表套裝。
1. 按一下 **[!UICONTROL Save All]**.
1. 從範本套用規則至多個報表套裝:
   1. 返回頁 [!UICONTROL Report Suite Manager] 面。
   1. 選取範本報表套裝，以及一個或多個目標報表套裝。
   1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.
   1. 按一下 **[!UICONTROL Save]**. 如果「儲存」按鈕在此步驟中是停用的，請展開一個規則以便啟用它。

