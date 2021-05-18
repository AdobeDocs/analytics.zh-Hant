---
description: 開始建立虛擬報告套裝前，請謹記以下一些注意事項。
keywords: 虛擬報告套裝
title: 建立虛擬報告套裝
feature: Reports and Analytics 基本需知
uuid: 022a6656-808e-4c92-b7ec-4d2a42e84fa8
exl-id: 5ff6ff1a-5b99-41cc-a3a7-928197ec9ef9
source-git-commit: 20bd38fc38fb14d724603b492bf093d313acbb7d
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 73%

---

# 建立虛擬報告套裝

開始建立虛擬報告套裝前，請謹記以下一些注意事項。

* 非管理員使用者看不到「虛擬報告套裝管理器」。
* 虛擬報告套裝無法共用。「共用」是透過群組/權限達成。
* 在「虛擬報告套裝管理器」中，您只看得到您自己的虛擬報告套裝。必須按一下「全部顯示」才能查看其他人的虛擬報告套裝。

1. 導覽至「**[!UICONTROL 元件]** > **[!UICONTROL 虛擬報告套裝]**」。
1. 按一下&#x200B;**[!UICONTROL 「新增 +」]**。

   ![](assets/new_vrs.png)

## 定義設定

在[!UICONTROL Settings]標籤上，定義這些設定，然後按一下&#x200B;**[!UICONTROL Continue]**。

| 元素 | 說明 |
| --- |--- |
| 名稱 | 虛擬報告套裝的名稱不會繼承自父報告套裝，且應為不同的名稱。 |
| 說明 | 為您的企業使用者著想，加入適當說明。 |
| 標記 | 您可新增標記來組織報告套裝。 |
| 來源 | 此虛擬報套裝會繼承報告套裝的以下設定。繼承大部分的服務層級和功能 (例如 eVar 設定、處理規則、分類等)。若要在 VRS 上變更這些繼承設定，您必須編輯父報告套裝 (「管理員 > 報告套裝」)。 |
| 時區 | 選擇時區是選用的。如果您選擇了時區，則會與 VRS 一併儲存。如果您沒有選擇時區，則系統會使用父報告套裝的時區。編輯 VRS 時，隨著 VRS 儲存的時區將顯示在下拉式選擇器中。如果系統新增時區支援之前，VRS 已經建立，則父報告套裝的時區會顯示在下拉式選擇器中。 |
| 區段 | 您可以只新增一個區段，也可以堆疊區段。注意：將兩個區段堆疊在一起時，會使用 AND 陳述式加以連結。無法變更為 OR 陳述式。如果嘗試刪除或修改虛擬報告套裝目前使用中的區段，便會出現警告。 |

## 定義瀏覽定義

在[!UICONTROL 瀏覽定義]標籤上，定義這些設定，然後按一下&#x200B;**[!UICONTROL 繼續]**。

![](assets/visit-definition.png)

| 元素 | 說明 |
| --- |--- |
| **設定造訪定義** |  |
| 啟用報表時間處理功能 | 使用報表時間處理功能，以變更預設造訪逾時長度。這些設定不具破壞性，只會套用至 Analysis Workspace。[了解更多](/help/components/vrs/vrs-report-time-processing.md) |
| 造訪逾時 | 定義自動開始新的造訪之前，不重複訪客需達到的閒置時間。這會影響造訪量度、造訪區段容器，以及在造訪時過期的 eVar。 |
| 因事件而開始新的造訪 | 不論工作階段是否逾期，只要觸發了指定事件，就會作為新的工作階段開始。 |
| **行動應用程式造訪設定** | 修改使用 Adobe 的 Mobile SDK 從行動應用程式收集點擊數的造訪次數定義。這些設定不具破壞性，只會套用至 Analysis Workspace。 |
| 避免將背景點擊動作計為新的造訪 | 可避免將背景點擊動作計為新的造訪，以免「造訪次數」和「不重複訪客」數據膨脹失真。 |
| 每次應用程式啟動時，即開始新的造訪 | 應用程式啟動後，便開始新的工作階段。[了解更多](/help/components/vrs/vrs-mobile-visit-processing.md) |

## 包含和重新命名元件

![](assets/components.png)

1. 在[!UICONTROL 元件]標籤上，選取核取方塊以套用組織，以包含、排除和重新命名此Analysis Workspace虛擬報表套裝的元件。
如需VRS組織的詳細資訊，請參閱[虛擬報表套裝元件組織](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=en#virtual-report-suites)。

1. 將您要包含在VRS中的元件（維度、量度、區段或日期範圍）拖曳至[!UICONTROL 包含的元件]區段。

1. 完成後，按一下&#x200B;**[!UICONTROL 保存]**。

## 預覽資料

在每個標籤的右側，您可以預覽此虛擬報表套裝中與原始報表套裝相比的點擊總數、瀏覽總數和訪客總數。

## 檢視產品相容性

虛擬報表套裝的某些功能並不受所有Adobe Analytics產品支援。 產品相容性清單可讓您根據目前的虛擬報表套裝設定，查看Adobe Analytics地區哪些產品受支援。
