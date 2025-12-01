---
title: 建立和編輯分類合併
description: 說明如何建立、驗證、執行、核准和取消分類合併。
exl-id: f36bcbcb-0ed0-44a7-a6a9-b28fd244fb27
feature: Classifications
source-git-commit: f34072ec42d62cef0a3e1fd4d63f6f39693cf0fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---

# 建立和編輯分類合併

分類集合併可讓您從多個分類集取得分類，並將它們合併成一個。 使用此介面可建立從開始到結束的分類集合併。 此介面對於從舊式分類移至分類集的組織而言最有價值。 使用分類集的組織已經不需要使用此合併工作流程。

## 建立合併 {#create-a-consolidation}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidation_setpriority"
>title="「分類設定」優先順序"
>abstract="![索引鍵](/help/assets/icons/Key.svg) *分類設定*&#x200B;是基礎分類設定，定義整體結構描述，並在任何合併衝突中優先處理。 其他分類設定則依從上到下的順序套用。"


若要建立分類合併，請在Adobe Analytics主介面中：

1. 從&#x200B;**[!UICONTROL 元件]**&#x200B;功能表選取&#x200B;**[!UICONTROL 分類集]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;管理員中，選取&#x200B;**[!UICONTROL 合併]**&#x200B;索引標籤。
1. 在&#x200B;**[!UICONTROL 分類設定 — 合併]**&#x200B;管理員中，選取![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 新]**。
1. 在&#x200B;**[!UICONTROL 新合併]**&#x200B;對話方塊中，

   ![分類設定 — 新合併](assets/classifications-sets-consolidations-new.png)
   1. 輸入&#x200B;**[!UICONTROL 名稱]**。 例如：`Consolidation Example`。
   1. 輸入&#x200B;**[!UICONTROL 描述（選擇性）]**。 例如，`Example classification set`。
   1. 在&#x200B;**[!UICONTROL 通知問題]**&#x200B;中輸入一或多個電子郵件地址（以逗號分隔）。 系統會向這些使用者傳送有關問題的電子郵件通知。
   1. 從&#x200B;**[!UICONTROL 要比對的「分類設定」]**&#x200B;下拉式功能表中選取分類設定。

      **[!UICONTROL Source分類設定]**&#x200B;左側清單已填入與所選分類清單類似且可合併的分類設定。 右側清單會自動填入選取的![索引鍵](/help/assets/icons/Key.svg)分類設定。 該基底集定義了整體結構描述，並在任何合併衝突中一律優先。

   1. 從左側清單中選取您要合併的分類集，並將選取的分類集拖曳至右側清單，使其位於選取的![索引鍵](/help/assets/icons/Key.svg)基底&#x200B;**[!UICONTROL _分類集_]**&#x200B;之下。

      當您執行合併時，其他分類集會以遞增順序合併。 如果一個索引鍵存在於多個其他集中，則會採用來自排名最前分類集的索引鍵值。 如果![Key](/help/assets/icons/Key.svg)基底集和任何其他集合中都存在索引鍵，則會使用基底集中的值。

      若要管理要使用哪些鍵值，請透過拖放來移動清單中的個別和選取的分類設定。 您也可以透過拖放將![索引鍵](/help/assets/icons/Key.svg) **[!UICONTROL _分類設定_]**&#x200B;取代為選取的分類設定。

   1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存分類合併。 選取「**[!UICONTROL 取消]**」即可取消。

儲存後，系統會自動驗證分類合併以進行合併。 此驗證可確保每個個別分類集對此合併有效。 一旦成功，分類合併清單中的專案就會顯示狀態&#x200B;**[!UICONTROL 已驗證]**。

建立合併後，接下來的步驟為：

* [重新驗證](#re-validate)當您變更初始組態時，重新驗證分類合併。
* [執行](#run)分類合併。
* [核准](#approve)分類合併。



<!--
         
  

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Consolidations]** > **[!UICONTROL Add]**

The following fields are available when creating a consolidation:

* **[!UICONTROL Name]**: The name of the consolidation.
* **[!UICONTROL Notify of issues]**: A comma-delimited list of email addresses that are notified of issues with this consolidation.
* **[!UICONTROL Dataset to match]**: A drop-down list of all classification sets.

Once you select a classification set, a table with two columns appears:

* The right column contains all classification sets that you want to consolidate. It starts with the classification set selected using the above drop-down list.
* The left column contains all classification sets eligible to be merged with the originally selected dataset. **Schemas must exactly match to be eligible for consolidation**. If schemas do not match the selected classification set, they do not appear in this left column.

Drag the desired classification sets from the available column on the left to the consolidation column on the right. Once the consolidation is given a name and two or more classification sets are in the right column, click **[!UICONTROL Save & Continue]**.

-->

## 編輯合併

若要編輯分類合併，請在Adobe Analytics主介面中：

1. 從&#x200B;**[!UICONTROL 元件]**&#x200B;功能表選取&#x200B;**[!UICONTROL 分類集]**。
1. 在&#x200B;**[!UICONTROL 分類設定]**&#x200B;管理員中，選取&#x200B;**[!UICONTROL 合併]**&#x200B;索引標籤。
1. 在&#x200B;**[!UICONTROL 分類集合併]**&#x200B;管理員中：
   1. 選取分類合併的名稱。 **[!UICONTROL 合併： _分類合併名稱_]**對話方塊就會顯示。 外觀和可用動作取決於合併的目前狀態，以及您是否仍然可以選擇修改分類合併。

      | 可用動作 | 說明 |
      |---|---|
      | ![取消](/help/assets/icons/Cancel.svg) **[!UICONTROL 取消]** | [取消合併](#cancel)。 |
      | ![核取記號](/help/assets/icons/Checkmark.svg) **[!UICONTROL 重新驗證]** | [重新驗證合併](#re-validate)。 |
      | ![播放](/help/assets/icons/Play.svg) **[!UICONTROL 執行]** | [執行合併](#run)。 |
      | ![ThumbUp](/help/assets/icons/ThumbUp.svg) **[!UICONTROL 核准]** | [核准合併](#approve)。 |



### 重新驗證

您可以在「合併：分類合併」對話方塊中，重新驗證分類合併。 ![警示](/help/assets/icons/Alert.svg)可能會針對需要重新設定合併的合併問題，提供其他資訊。

![分類設定 — 合併重新驗證](assets/classifications-sets-consolidations-validated.png)

若要重新驗證分類合併：

1. 使用您用來建立合併的相同拖放介面，重新設定合併。
1. 選取![核取記號](/help/assets/icons/Checkmark.svg) **[!UICONTROL 重新驗證]**。 驗證可確保每個個別的分類集對此合併有效。 成功時，會顯示快顯通知訊息： ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 已成功提交合併以進行驗證！]**
1. 選取![CrossSize400](/help/assets/icons/CrossSize400.svg)以關閉對話方塊。 或選取![播放](/help/assets/icons/Play.svg) **[!UICONTROL 執行]**&#x200B;以執行合併，或選取![取消](/help/assets/icons/Cancel.svg) **[!UICONTROL 取消]**&#x200B;取消分類。



<!--
Once you have created a consolidation, a list of source datasets appears on the right. The **[!UICONTROL Validate]** button makes sure that each individual classification set is valid for this consolidation. You can reorder the classification steps here to determine priority in cases of mismatched classification values. **The highest classification set in the list overwrites any mismatched values in other classification sets.**

-->

### 執行

一旦成功驗證分類合併，您就可以執行合併。

若要執行分類合併，請執行下列動作：

1. 選取![播放](/help/assets/icons/Play.svg) **[!UICONTROL 執行]**。 快顯通知訊息顯示![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 已成功提交合併以進行處理！]**
1. 選取![CrossSize400](/help/assets/icons/CrossSize400.svg)以關閉對話方塊。


### 核准 {#approve}


>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_mismatch"
>title="不相符"
>abstract="當整合分類集中的值與來源分類集不符時，鍵值不相符百分比。"

>[!CONTEXTUALHELP]
>id="classificationsets_consolidations_absent"
>title="不存在"
>abstract="已整合分類集中，但來源分類集中沒有索引鍵的百分比。"

分類合併成功執行後，合併狀態為![StatusOrange](/help/assets/icons/StatusOrange.svg) **[!UICONTROL 正在等待核准]**。 核准分類合併會以合併的分類設定取代個別分類設定，且會移除個別分類設定。

![分類集 — 合併等待核准](assets/classifications-sets-consolidations-waitingforapproval.png)

若要核准分類集合併，請執行下列步驟：

1. 使用&#x200B;**[!UICONTROL 相似度報表]**&#x200B;來檢閱合併。 此報告顯示含有下列資料欄的表格：

   * **[!UICONTROL 分類設定名稱]**：分類設定的名稱。
   * **[!UICONTROL 不相符]**：索引鍵值不符合來源分類集的資料列百分比。 如果不相符百分比很高，不相符可能表示分類資料太不同。 檢查並確保選取的分類設定有類似的分類資料。
   * **[!UICONTROL 不存在]**：索引鍵值在![索引鍵](/help/assets/icons/Key.svg)分類設定中，但不在來源分類設定中的資料列百分比。 所有缺失的列都會新增至整合的分類集。

1. 如果分類合併已準備好進行核准，請選取![核取記號](/help/assets/icons/Checkmark.svg) **[!UICONTROL 核准]**。 **[!UICONTROL 核准合併？]**&#x200B;對話方塊提示確認。 選取&#x200B;**[!UICONTROL 核准]**&#x200B;以核准合併。 選取「**[!UICONTROL 取消]**」即可取消。

核准後，就會建立合併的分類集。 狀態已設定為&#x200B;**[!UICONTROL 完成]**。


### 取消

您可以在核准前取消分類合併。

若要取消分類合併，請執行下列步驟：

1. 選取&#x200B;**[!UICONTROL 取消]**。

   合併取消後，您無法繼續合併。
1. 選取&#x200B;**[!UICONTROL 取消合併]**&#x200B;以取消合併。 選取&#x200B;**[!UICONTROL 返回]**&#x200B;以恢復取消。
