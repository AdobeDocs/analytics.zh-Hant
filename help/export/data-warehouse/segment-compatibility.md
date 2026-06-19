---
title: Data Warehouse 區段相容性
description: 瞭解哪些區段定義在Data Warehouse中有效。
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# Data Warehouse 區段相容性

並非所有內建在區段產生器中的區段都可以在Data Warehouse中使用。 使用此頁面瞭解哪些區段定義與Data Warehouse相容，以便在您[建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md)時可供選取。

只有當&#x200B;**下列**&#x200B;皆為True時，區段才與Data Warehouse相容：

* **支援的元件**：此區段僅使用Data Warehouse支援的維度和量度。
* **支援的結構**：區段的結構遵循Data Warehouse所執行的規則。

若任一條件未符合，當您建立Data Warehouse請求時，區段就不會顯示為選項；若您選取的虛擬報表套裝包含不相容的區段，則會顯示錯誤。

## 支援的元件

由於評估區段的資料與其套用到的要求相同，因此&#x200B;**Data Warehouse要求中不支援的任何元件在區段中也不支援。** 如需Data Warehouse不支援的維度和量度完整清單，請參閱Data Warehouse中的[元件支援](component-support.md)。

除了[元件支援](component-support.md)中列出的維度和量度之外，Data Warehouse *要求*&#x200B;中還提供下列維度，但&#x200B;**不能在區段定義**&#x200B;中使用：

* [[!UICONTROL 幾月幾號]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL 星期幾]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL 一年當中的第幾天]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL 當天幾點]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL 行銷管道]](/help/components/dimensions/marketing-channel.md) （改用[[!UICONTROL 上次接觸管道]](/help/components/dimensions/last-touch-channel.md)）
* [[!UICONTROL 一年中的月份]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL 找不到頁面]](/help/components/dimensions/pages-not-found.md) （請改用[[!UICONTROL 頁面型別錯誤]](/help/components/dimensions/pages-not-found.md)）
* [[!UICONTROL 一年中的季度]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL 平日/週末]](/help/components/dimensions/weekday-weekend.md)

## 支援的結構

即使區段僅使用支援的元件，其結構也必須遵循Data Warehouse所執行的規則。 區段結構完全支援、部分支援或不支援：

**支援**：

* **區段棧疊**：可以將多個區段套用至單一Data Warehouse請求。
* **巢狀容器**：支援，提供的範圍在每個層級（訪客→造訪→點選）都減少。 不支援範圍增加的容器。

**部分支援**：

* **排除容器**：僅支援最上層。 Data Warehouse僅支援可表示為`A AND NOT B`的區段，即&#x200B;**包含此特性**&#x200B;和&#x200B;**排除此特性**。 不支援排除巢狀在其他容器中的容器。
* **AND/OR logic**：支援限制。 在搭配AND/OR邏輯使用`exclusion`或`without`容器時，僅支援可重寫為`A AND NOT B`的區段。

**不支援**：

* **循序區段**：不支援使用THEN運運算元定義循序訪客導覽序列的區段。
* **「等於任何」和「不等於任何」運運算元**： Data Warehouse區段不支援這些運運算元。

## 用作維度的區段

當您在Data Warehouse報表中使用區段作為維度時，報表傳回包含`"0"`或`"1"`的欄：

* **`"0"`**：該維度項目不符合區段標準。
* **`"1"`**：該維度項目符合區段標準。
