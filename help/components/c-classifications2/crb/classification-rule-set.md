---
description: 規則集是一組特定變數的分類規則。您可以套用變數至規則集。 如果您想要為一個變數建立多個規則集，您必須將每個規則集套用至多個報表套裝。
subtopic: Classifications
title: 分類規則集
topic: Admin tools
uuid: c4d7b77c-fa98-44be-955f-9aee7f73480b
translation-type: tm+mt
source-git-commit: 0e97e28ffb2bf94acfb382c3f97ff30b31321467

---


# 分類規則集

規則集是一組特定變數的分類規則。您可以套用變數至規則集。 如果您想要為一個變數建立多個規則集，您必須將每個規則集套用至多個報表套裝。

## 分類規則集

規則集是一組特定變數的分類規則。您可以套用變數至規則集。 如果您想要為一個變數建立多個規則集，您必須將每個規則集套用至多個報表套裝。

## Classification Rule Builder Page {#section_C60B0888C76D49C596EF19F11808B718}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

下列欄位和選項可在中取用 [!UICONTROL Classifications Rule Builder]。

<table id="table_A5D92409969747E39E041216A5AA32CD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><a href="/help/components/c-classifications2/crb/classification-rule-set.md"  > 新增規則集</a> </p> </td> 
   <td colname="col2"> <p>建立規則集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>規則 </p> </td> 
   <td colname="col2"> 顯示規則集中包含的規則數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>狀態 </p> </td> 
   <td colname="col2"> 顯示規則集的活動狀態，例如「草稿」或「作用中」。 作用中規則會每日處理，通常會追溯一個月的分類資料。 規則會自動檢查新值並上傳分類。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>上次變更時間 </p> </td> 
   <td colname="col2"> 指出規則集的編輯時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>複製 </p> </td> 
   <td colname="col2"> 複製 (拷貝) 規則集，以便將規則集套用到其他變數，或套用到不同報表套裝裡的同一個變數。 </td> 
  </tr> 
 </tbody> 
</table>

## 建立分類規則集 {#create-classification-rule-set}

命名分類規則集、套用變數及指定覆寫設定。

1. （先決條件）在 **[!UICONTROL Admin]** >中定義分類結 **[!UICONTROL Report Suites]**&#x200B;構。

   (請參閱「 [管理工具](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) 」說明中的「分類」，瞭解如何新增分類。)

   Variables will display in the [!UICONTROL New Rule Set] panel only after they have at least one classification defined for that variable.

   您可以在> > > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** (或 **[!UICONTROL Traffic]** > **[!UICONTROL Traffic Classifications]****[!UICONTROL Conversion]****[!UICONTROL Conversion Classifications]**)中建立變數的分類。 Then select the variable, then click **[!UICONTROL Add Classification]**.

1. 若要建立規則集，請按一下 **[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]** > **[!UICONTROL Add Rule Set]**。

   ![](assets/new_rule_set.png)

1. 為規則集命名，然後按一下 **[!UICONTROL Create Rule Set]**。
1. 選取要編輯的規則集。

   ![](assets/classification_rules_page.png)

1. 按一下 **[!UICONTROL Select Report Suites and Variables]**.

   報表套裝和變數清單會填入您登入公司中所有報表套裝中可用的所有分類變數。 報表套裝中的單一變數只能屬於一個規則集。

   請參閱&#x200B;*`Variable`*&#x200B;分類規則產生器[頁面所列定義中的](/help/components/c-classifications2/crb/classification-rule-definitions.md)以取得詳細資訊。
1. Specify the report suites and variables to use, then click **[!UICONTROL Save]**.
1. [將分類規則新增](/help/components/c-classifications2/crb/classification-rule-set.md)到規則集以繼續執行。
