---
description: 「資料控管的隱私權標籤」對話方塊提供報表套裝隱私權標籤和命名空間的概觀。 您也可以從此處將設定匯出為.csv檔案。
title: 檢視/管理資料控管的隱私權標籤
feature: Data Governance
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: aa794220b464b7665e89345a116a263189dcc3fa
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 44%

---

# 檢視/管理資料控管的隱私權標籤

>[!NOTE]
>
>此更新的UI目前正在進行有限的測試。

此 **[!UICONTROL 資料控管的隱私權標籤]** 對話方塊提供報表套裝隱私權標籤和命名空間的概觀。 您也可以從此處將設定匯出為.csv檔案。

## 檢視隱私權標籤 {#view-privacy}

1. 登入 Adobe Experience Cloud。
1. 導覽至  **[!UICONTROL Analytics]** > **[!UICONTROL 管理]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 資料配置和收集]** > **[!UICONTROL 資料控管]**.

   >[!NOTE]
   >
   >如果您沒有看到此選單項目，則需要將您新增到具有此功能權限的 [Admin Console 的產品設定檔](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hant)。

1. 在右上角選取您要檢視或管理其隱私權標籤的報表套裝。

   ![](assets/privacy_labeling.png)

| 設定 | 說明 |
| --- | --- |
| **[!UICONTROL 元件名稱]** | 此欄列出屬於此報表套裝的所有元件（維度、量度）。 |
| **[!UICONTROL 身分]** | 身分資料「I」標籤可用來分類可識別身分或聯絡特定人員的資料。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#identity-data-labels) |
| **[!UICONTROL 靈敏度]** | 系統會使用敏感資料「S」標籤，將地理資料等敏感資料加以分類。未來將會引入其他敏感資料標籤，以識別其他類型的敏感資訊。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#sensitive-data-labels) |
| **[!UICONTROL GDPR存取]** | 資料控管標籤讓使用者能夠分類資料，這些資料會反映隱私權相關考量事項，以及遵循法規和公司政策的合約條件。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-access-labels) |
| **[!UICONTROL GDPR刪除]** | 惟欄位含有允許點擊與資料主體建立關聯的值時 (亦即允許辨識資料主體的身分)，才需要使用刪除標籤。 其他個人資訊 (我的最愛、瀏覽/購物記錄、健康情況等)則不需要刪除，因為與資料主體之間的關聯將遭到截斷。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#data-privacy-delete-labels) |
| **[!UICONTROL 命名空間]** | 當您將變數標示為 ID-DEVICE 或 ID-PERSON 時，系統會提示您提供命名空間。您可以使用先前定義的命名空間或定義新的命名空間。[了解更多](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-labels.html?lang=en#section_F0A47AF8DA384A26BD56032D0ABFD2D7) |
| **[!UICONTROL 類別]** | 指元件的類型，例如標準元件、轉換變數等。 |

{style=&quot;table-layout:auto&quot;}

## 將隱私權標籤複製到報表套裝  {#copy-to-rs}

如果您想要將相同的DULE/資料隱私權設定套用至多個報表套裝，請遵循下列步驟：

1. 選取您要複製的變數。 請注意，您一次只能複製一個變數的標籤。
1. 按一下 **[!UICONTROL 複製至報表套裝]** 在「資料控管」對話方塊的底部。

   ![複製至報表套裝](assets/copy_to_reportsuite.png)

1. 產生的畫面會顯示變數名稱、您目前嘗試複製的標籤、報表套裝及其ID，以及目標報表套裝中的設定是否相符。

   ![將標籤複製到報表套裝](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >請記住，您選取的所有報表套裝都必須對應至您的 Experience Cloud 組織。

   將某個變數或一組變數的標籤複製到不同的報表套裝時，複製的標籤會出現在目標報表套裝中對應位置的變數。對於標準元件、清單變數和成功事件，標籤將會以 **相同名稱** 在目標報表套裝中。

   不過，針對轉換變數(eVar)和流量Dimension(prop)，復本會複製到具有 **相同數字** 在目標報表套裝中。 例如，系統會將 eVar12 複製到所有目標報表套裝中的 eVar12。在判斷複製目標時，系統會忽略這些變數的名稱。如果目標報表套裝未啟用對應的變數，該變數的複製作業將會失敗。

   複製為變數定義之分類的標籤時，標籤會複製到目標報表套裝中對應變數的分類(例如eVar7到eVar7)，其名稱與要複製的分類相同。 否則，該分類標籤的複製作業將會失敗。

1. 勾選設定相符的一或多個報表套裝旁的方塊。
1. 按一下&#x200B;**[!UICONTROL 套用]**。

   套用標籤後會顯示狀態訊息。 狀態訊息包含任何目標變數或分類的名稱，以及複製失敗的報表套裝。

   >[!IMPORTANT]
   >
   >每次都應該檢查目標報表套裝，確認您所複製的標籤正確無誤。這點對於含有 ID 或 DEL 標籤的變數來說尤其重要。

## 匯出為.csv檔案

您可以下載CSV檔案，其中包含所選報表套裝之所有變數的所有目前標籤定義。建議您的法律團隊檢閱您的標籤選擇，此選項有助於進行此次檢閱。 您可以將 .CSV 檔案分享給他們，而不必在登入資料控管 UI 的情況下執行審核程序。

1. 按一下 **[!UICONTROL 匯出CSV]** 對話方塊隨即顯示：

   ![](assets/export_csv.png)

1. 選取您要匯出所有資料控管設定的一或多個報表套裝。

## 編輯隱私權標籤

請參閱 [指派或編輯報表套裝隱私權標籤](/help/admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md).
