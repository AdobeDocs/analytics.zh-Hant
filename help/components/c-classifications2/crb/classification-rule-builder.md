---
description: 您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。
seo-description: 您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。
seo-title: 分類規則產生器工作流程
solution: Analytics
subtopic: '分類   '
title: 分類規則產生器工作流程
topic: 管理工具
uuid: edb1f07e-fa86-4055-8f4 b-cce2 d370 edb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# 分類規則產生器工作流程

您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。

## 開始之前的重要通知

開始使用分類規則之前，請記住：

* 我們目前的分類系統一次只能匯出高達1000000列。
* 當分類規則產生器(CRB)請求匯出時，它會提取分類和未分類的值，並在匯出結束時傳遞未分類的值。這表示隨著時間的推移，您可能會填滿1000萬個分類值-而不會得到未分類的值。
* 由於架構是以CRM從伺服器的「n」個數來設定的，因此可能會導致伺服器在哪一個順序下被挑選和排序。因此，很難取得未分類的值。

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## 分類規則快速入門 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL 管理員]** &gt; **[!UICONTROL 分類規則產生器]**

以下是您實施分類規則所採取的高階步驟：

| 步驟 | 執行位置 | 說明 |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL 管理員] &gt; [!UICONTROL 報表套裝] &gt; [!UICONTROL 編輯設定] &gt;&lt;流量分類或轉換分類&gt; | 選擇變數並定義用於該變數的分類。<br>變數至少必須先建立一個分類欄，才能夠在規則中使用。<br>啟用分類後，您可使用匯入工具和規則產生器來分類特定值。 |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL 管理員] &gt; [!UICONTROL 分類規則產生器] &gt; [!UICONTROL 新增規則集] | 規則集是一組特定變數的分類規則。 |
| 步驟3：設定報表套裝和變數。 | [!UICONTROL 分類規則產生器] &gt;&lt;您的規則集&gt; | 套用規則集至報表套裝和變數。 |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL 分類規則產生器] &gt;&lt;您的規則集&gt; | 匹配條件和分類，然後指定要針對規則採取的動作。Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | 您要在「草稿」模式中編輯規則，以測試驗證的規則。無法在「草稿」模式中執行規則。<br>使用 [規則運算式](../../../components/c-classifications2/crb/classification-quickstart-rules.md)時，這個步驟很重要。 |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 一旦規則有效，就啟動規則集。如果有必要，可以覆寫現有的索引鍵。請參閱 [規則的處理方式](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | 刪除規則集裡不要的規則。<br>附註: 刪除規 不會刪除已 傳的分類資料。See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>具有使用分類匯入工具權限的群組可以使用分類規則。See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**其他資源**

**部落格**：如需此功能的其他資訊，請參閱數位行銷部落格： [規則型分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**影片**：請造訪 [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) 以檢視 [!UICONTROL 「分類概述] 」視訊。
