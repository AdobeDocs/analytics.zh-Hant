---
title: 分類概觀
description: 自訂維度項目的分組。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 1e209d4313c3d9d67f15a0c3a0939ceeb7a1ed31
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 87%

---

# 分類概觀

分類是將 Analytics 變數資料分類，然後在您產生報告時以不同方式顯示資料的方式。您在變數值和與其相關之中繼資料之間建立關係。大多數自訂維度皆可使用分類，例如[追蹤程式碼](/help/components/dimensions/tracking-code.md)、[Prop](/help/components/dimensions/prop.md) 以及 [eVar](/help/components/dimensions/evar.md)。

* **分類集**&#x200B;是用來分類資料的主要元件。 [分類設定](/help/components/classifications/sets/overview.md)可讓您在單一簡化介面中建立和管理分類。

* **舊式分類**&#x200B;會記錄用來分類資料的舊式分類方法。 這些方法已淘汰，而且在 2026 年 8 月 31 日之後將無法再存取。

   * [分類規則](/help/components/classifications/crb/classification-rule-builder.md)：建立將指定維度項目指派給分類維度項目的規則。當維度經常遇到新的唯一值，或必須經常進行手動分類且造成負擔時，這是資料分類的最合適方法。
   * [分類匯入工具](/help/components/classifications/importer/c-working-with-saint.md)：匯出範本試算表，其中每列含有維度項目。欄代表維度的每個分類。當所有維度項目為已知項目，且不需要頻繁更新時，這是為資料分類的最佳方法。

單一維度可以具有多個分類維度。例如，您可以使用其他產品屬性來分類[!UICONTROL 產品 ID]，例如產品名稱、顏色、尺寸、說明以及 SKU。上述每一個屬性都會是獨立的分類維度，且隸屬於同一個上層維度。使用這些屬性來強化您的報告，可提供更深入且更複雜的報告機會。只要維度包含分類資料，唯有僅包含分類維度項目的報告才可以使用該分類維度。任何未包含分類值的上層維度項目，皆會歸類為[未指定](/help/technotes/unspecified.md)。
