---
title: 分類概觀
description: 自訂維度項目的分組。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 84%

---

# 分類概觀

分類是將 Analytics 變數資料分類，然後在您產生報告時以不同方式顯示資料的方式。 您在變數值和與其相關之中繼資料之間建立關係。 大多數自訂維度皆可使用分類，例如[追蹤程式碼](/help/components/dimensions/tracking-code.md)、[Prop](/help/components/dimensions/prop.md) 以及 [eVar](/help/components/dimensions/evar.md)。

* **分類集**&#x200B;是資料分類的主要元件。 [分類集](/help/components/classifications/sets/overview.md)可讓您在單一簡化的介面中建立和管理分類。

* **舊版分類**&#x200B;記錄了用於將資料分類的舊版分類方法。 這些方法將在不久的未來淘汰，並將不再可供存取。

   * [分類規則](/help/components/classifications/crb/classification-rule-builder.md)：建立將指定維度項目指派給分類維度項目的規則。 當維度經常遇到新的唯一值，或必須經常進行手動分類且造成負擔時，這是資料分類的最合適方法。 此功能將於2027年2月28日後淘汰。

   * [分類匯入工具](/help/components/classifications/importer/c-working-with-saint.md)：匯出範本試算表，其中每列含有維度項目。 欄代表維度的每個分類。 當所有維度項目為已知項目，且不需要頻繁更新時，這是為資料分類的最佳方法。 此功能將於2026年8月31日後淘汰。 隨著支援終止，您將無法再使用標準FTP匯入分類。

單一維度可以具有多個分類維度。 例如，您可以使用其他產品屬性來分類[!UICONTROL 產品 ID]，例如產品名稱、顏色、尺寸、說明以及 SKU。 上述每一個屬性都會是獨立的分類維度，且隸屬於同一個上層維度。 使用這些屬性來強化您的報告，可提供更深入且更複雜的報告機會。 只要維度包含分類資料，唯有僅包含分類維度項目的報告才可以使用該分類維度。 任何未包含分類值的上層維度項目，皆會歸類為[未指定](/help/technotes/unspecified.md)。
