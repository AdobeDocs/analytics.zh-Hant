---
title: 分類概觀
description: 自訂維度項目的分組。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 0f5890679ea73c1bbea9f5d2939e89c6775c85da
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 62%

---

# 分類概觀

分類是將 Analytics 變數資料分類，然後在您產生報告時以不同方式顯示資料的方式。您在變數值和與其相關之中繼資料之間建立關係。分類可用於大部分的自訂維度，例如[追蹤代碼](/help/components/dimensions/tracking-code.md)、[prop](/help/components/dimensions/prop.md)和[eVars](/help/components/dimensions/evar.md)。

Adobe 提供多種資料分類方法。所有分類資料在報告中的運作方式均相同，您可以結合任何最符合您組織的方法。Adobe 建議使用&#x200B;**分類集**。

* **分類集**：在單一簡化介面中建立和管理分類及其規則。
* **分類規則**：建立將指定維度項目指派給分類維度項目的規則。當維度經常遇到新的唯一值，或手動分類經常發生並造成負擔時，此方法可提供最佳資料分類。
* **分類匯入工具**：匯出範本試算表，其中每列含有維度項目。欄代表維度的每個分類。當所有維度項目為已知項目，且不需要頻繁更新時，這是為資料分類的最佳方法。

單一維度可以有多個分類維度。例如，您可以使用其他的產品屬性將「[!UICONTROL 產品 ID]」分類，例如產品名稱、顏色、大小、說明和 SKU。每一個屬性都是屬於相同父維度的個別分類維度。 使用這些屬性增加報表內容，可提供更深入、更複雜的報表機會。 一旦維度包含分類資料，分類維度就可在僅包含分類維度專案的報告中使用。 不包含分類值的任何父維度專案都會分組到[未指定](/help/technotes/unspecified.md)下
