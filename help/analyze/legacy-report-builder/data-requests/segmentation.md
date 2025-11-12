---
description: 如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。
title: 管理區段(Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 25%

---

# 管理區段

{{legacy-arb}}

如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。

Report Builder提供「請求精靈」步驟1的區段面板，可讓您建立和管理區段。

![熒幕擷圖顯示[新增]、[編輯]或[清除]區段的[區段]選項，並反白顯示[控制]、[篩選]和[重新整理]圖示。](assets/seg_dialog.png)

## 新增或編輯區段 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>若要新增或編輯區段，Report Builder 區段介面會在 Microsoft Internet Explorer 視窗中啟動 Analytics 區段產生器。您的Report Builder工作階段將保持作用中。 此作業不支援Internet Explorer以外的瀏覽器。

1. 在「請求精靈」步驟 1 的區段面板中，按一下&#x200B;**[!UICONTROL 「新增」]**。
1. Internet Explorer視窗會啟動，開啟Analytics區段產生器介面。 如需關於如何建立區段的資訊，請參閱 [Analytics 區段](/help/components/segmentation/seg-home.md)。
1. 定義並儲存區段後，請返回「請求精靈」。
1. 按一下「重新整理」圖示以重新整理區段清單。

>[!IMPORTANT]
>
>本清單是快取清單，除非您重新整理，否則新建立的區段不會顯示出來。

## 建立內文中區段 {#section_6DD2C663B2854469AA1075438F907678}

您可以將要轉換成區段的報表維度合併為特定組合。您可以從Report Builder介面建立這些區段。 例如，從頁面請求輸出中選取一些頁面，並根據這些值建立區段。

1. 選取您要轉換成區段的報表輸出專案。
1. 按一下滑鼠右鍵選取「**[!UICONTROL 建立內文中區段於]**」，並指定正確的容器 (點擊數容器、瀏覽次數容器、訪客容器)。

   ![熒幕擷圖顯示所選和可用容器選項中的「建立內文中區段」。](assets/seg_in_context.png)

   如需容器的詳細資訊，請參閱[分段指南](/help/components/segmentation/seg-home.md)。

1. Internet Explorer現在會啟動區段產生器UI。 區段產生器UI將會以您指定的容器和篩選進行初始化。
1. 新增名稱和說明至區段後，請儲存。
1. 返回Report Builder並按一下「重新整理」圖示，重新整理區段清單。
1. 您現在已準備好套用此區段。

## 搜尋並套用區段

在Reports &amp; Analytics （現已終止服務）、Report Builder或Data Warehouse中建立的任何區段，都會出現在此區段清單中。 若要重新整理清單，請按一下[重新整理]圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)。

您可以將一或多個區段套用至任何特定請求。 這包括循序區段。

1. 前往&#x200B;**[!UICONTROL 「區段」]**&#x200B;下拉式清單，按一下&#x200B;**[!UICONTROL 「選擇區段」]**&#x200B;方塊中的小型向下箭頭，以顯示所有區段。

1. 勾選您要套用的區段。

   ![熒幕擷圖顯示選取的區段。](assets/seg_list.png)

>[!NOTE]
>
>無論您是否擔任管理員，都只能在Report Builder中檢視您擁有的區段以及與您共用的區段

## 篩選區段 {#filter}

按一下「篩選」圖示： **篩選圖示**，即可篩選![區段](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)

可用的篩選條件包括：

| 篩選器名稱 | 說明 |
|---|---|
| 標記 | 可讓您篩選具有特定標籤的區段。 請注意，標籤篩選器會使用AND運運算元。 如果您核取兩個標籤，右窗格會顯示已使用&#x200B;**both**&#x200B;標籤標籤的區段。 |
| 所有者 | 可讓您依擁有者篩選區段。 請注意，擁有者篩選器會使用OR運運算元。 如果檢查兩個擁有者，右窗格會顯示&#x200B;**任一**&#x200B;擁有者擁有的區段。 |
| 其他篩選器>僅&#x200B;*報表套裝名稱* | 如果您在Adobe Analytics的「區段產生器」中套用「僅&#x200B;*報表套裝名稱*」篩選條件，然後在[!DNL Report Builder]中顯示「進階篩選」，則進階篩選只會顯示所選報表套裝的區段。 |
| 其他篩選器 > 我的 | 顯示您擁有的所有區段。 |
| 其他篩選器 > 與我共用 | 顯示其他人與您共用的所有區段。 |
| 其他篩選器>我的最愛 | 顯示所有標示為我的最愛區段。 |
| 其他篩選器>已核准 | 顯示所有正式核准的區段。 |

## 將區段控制項新增至活頁簿 {#segment-control}

新增區段控制項可讓您在活頁簿內切換區段，而無需前往「請求精靈」。

1. 按一下區段下拉式清單旁的控制項圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)。

1. 勾選您要出現在區段控制項中的所有區段，或勾選&#x200B;**[!UICONTROL 全選]**。

   ![選取所有區段的[控制項設定]對話方塊熒幕擷圖。](assets/seg_control.png)

1. 注意選項&#x200B;**[!UICONTROL 在選取專案時自動重新整理連結的請求]**。

   * 如果勾選，所有使用此控制項的請求都會重新整理。
   * 若未勾選，則會更新關聯的請求引數，但不會重新整理請求。

1. 指定區段控制項的左上角儲存格位置。

1. 按一下&#x200B;**[!UICONTROL 確定]**，區段控制項就會顯示在指定的位置。

   ![熒幕擷圖顯示[選擇區段]欄位下拉式欄位。](assets/seg_control2.png)

## 重新整理區段清單 {#refresh}

每次新增區段或編輯現有區段時，請務必按一下「重新整理」圖示![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg)，以重新整理區段的快取清單。

## 管理各請求中的區段 {#manage}

v5.4之前，Report Builder可讓使用者變更多個請求上的區段。 不過，此程式一律會取代現有區段。 想要為每個請求新增一個區段的使用者無法這麼做，因為新增區段會移除已指派給每個請求的先前區段集。

Report Builder 5.4 可讓您在多個目標請求當中新增、移除、取代以及取代所有區段：

1. 在活頁簿中選取多個請求。
1. 按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL 「編輯請求]** > **[!UICONTROL 依區段」]**。

   ![熒幕擷圖顯示編輯要求及選取的區段。](assets/edit_by_segment.png)

1. 在「編輯群組」對話方塊中，選取四個選項其中一個：

   | 選項 | 說明 |
   |---|---|
   | 新增區段 | 可讓您選擇要新增至目前區段清單的一或多個區段。 |
   | 取代區段 | 可讓您選擇要以一或多個區段取代的區段。 |
   | 取代所有區段，方法為 | 可讓您選擇一或多個區段，以取代目前的區段。 |
   | 移除區段 | 可讓您從請求中移除區段。 |
