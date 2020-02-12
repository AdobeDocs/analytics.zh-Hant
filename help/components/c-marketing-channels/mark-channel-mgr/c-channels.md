---
description: 在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷渠道的報表套裝，自動設定可為您建立多個渠道及其規則。您可視需要編輯預定義渠道或建立自己的渠道 (最多總共 25 個)。
subtopic: Marketing channels
title: 管理行銷渠道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dd58453a0459bc200a00badf34d06c259ce9fb59

---


# 管理行銷渠道

在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷渠道的報表套裝，自動設定可為您建立多個渠道及其規則。您可視需要編輯預定義渠道或建立自己的渠道 (最多總共 25 個)。

以下是建立渠道的指引:

* 透過設立所有渠道的清單來提前計劃，以便將所有訪客點按歸入正確的渠道類別。
* 一律包括[內部](/help/components/c-marketing-channels/mc-faq/c-faq.md)點按和[直接](/help/components/c-marketing-channels/mc-faq/c-faq.md)點按類別的渠道。

Adding channels to the [!UICONTROL Marketing Channels] page is done independently of creating rules on the [Marketing Channel Processing Rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) page. 建立規則時，您會將規則與渠道相關聯。

## 新增行銷渠道 {#add-mktg-channels}

在行銷管道管理員中新增行銷管道。

> [!NOTE] 管道無法刪除。如果不想使用渠道，則可停用或重新命名它，並保留以備將來之用。

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. 在頁面 [!UICONTROL Report Suite Manager] 上，選取報表套裝。

   如果選擇多個報表套裝，請選擇一個範本，將範本設定複製到所選的報表套裝。

   請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/getting-started/t-template.md)。

1. 按一下 **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   如果報表套裝尚未定義管道，則會顯示[自動設定](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)頁面。

1. 在頁面上 [!UICONTROL Marketing Channel Manager] ，按一下 **[!UICONTROL Add Channel]**。

   已定義 25 個渠道時，此選項不可用。

1. 按一下 **[!UICONTROL Save.]**
1. 若要設定渠道規則，請按一下 **[!UICONTROL Marketing Channel Processing Rules]**。

   請參閱[建立行銷管道處理規則](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md)。

## 行銷管道管理員 - 介面定義 {#mktg-channel-mgr}

頁面的欄位 [!UICONTROL Marketing Channel Manager] 定義。

| 欄位 | 定義 |
|--- |--- |
| 已啟用 | 啟用或停用該行銷渠道。 |
| 渠道名稱 | 行銷渠道的友好名稱。 |
| 覆蓋上次接觸渠道 | 可讓您選擇是否使用選取的渠道覆蓋現有的永久性上次接觸渠道。如果勾選此核取方塊，任何渠道 (包括直接和內部) 都會覆蓋現有的上次接觸渠道。產生的結果會將轉換歸屬於可能不值得該評價的渠道。例如，若之前已透過免費搜尋渠道獲得使用者，則此選項可確保直接渠道不會接收用於轉換的評價。 |
| 渠道劃分 | 允許您依該值劃分渠道。You can add possible channel breakdowns (subchannels) when creating [marketing channel classifications](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md). |
| 類型 | 指定使用者前往您網站的方式。您可選擇「線上」或「離線」。對於透過搜尋引擎或電子郵件促銷活動到來的訪客，您可使用「線上」渠道。「離線」渠道適用於透過報章廣告或雜誌廣告找到您網站的訪客。離線渠道通常包括從報告資料來源匯入的資料。請參閱 [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html)。請參閱[新增離線資料](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md)。 |
| 色彩 | 與該行銷渠道相關的色彩。該色彩代表行銷渠道報表中的渠道。 |