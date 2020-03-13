---
title: 將啟動資料元素對應至Analytics變數
description: 將資料元素指派給Analytics變數，以便在分析工作區中將它們當做維度使用。
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# 將啟動資料元素對應至Analytics變數

在Adobe Experience Platform Launch中擁有資料元素的儲存庫後，您就可以將其指派給Analytics維度。

## 必備條件

[將資料層物件對應至資料元素](layer-to-elements.md):請確定您瞭解Launch中的資料元素，以及您有數個要處理的元素。

[建立解決方案設計檔案](../prepare/solution-design.md):解決方案設計檔案對於保持井然有序至關重要。 遵循解決方案設計檔案可簡化資料元素對Analytics變數的指派。

## 指派資料元素至Analytics變數

依照下列步驟後，在Launch中發佈程式庫可讓您在分析工作區中使用自訂維度。 您可以全域或個別規則中設定Analytics變數。

### 設定全域變數

在您想要在資料元素所在的所有頁面上設定變數值時，最適合使用全域變數。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下所要的「啟動」屬性。
1. 按一下 [!UICONTROL Extensions tab]，然後按一 [!UICONTROL Configure] 下Adobe Analytics擴充功能下方的。
1. 按一下 [!UICONTROL Global variables] accordion，可顯示要指派全域變數的介面。

### 在規則中設定變數

規則中的變數集最適合不希望在每個頁面上設定變數的情況。 您可以在規則中定義標準。 See [Rules](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html) in the Adobe Experience Platform Launch user guide.

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下所要的「啟動」屬性。
1. 按一下 [!UICONTROL Rules] 標籤，然後按一下所要的規則（或建立一個規則）。
1. 按一下下 [!UICONTROL Add] 方的按鈕 [!UICONTROL Actions]。
1. 將下拉 [!UICONTROL Extension] 式清單設定為Adobe Analytics，並設定 [!UICONTROL Action Type] 變數。
1. 按一 [!D下所需](assets/data-element.png) Analytics變數右側的資料元素圖示。 您組織的解決方 [案設計檔案](../prepare/solution-design.md) ，決定要使用哪些Analytics變數。
1. 在模型窗口中選擇所需的資料元素。 按一下 [!UICONTROL Select].
1. 資料元素名稱會新增至由符號所環繞的文字 `%` 欄位。 例如，如果您將資料元素命名為「頁面名稱」，則在將資料元素指派 `%Page name%` 至變數時，會看到字串。

> [!TIP] 您可以串連相同變數中的資料元素。 例如，如果您有「主機名」資料元素和「路徑名」資料元素，則可使用將兩者結合為單一變數 `%Hostname%%Pathname%`。

## 後續步驟

[頁面變數](../vars/page-vars/page-variables.md):瞭解您可在實施中使用哪些頁面層級變數，以便在分析工作區中進一步運用維度。

[組態變數](../vars/config-vars/configuration-variables.md):瞭解您可在實作中使用哪些設定變數，以解除鎖定Adobe Analytics中的更多功能。
