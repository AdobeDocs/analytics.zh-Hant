---
title: 將標記資料元素對應至 Analytics 變數
description: 將資料元素指派給 Analytics 變數，好讓您可以在 Analysis Workspace 中將其當成維度使用。
feature: Tags
exl-id: 996c1204-3f8a-453e-8104-5e8e1279517c
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 96%

---


# 將標記資料元素對應至 Analytics 變數

當您擁有標記資料元素的存放庫之後，您可以將其指派給 Analytics 維度。

## 先決條件

[將資料層物件對應至資料元素](layer-to-elements.md)：請確定您了解標記資料元素，並且擁有數個可使用的元素。

[建立解決方案設計文件](../prepare/solution-design.md)：解決方案設計文件對於保持井然有序非常重要。按照解決方案設計文件操作，可簡化將資料元素指派給 Analytics 變數的作業。

## 將資料元素指派給 Analytics 變數

按照下列步驟操作後，發佈標記庫可讓您在 Analysis Workspace 中使用自訂維度。 您可以在全域或個別規則中設定 Analytics 變數。

### 設定全域變數

想在有資料元素的所有頁面上設定變數值，適合使用全域變數。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下[!UICONTROL 「擴充功能」標記]，然後按一下 Adobe Analytics 擴充功能下方的[!UICONTROL 「設定」]。
1. 按一下[!UICONTROL 「全域變數」]摺疊式功能表，這會顯示指派全域變數的介面。

### 在規則中設定變數

不想在每個頁面上設定變數，適合使用規則中設定的變數。您可以在規則中定義標準。請參閱 Adobe Experience Platform 標記文件中的「[規則](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html?lang=zh-Hant)」。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 按一下[!UICONTROL 「規則」]標記，然後按一下所需的規則 (或建立規則)。
1. 按一下[!UICONTROL 「動作」]中的[!UICONTROL 「新增」]按鈕。
1. 將[!UICONTROL 擴充功能]下拉式清單設定為Adobe Analytics，並將[!UICONTROL 動作型別]設定變數。
1. 按一下所需 Analytics 變數右側的![「資料元素」](assets/data-element.png)圖示。您組織的[解決方案設計文件](../prepare/solution-design.md)會規定要使用的 Analytics 變數。
1. 在強制回應視窗中選取所需的資料元素。按一下[!UICONTROL 「選取」]。
1. 資料元素名稱會新增至由 `%` 符號包住的文字欄位。例如，如果您將資料元素命名為「Page name」，會在將資料元素指派至變數時看到字串 `%Page name%`。

>[!TIP]
>
>您可以串連相同變數中的資料元素。舉例來說，如果您有「Hostname」資料元素和「Pathname」資料元素，可使用 `%Hostname%%Pathname%` 將兩者合併成單一變數。

## 後續步驟

[頁面變數](../vars/page-vars/page-variables.md)：了解您可在實作中使用的頁面層級變數，以便在 Analysis Workspace 中進一步運用維度。

[設定變數](../vars/config-vars/configuration-variables.md)：了解您可在實作中使用的設定變數，以解鎖 Adobe Analytics 的更多功能。
