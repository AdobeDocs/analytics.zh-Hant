---
description: 您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。
solution: Analytics
subtopic: Classifications
title: 分類規則產生器工作流程
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 分類規則產生器工作流程

您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。

## 重要注意事項，再開始使用

開始使用分類規則前，請記住以下事項：

* 我們目前的分類系統一次只能匯出多達1000萬列。
* 當分類規則產生器(CRB)要求匯出時，會同時提取分類的AND未分類值，未分類的值會在匯出結束時傳遞。 這意味著，隨著時間的推移，你可以填寫1000萬個分類值，而不必去找未分類的值。
* 由於架構的設定方式可讓CRB從「n」個伺服器中提取，因此可能會導致伺服器被擷取位置及順序不一致。 因此，很難得到未分類的值。

對於維 **度有** 1000萬個以上分類值的人，這是因應措施：您需要透過FTP，以1000萬個批次匯出未分類的值，並手動加以分類。

## 分類規則快速入門 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理員]** &gt;分 **[!UICONTROL 類規則產生器]**

以下是您實施分類規則的高階步驟：

| 步驟 | 執行位置 | 說明 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html). | [!UICONTROL 管理] &gt;報 [!UICONTROL 表套裝] &gt;編輯設 [!UICONTROL 定] &gt; &lt;流量分類或轉換分類&gt; | 選擇變數並定義用於該變數的分類。<br>變數至少必須先建立一個分類欄，才能夠在規則中使用。<br>啟用分類後，您可使用匯入工具和規則產生器來分類特定值。 |
| Step 2: [Create a rule set](/help/components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理員] &gt; [!UICONTROL 分類規則產生器] &gt; [!UICONTROL 新增規則集] | 規則集是一組特定變數的分類規則。 |
| 步驟3:設定報表套裝和變數。 | [!UICONTROL 分類規則產生器] &gt; &lt;您的規則集&gt; | 套用規則集至報表套裝和變數。 |
| Step 4: [Add classification rules to the set](/help/components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分類規則產生器] &gt; &lt;您的規則集&gt; | 匹配條件和分類，然後指定要針對規則採取的動作。請熟悉規則處理 [方式中的資訊](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 步驟5:測 [試分類規則集](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | 您要在「草稿」模式中編輯規則，以測試驗證的規則。無法在「草稿」模式中執行規則。<br>使用規則運算式時，此步 [驟很重要](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 |
| 步驟6:啟 [用有效規則](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 一旦規則有效，就啟動規則集。如果有必要，可以覆寫現有的索引鍵。請參閱 [規則的處理方式](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](/help/components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 刪除規則集裡不要的規則。<br>附註: 刪除規 不會刪除已 傳的分類資料。See  [Delete classification data](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>具有使用分類匯入工具權限的群組可以使用分類規則。 See [How Rules Are Processed](/help/components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**其他資源**

**部落格**:如需此功能的詳細資訊，請參閱數位行銷部落格：規 [則型分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**影片**:請造 [訪YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) ，以檢視 [!UICONTROL 分類概述] 影片。
