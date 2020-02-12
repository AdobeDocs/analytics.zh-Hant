---
description: 您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。
subtopic: Classifications
title: 分類規則產生器工作流程
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: f6b528f8a1b89a008a736fa62d58d6e83f13e4e4

---


# 分類規則產生器工作流程

您可以建立自動的規則型分類並套用至多個報表套裝，如此就無須在每次追蹤程式碼變更時維護和上傳分類。視您的分類相關流量大小而定，會以頻繁間隔處理規則。

## 開始使用前的重要注意事項

開始使用分類規則前，請記住以下事項:

* 分類規則產生器(CRB)不支援子分類。
* 我們目前的分類系統一次最多只能匯出 1000 萬列。
* 當CRB要求匯出時，它會同時提取已分類的AND未分類值，未分類的值會在匯出結束時傳遞。 這表示隨著時間推移，最多可填入 1000 萬個分類值，永遠不需要尋找未分類的值。
* 由於此架構的設定方式可讓 CRB 從「n」個伺服器中提取資料，因此可能會導致擷取的伺服器及順序不一致。基於上述原因，要取得未分類的值相當困難。

若您的一個維度有 1000 萬個以上分類值，以下提供&#x200B;**因應措施**: 您需要透過 FTP 匯出未分類的值 (一個批次 1000 萬個)，並手動加以分類。

## 分類規則快速入門 {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

以下是實作分類規則所需的高層級步驟:

| 步驟 | 執行位置 | 說明 |
|--- |--- |--- |
| 步驟 1 (必要條件): [設定分類結構](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html)。 | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > &lt;流量分類或轉換分類> | 選擇變數並定義用於該變數的分類。<br>變數至少必須先建立一個分類欄，才能夠在規則中使用。<br>啟用分類後，您可使用匯入工具和規則產生器來分類特定值。 |
| 步驟 2: [建立規則集](/help/components/c-classifications2/crb/classification-rule-set.md)。 | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | 規則集是一組特定變數的分類規則。 |
| 步驟 3: 設定報表套裝與變數。 | [!UICONTROL Classification Rule Builder] >  &lt;您的規則集> | 套用規則集至報表套裝和變數。 |
| 步驟 4: [將分類規則新增到規則集](/help/components/c-classifications2/crb/classification-quickstart-rules.md)。 | [!UICONTROL Classification Rule Builder] >  &lt;您的規則集> | 匹配條件和分類，然後指定要針對規則採取的動作。請詳閱[規則的處理方式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)中的資訊。 |
| 步驟 5: [測試分類規則集](/help/components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | 您要在「草稿」模式中編輯規則，以測試驗證的規則。無法在「草稿」模式中執行規則。<br>使用[規則運算式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)時，此步驟很重要。 |
| 步驟 6: [啟用有效規則](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 一旦規則有效，就啟動規則集。如果有必要，可以覆寫現有的索引鍵。請參閱[規則的處理方式](/help/components/c-classifications2/crb/classification-quickstart-rules.md). |
| 步驟 7 (選用): [刪除不要的規則](/help/components/c-classifications2/crb/classification-rule-definitions.md)。 | [!DNL Rules Page] | 刪除規則集裡不要的規則。<br>附註: 刪除規則不會刪除已上傳的分類資料。如需刪除已分類的資料，請參閱[刪除分類資料](/help/components/c-classifications2/c-classifications-importer/t-delete-classification-data.md)。 |

>[!NOTE]
>
>擁有使用分類匯入工具之權限的群組可以使用分類規則。請參閱[規則的處理方式](/help/components/c-classifications2/crb/classification-quickstart-rules.md)以取得重要的處理資訊。

**其他資源**

**部落格**: 如需此功能的其他相關資訊，請參閱 Digital Marketing Blog 上的[規則型分類](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)。

**影片**:請造 [訪YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) ，以檢視 [!UICONTROL Classifications Overview] 影片。
