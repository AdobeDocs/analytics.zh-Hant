---
description: 在 Analysis Workspace 和「區段產生器」中可供使用。
seo-description: 在 Analysis Workspace 和「區段產生器」中可供使用。
seo-title: 具有 Experience Cloud ID 的訪客
title: 具有 Experience Cloud ID 的訪客
uuid: 47edbd3d6-a92-1e51-ac7 a-b8 d5 fb9565 e0
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 具有 Experience Cloud ID 的訪客

在 Analysis Workspace 和「區段產生器」中可供使用。

顯示具有 Experience Cloud ID 的訪客數目。您可以瞭解哪些頁面已部署了Identity Service，您可以瞭解可與其他Experience Cloud解決方案共用多少訪客。您也可以在與 Experience Cloud 共用的區段中使用此量度。

>[!IMPORTANT]
>
>For this metric to appear, you have to have the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) running for the report suite.

## Experience Cloud ID 設定除錯 {#section_679E62142A3E46548FF8FBDA46568005}

The [!UICONTROL Visitors with Experience Cloud ID] metric is a useful metric in Adobe Analytics intended to help you find and debug your [!UICONTROL Identity Service]setup. 度量是報表套裝中已指派Experience Cloud ID來自Identity Service的訪客數目計數。此量度在進行下列作業時非常有用: 診斷某些 Experience Cloud 整合可能無法與如預期數量訪客共用的原因，或找出網站可能尚未部署 MCID 的區域。

若要使用「具有 Experience Cloud ID 的訪客」量度，只需將其拖曳至任何報表內作為量度即可，例如此[!UICONTROL 「頁面」]報表:

![](assets/metric-mcvid1.png)

在此範例中，請注意每頁的「獨特訪客」數量都與「具有 Experience Cloud ID 的訪客」數量相同。但是，「獨特訪客」的總數卻大於「具有 Experience Cloud ID 的訪客」總數。若要找出沒有為所有訪客設定 MCID 的頁面，請使用此定義[建立計算量度](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html):

![](assets/metric-mcvid2.png)

將計算量度加入報表後，您便可為「頁面」報表排序，進而顯示沒有 MCID 的訪客最多頁面:

![](assets/metric-mcvid3.png)

您現在可以快速看出「產品快速檢視」頁面未適當地與身分服務建置，且應盡快更新。您可以任何類型的維度構建類似的報表，例如瀏覽器類型、網站區域或內容類型。

當您識別出訪客沒有 MCID 的頁面，就可以回報給實施團隊，請他們修正這些頁面。

在某些情況下，即使 MCID 服務已在頁面實施，您仍可能會發現少量 MCID 並未設定供部分訪客使用。這類情況很可能是由於在提供報表套裝之前，呼叫了 AppMeasurement 函數的 Analytics JavaScript 或 DTM 設定的常見錯誤設定。若要避免此情況，請務必正確[插入核心 AppMeasurement 代碼](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html)。

請注意，您與 Experience Cloud 共用之「產品快速檢視」頁面 (如上所示) 的任何區段，與其他 Experience Cloud 解決方案的符合率很可能會非常低。若要查看任意區段的 MCID 涵蓋率，您可以建構如下的報表:

![](assets/metric-mcvid4.png)

在這個表格中 (比較「獨特訪客」數量與「具有 Experience Cloud ID 的訪客」數量)，很容易看出「區段 1」的 MCID 覆蓋率未達 100％，而「區段 2」則有。這代表如果我要與 Experience Cloud 共用「區段 1」，則在總計 3,859 名訪客中只有 2,186 名有資格共用。
