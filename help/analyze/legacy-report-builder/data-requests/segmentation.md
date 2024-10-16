---
description: 如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。
title: 管理區段(Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 74%

---

# 管理區段

如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。

Report Builder提供「請求精靈」步驟1的區段面板，可讓您建立和管理區段。

![熒幕擷圖顯示[新增]、[編輯]或[清除]區段的[區段]選項，並反白顯示[控制]、[篩選]和[重新整理]圖示。](assets/seg_dialog.png)

## 新增或編輯區段 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>若要新增或編輯區段，Report Builder 區段介面會在 Microsoft Internet Explorer 視窗中啟動 Analytics 區段產生器。您的Report Builder工作階段將保持作用中。 此作業不支援 Internet Explorer 以外的瀏覽器。

1. 在「請求精靈」步驟 1 的區段面板中，按一下&#x200B;**[!UICONTROL 「新增」]**。
1. Internet Explorer 視窗隨即啟動，並開啟 Analytics 區段產生器介面。如需關於如何建立區段的資訊，請參閱 [Analytics 區段](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)。
1. 在定義及儲存區段之後，返回「請求精靈」。
1. 按一下「重新整理」圖示以重新整理區段清單。

>[!IMPORTANT]
>
>本清單是快取清單，除非您重新整理，否則新建立的區段不會顯示出來。

## 建立內文中區段 {#section_6DD2C663B2854469AA1075438F907678}

您可以將要轉換成區段的報表維度合併為特定組合。您可以從 Report Builder 介面建立這些區段。例如，從「頁面」請求輸出選取一些頁面，並根據這些值建立區段。

1. 選取您要轉換成區段的報表輸出項目。
1. 按一下滑鼠右鍵選取「**[!UICONTROL 建立內文中區段於]**」，並指定正確的容器 (點擊數容器、瀏覽次數容器、訪客容器)。

   ![熒幕擷圖顯示所選和可用容器選項中的「建立內文中區段」。](assets/seg_in_context.png)

   如需容器的詳細資訊，請參閱[劃分指南](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html)。

1. 區段產生器使用者介面將立即在 Internet Explorer 中啟動。區段產生器使用者介面將會依您指定的容器與篩選條件進行起始化。
1. 將名稱與說明新增至區段後，請儲存。
1. 返回Report Builder並按一下重新整理圖示，以重新整理區段清單。
1. 現在，您已可套用此區段。

## 搜尋及套用區段 {#search}

在Reports &amp; Analytics （現已終止服務）、Report Builder或Data Warehouse中建立的任何區段，都會出現在此區段清單中。 若要重新整理清單，請按一下[重新整理]圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)。

您可以套用一或多個區段至任何指定的請求。這包含依序排列的區段。

1. 前往&#x200B;**[!UICONTROL 「區段」]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL 「選擇區段」]**&#x200B;方塊中的小型向下箭頭，以顯示所有區段。

1. 勾選您要套用的區段。

   ![熒幕擷圖顯示選取的區段。](assets/seg_list.png)

>[!NOTE]
>
>無論您是否擔任管理員，都只能在Report Builder中檢視您擁有的區段以及與您共用的區段。

## 篩選區段 {#filter}

按一下「篩選」圖示： ![篩選圖示](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)，即可篩選&#x200B;**區段**

可用的篩選條件包括：

| 篩選名稱 | 說明 |
|---|---|
| 標記 | 可讓您利用特定標記篩選區段。請注意，「標記」篩選條件使用 AND 運算子。如果您勾選兩個標記，右側窗格會顯示同時擁有&#x200B;**兩個**&#x200B;標記的區段。 |
| 擁有者 | 可讓您依擁有者篩選區段。請注意，「擁有者」篩選條件使用 OR 運算子。如果您勾選兩個擁有者，右側窗格會顯示&#x200B;**其中一位**&#x200B;擁有者擁有的區段。 |
| 其他篩選條件 > 僅&#x200B;*報表套裝名稱* | 如果您在Adobe Analytics的「區段產生器」中套用「僅&#x200B;*報表套裝名稱*」篩選條件，然後在[!DNL Report Builder]中顯示「進階篩選」，則進階篩選只會顯示所選報表套裝的區段。 |
| 其他篩選器 > 我的 | 顯示您擁有的所有區段。 |
| 其他篩選器 > 與我共用 | 顯示所有其他人與您共用的區段。 |
| 其他篩選條件 > 我的最愛 | 顯示所有標記為「我的最愛」的區段。 |
| 其他篩選條件 > 批准 | 顯示所有已正式批准的區段。 |

## 將區段控制項新增至活頁簿 {#segment-control}

新增區段控制項可讓您在活頁簿內切換區段，而無需前往「請求精靈」。

1. 按一下區段下拉式清單旁的控制項圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)。

1. 勾選所有您希望在區段控制項中出現的區段，或勾選「**[!UICONTROL 選取全部]**」。

   ![選取所有區段的[控制項設定]對話方塊熒幕擷圖。](assets/seg_control.png)

1. 請注意「**[!UICONTROL 項目選取時自動重新整理連結的請求]**」選項。

   * 如果勾選此選項，所有使用該控制項的請求都會重新整理。
   * 如果未勾選此選項，則會更新相關的請求參數，但不會重新整理請求。

1. 指定區段控制項的左上方儲存格位置。

1. 按一下「**[!UICONTROL 確定]**」，區段控制項便會出現在指定的位置。

   ![熒幕擷圖顯示[選擇區段]欄位下拉式欄位。](assets/seg_control2.png)

## 重新整理區段清單 {#refresh}

每次新增區段或編輯現有區段時，請務必按一下「重新整理」圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)，以重新整理區段的快取清單。

## 管理各請求中的區段 {#manage}

5.4 版之前，Report Builder 可讓使用者變更多個請求上的區段。然而，該過程一律會取代現有區段。使用者無法將新區段新增至每個請求，由於新增區段將移除先前指派給每個請求的區段集。

Report Builder 5.4 可讓您在多個目標請求當中新增、移除、取代以及取代所有區段：

1. 選取活頁簿中的多個請求。
1. 按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 「編輯請求]** > **[!UICONTROL 依區段」]**。

   ![熒幕擷圖顯示編輯要求及選取的區段。](assets/edit_by_segment.png)

1. 在「編輯群組」對話方塊中，選取四個選項其中一個：

   | 選項 | 說明 |
   |---|---|
   | 「新增區段」 | 可讓您選擇一個或多個區段，以便新增至現有的區段清單。 |
   | 「取代區段」 | 可讓您選擇要以一個或多個區段來取代的區段。 |
   | 「取代所有區段依據」 | 可讓您選擇要以一個或多個區段來取代的一個或多個區段。 |
   | 「移除區段」 | 可讓您從請求中移除區段。 |
