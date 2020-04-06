---
description: 如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。
title: 管理區段
topic: Report builder
uuid: 4e4edc39-ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理區段

如何在 Report Builder 中新增、編輯、套用及篩選 Adobe Analytics 區段。

報告建立工具在「請求精靈」的步驟1中提供區段面板，可讓您建立和管理區段。

![](assets/seg_dialog.png)

## 新增或編輯區段 {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE] 若要新增或編輯區段，Report Builder 區段介面會在 Microsoft Internet Explorer 視窗中啟動 Analytics 區段產生器。您的報告建立工具作業將保持作用中。 此作業不支援Internet Explorer以外的瀏覽器。

1. In the segment panel of Step 1 of the Request Wizard, click **[!UICONTROL Add]**.
1. Internet Explorer視窗隨即啟動，開啟Analytics區段產生器介面。 如需如何建立區段的詳細資訊，請參 [閱https://marketing.adobe.com/resources/help/en_US/analytics/segment/](https://marketing.adobe.com/resources/help/zh_TW/analytics/segment/)。
1. 定義並儲存區段後，請返回「請求精靈」。
1. 按一下「重新整理」圖示以重新整理區段清單。

>[!IMPORTANT]
>
>本清單是快取清單，除非您重新整理，否則新建立的區段不會顯示出來。

## 建立內文中區段 {#section_6DD2C663B2854469AA1075438F907678}

您可以將要轉換成區段的報表維度合併為特定組合。您可以從報告建立工具介面建立這些區段。 例如，從「頁面」請求輸出中選取幾個頁面，並根據這些值建立區段。

1. 選取您要轉換成區段的報表輸出項目。
1. Right-click to select **[!UICONTROL Create In-Context Segment in]** and specify the right container (Hits Container, Visits Container, Visitor Container).

   ![](assets/seg_in_context.png)

   如需容器的詳細資訊，請參閱區 [段指南](https://marketing.adobe.com/resources/help/zh_TW/analytics/segment/)。

1. 區段產生器UI現在將會在Internet Explorer中啟動。 區段產生器UI將會以您指定的容器和篩選器初始化。
1. 在區段中新增名稱和說明後，請加以儲存。
1. 返回報告建立工具，然後按一下「重新整理」圖示以重新整理區段清單。
1. 您現在已準備好套用此區段。

## 搜尋並套用區段 {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

任何在「報表與分析」、「Ad Hoc Analysis」、Report Builder 或「Data Warehouse」中建立的區段，都會出現在此區段清單中。若要重新整理清單，請按一下「重新整理」圖示 (![](assets/refresh_icon.png)。

您可以套用一或多個區段至任何指定的請求。 這包括循序區段。

1. Go to the **[!UICONTROL Segment]** drop-down list and click the small down arrow in the **[!UICONTROL Choose Segment]** box to display all the segments.

   ![](assets/seg_list.png)

1. 勾選您要套用的區段。

>[!NOTE] 無論您是否擔任管理員，都只能在 Report Builder 中查看您擁有的區段以及與您共用的區段(在「行銷 Reports &amp; Analytics」使用者介面中，管理員可查看組織中的所有區段)。

## 篩選區段 {#section_376E986D3E684999A7CDB08E53854159}

若要&#x200B;**篩選**&#x200B;區段，請按一下「篩選」圖示：![](assets/segment_filter.png)

可用的篩選條件包括：

| 篩選器名稱 | 說明 |
|---|---|
| 標記 | 可讓您篩選具有特定標籤的區段。 請注意，「標籤」篩選器使用AND運算子。 如果您勾選兩個標籤，右窗格會顯示已使用兩個標籤標籤的 **區段** 。 |
| 擁有者 | 可讓您依擁有者篩選區段。 請注意，「擁有者」篩選器使用OR運算子。 如果您勾選兩個擁有者，右窗格會顯示其中一個擁有者所擁有 **的區** 段。 |
| 其他篩選器>僅報 *表套裝名稱* | 如果您在 [!DNL marketing reports & analytics] 的「區段產生器」中套用&#x200B;*「僅限報表套裝名稱」*&#x200B;篩選條件，接著在 [!DNL report builder] 中顯示「進階篩選」，則進階篩選只會顯示所選報表套裝的區段。 |
| 其他篩選器 > 我的 | 顯示您擁有的所有區段。 |
| 其他篩選器 > 與我共用 | 顯示其他人與您共用的所有區段。 |
| 其他篩選器>我的最愛 | 顯示您標示為「我的最愛」的所有區段。 |
| 其他篩選器>已核准 | 顯示所有正式核准的區段。 |

## 新增區段控制項至活頁簿 {#section_E3E5149A8464441FA5445A98DBD520AC}

新增區段控制項可讓您在活頁簿內切換區段，而無需前往「請求精靈」。

1. 按一下區段下拉式清單旁的「控制項」圖示 (![](assets/control_icon.png))。

   ![](assets/seg_control.png)

1. 勾選您要顯示在區段控制項中的所有區段，或勾選 **[!UICONTROL Select All]**。
1. 請注意此選項 **[!UICONTROL Automatically refresh linked requests upon item selection]**。

   * 如果勾選，則會重新整理使用此控制項的所有請求。
   * 如果未勾選，則會更新相關的請求參數，但不會重新整理請求。

1. 指定區段控制項的左上方儲存格位置。
1. 按一 **[!UICONTROL OK]** 下，區段控制項就會出現在指定的位置。

   ![](assets/seg_control2.png)

## 重新整理區段清單 {#section_22E4A86789444B4A998532396B476EFB}

每次新增區段或編輯現有區段時，請務必按一下「重新整理」圖示 (![](assets/refresh_icon.png)，以重新整理區段的快取清單。

## 管理各請求中的區段 {#section_C3D63FCBE1A94369A319243313B03C93}

在5.4版之前，Report Builder可讓使用者在多個請求上變更區段。 不過，此程式會一律取代現有區段。 想要在每個請求中新增一個區段的使用者無法這麼做，因為新增區段會移除已指派給每個請求的先前區段集。

Report Builder 5.4 可讓您在多個目標請求當中新增、移除、取代以及取代所有區段：

1. 在活頁簿中選取多個請求。
1. 按一下右鍵並選擇 **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**。

   ![](assets/edit_by_segment.png)

1. 在「編輯群組」對話方塊中，選取四個選項其中一個：

   | 選項 | 說明 |
   |---|---|
   | 新增區段 | 可讓您選擇一或多個區段以新增至目前區段的清單。 |
   | 取代區段 | 可讓您選擇要以一或多個區段取代的區段。 |
   | 將所有區段取代為 | 可讓您選擇一或多個區段，以取代目前的區段。 |
   | 移除區段 | 可讓您從請求中移除區段。 |

