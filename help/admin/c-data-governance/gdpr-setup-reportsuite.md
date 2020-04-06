---
description: 為報表套裝資料加上標籤表示您為指定報表套裝中的每個變數指派身分、敏感性和資料控管標籤。 請務必先熟悉標籤及其定義。
title: 標籤報表套裝資料
uuid: a694851c-8933-496e-9118-113cc38cba8a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 標籤報表套裝資料

為報表套裝資料加上標籤表示您為指定報表套裝中的每個變數指派身分、敏感性和資料控管標籤。 請務必先熟悉標籤及其定義。

>[!NOTE] 請記住，每次建立新報表套裝，或在現有報表套裝內啟用新變數時，都必須仔細檢視標籤。在啟用新的解決方案整合時，您也需要檢閱標籤，因為這些標籤可能會公開可能需要標籤的新變數。 重新實作行動應用程式或網站可能會改變現有變數的使用方式，這可能也需要更新標籤。

## 指派或編輯報表套裝標籤 {#section_39F829F35A274EACA532E2F6FF392996}

**範例**：您做為資料控管單位，計劃從資料主體收集電子郵件地址和 Cookie ID 以處理其資料隱私權請求。這些Cookie ID儲存在Adobe Analytics的報表套裝中。 若要建立電子郵件地址和Cookie ID的標籤，您必須在Analytics中使用Adobe Cloud Platform的「資料使用標籤與強制執行」(DULE)架構。

1. 在Analytics中，導覽至 **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]** > **[!UICONTROL (select report suite)]**![](assets/privacy_rs_settings.png)

1. 選取您要標籤的變數群組。

   ![](assets/variables.png)

   * **標準維度** （Adobe Analytics現成可用的維度）
   * **標準量度** （Adobe Analytics現成可用的量度）
   * **轉換事件** (自訂成功事件)
   * **銷售轉換維度** (銷售 eVars)
   * **轉換維度** （非銷售eVar）
   * **自訂流量維度** (prop)
   * **解決方案維度和事件** （與行動、視訊、Activity Map等解決方案相關的維度／事件，以及與Adobe Campaign、Adobe Experience Manager、Advertising Cloud等解決方案的整合）
   * **資料處理維度** （未透過Adobe Analytics UI直接在報表中公開的變數，但可透過資料饋送和／或資料倉庫請求提供）

1. （可選）按一下每個變數旁的資訊(i)圖示，以更好地瞭解過去90天中最常見的值。 （這項功能不適用於資料處理維度，因為Analytics UI中不提供。）

   ![](assets/info.png)

1. Select one or more variables by clicking their checkbox, then select the **[!UICONTROL Edit]** icon (to the right) to edit one or more variable(s).

   ![](assets/edit.png)

1. 「身 **分資料** 」標籤對話方塊會自動開啟。 這些標籤會分類可供自己使用或與其他資料結合使用的資料，以識別或直接與個人聯絡。 如需這些選項的詳細資訊，請參閱[身分資料標籤 (DULE)](/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels)。

   >[!NOTE]
   >
   >資料使用標籤和實行 (DULE) 架構的設計目的，是為了在解決方案/服務/平台上提供統一方式，以擷取、通訊和使用 Adobe Experience Cloud 上資料的中繼資料。中繼資料可協助資料控管單位指出哪些資料屬於個人資料、哪些資料屬於敏感資料，以及資料具有哪些合約規定。

   ![](assets/identity_labels.png)

1. 開啟&#x200B;**「敏感資料」**&#x200B;區段以設定依地理位置資料分類的敏感資料標籤。如需這些選項的詳細資訊，請參閱[敏感資料標籤 (DULE)](/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels)。

   ![](assets/sensitive_data.png)

1. 開啟「資料隱私權資料」區段以設定&#x200B;**資料控管**&#x200B;標籤。使用本節內容指示 Adobe 該如何處理資料隱私權存取和刪除請求的每個變數，以及定義應掃描哪些變數來尋找這些請求的資料主體 ID。如需這些選項的詳細資訊，請參閱[資料控管標籤 (資料隱私權)](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)。

   ![](assets/privacy_labels.png)

1. Click **[!UICONTROL Apply]** once you have completed all labeling.

## 將標籤複製到報表套裝 {#section_7C6FDAFF049F4126B84F6261F72668EE}

若您想將相同的 DULE/資料隱私權設定套用至多個報表套裝，您可以依照以下步驟操作：

1. 選取變數群組（標準維度、轉換維度等）包含您要複製的變數。 請注意，一次只能複製一組變數的標籤。
1. 選取此群組中的部分或全部變數。
1. 按一 **[!UICONTROL Copy Labels to Report Suite(s)]** 下「資料管理」對話方塊右上角的。

   ![](assets/apply_as_template.png)

1. Either check **[!UICONTROL Select All]** to copy labels for the selected variables to all report suites or select the individual report suites that you want to copy the labels to.

   >[!IMPORTANT]
   >
   >請記住，您選取的所有報表套裝都必須對應至您的 Experience Cloud 組織。

   將某個變數或一組變數的標籤複製到不同的報表套裝時，複製的標籤會出現在目標報表套裝中對應位置的變數。對於標準維度、標準量度、解決方案維度和事件以及資料處理維度，標籤將複製至目標報表套裝中名 **稱相同** 的變數。

   不過，對於轉換變數(eVar)、銷售轉換維度和自訂流量維度(prop)，復本將會複製到目標報表套裝中 **編號相同的變數** 。 例如，eVar12將複製至所有目標報表套裝的eVar12。 在決定復本的目標時，會忽略這些變數的名稱。 如果目標報表套裝中未啟用對應的變數，該變數的復本將失敗。

   複製為變數定義之分類的標籤時，標籤將複製至目標報表套裝（例如eVar7到eVar7）中對應變數的分類，其名稱與所複製之分類相同。 否則，該分類標籤的復本將會失敗。

   套用一組標籤後，會顯示狀態訊息。 狀態訊息將包含任何目標變數或分類的名稱，以及復本失敗的報表套裝。

   >[!IMPORTANT]
   >
   >每次都應該檢查目標報表套裝，確認您所複製的標籤正確無誤。這點對於含有 ID 或 DEL 標籤的變數來說尤其重要。

1. 按一下 **[!UICONTROL Apply]**.

