---
description: 處理規則可簡化資料收集，以及管理傳送至報告的內容。
subtopic: Processing rules
title: 處理規則概觀
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# 處理規則概觀

處理規則可讓您在資料寫入報表套裝之前，先修改資料的收集方式。

**[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** >選取報表套裝> **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 處理規則]**

>[!WARNING]
>
>處理規則直接影響資料收集，如果使用不正確，可能會造成資料遺失。 一律先在開發報表套裝中測試處理規則，然後在生產報表套裝中啟用這些規則以緩解資料品質問題。

處理規則的兩個主要使用案例包括：

* **使用內容資料變數實作工作流程**：您不必直接在實作中設定變數，而是可以使用[內容資料變數](/help/implement/vars/page-vars/contextdata.md)來設定索引鍵/值配對。 例如，不要設定：

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  您可以改為設定：

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  然後，您可以在Analytics UI中將內容資料變數對應至所需的維度和量度。

  與組織中的開發人員通訊以在屬性上實施Analytics時，使用內容資料變數可簡化通訊程式。 開發人員只需實作每個索引鍵/值組一次，您身為Analytics管理員可確保資料匯入正確的實作變數。

* **在收集資料時修改資料**：此使用案例包含各種應用程式，例如暫時修正資料品質或協助填補實作空白。 如需詳細資訊與特定範例，請參閱[處理規則使用案例](pr-use-cases.md)。

## 權限

產品管理員預設擁有處理規則的存取權。 您可以將處理規則的存取權授與非管理員，方法是將其納入包含&#x200B;**[!UICONTROL 處理規則]**&#x200B;許可權專案的產品設定檔中。 如需詳細資訊，請參閱[報表套裝工具的產品設定檔許可權](/help/admin/admin-console/permissions/report-suite-tools.md)。

## 建立或編輯處理規則時的注意事項

建立或編輯處理規則時，請考量下列事項：

* **可能的空白值**：建立規則時，請考慮覆寫值為空白的情況。 例如，如果您有使用eVar2覆寫eVar1的規則，而eVar2是空的，兩個變數都會被清除。 Adobe建議先新增條件，檢查變數值，再使用它覆寫其他值。
* **儲存後立即套用**：處理規則會在您儲存收集的資料時套用至這些資料。 它們不會回溯套用至已收集的資料。
* **規則內的處理順序**：如果您有多個處理規則，它們執行的順序很重要。 請務必確認，如果您在多個規則中使用指定變數，這些規則會以正確順序執行。 如果您覆寫規則1中的eVar3，該原始eVar3值就無法用於任何後續規則。
* **資料收集管道中的處理順序**：請參閱[Adobe Analytics中的資料處理順序](/help/technotes/processing-order.md)，瞭解處理規則在整個資料收集管道中的套用位置。
* **編碼**：幾乎所有情況下都採用UTF-8編碼。
* **區分大小寫**：處理規則中的字串比較不區分大小寫。 您用來覆寫值的字串值，會使用與直接填入變數相同的規則。
* **單一報表套裝**：當您編輯處理規則時，這些規則只會套用至一個報表套裝。 在報表套裝管理員中選取多個報表套裝，即可強制選取單一報表套裝。 建立或編輯所需的處理規則後，您可以[將這些規則](pr-copy.md)複製到其他報表套裝。
* **沒有資料排除**：排除資料不是處理規則的預定功能。 請考慮在資料收集層級使用[`abort`](/help/implement/vars/config-vars/abort.md)，或在收集資料後使用[VISTA規則](/help/technotes/vista.md)。
* **可用的變數**：並非所有維度和量度都可在處理規則中使用。 如需支援專案的完整清單，請參閱[可用於處理規則的維度和量度](pr-variables.md)。
* **允許的規則數目**：每個報表套裝最多可包含150個規則。 每個規則最多可包含30個條件。

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [使用處理規則將內容資料變數對應至prop和eVar](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
