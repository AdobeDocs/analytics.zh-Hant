---
description: 使用資料來源的準備步驟
subtopic: Data sources
title: 準備使用資料來源
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 準備使用「資料來源」

使用資料來源的準備步驟

* [識別和命名量度](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [識別資料維度](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [促銷活動追蹤程式碼](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [交易 ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [識別資料來源資料的有效日期範圍](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 識別和命名量度 {#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

重要的是，要瞭解您的資料來源中的量度和測量，例如 *`Off-line Sales Revenue by Product`*、*`Returns by Product`* 或 *`Ad Impressions by Campaign`*。這些是您可與報表量度（事件、prop和eVar）產生關聯的名稱。

在您為Data Sources資料決定適當的量度對事件映射後，以適合相關Data Sources量度的描述性名稱重新命名事件。

請參 [閱「管理工具](https://marketing.adobe.com/resources/help/zh_TW/reference/success_event.html) 」說明中的「成功事件」。

>[!NOTE]Adobe 強烈建議讓「資料來源資料」使用新的空事件，但在少數情形下，使用原先現存的事件可能比較適當。

## 識別資料維度 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

識別並收集您要用來劃分透過Data Sources匯入之量度的資料（報表）。 此資料稱為 *`data dimensions`*。

例如，如果Data Sources量度測量廣告印象，您的資料維度可能是促銷活動追蹤代碼。 如果您是測量離線銷售，您可能會想使用產品代碼（或SKU）做為資料維度。

您可以為量度定義多個資料維度，但每個量度必須為每個關聯的資料維度提供相關值或值組合。 例如，如果您匯入「離線銷售」量度，並將其與 *`Product`**`Partner`* 資料維度關聯，則「離線銷售」量度必須與每個產品與合作夥伴組合（例如「總收入」）相關。

>[!NOTE] 可匯入無法以任何維度劃分的總量度。

在您定義要與資料來源搭配使用的資料維度後，將維度資料對應至變數，將其整合至行銷報表。 使用標準報表（例如產品、追蹤代碼、搜尋關鍵字）或轉換流量變數(eVar)。

使用eVar時，您可以使用現有的eVar或新的eVar做為資料維度。 選取要從Data Sources接收資料維度的eVar後，請務必正確命名。

請參 [閱Analytics說明](https://marketing.adobe.com/resources/help/zh_TW/reference/success_event.html) 中的成功事件。

## 促銷活動追蹤程式碼 {#section_468222796FF449ABAA90D88EB3264CB1}

除了匯入成功事件外，您也可以選擇匯入相關的eVar值。 例如，如果您使用促銷活動追蹤代碼追蹤線上活動，並有離線量度的促銷活動追蹤代碼，則可匯入具有促銷活動追蹤代碼的量度。 此方法可讓您在促銷活動報表中檢視線上和離線度量。

如果您未匯入具有關聯eVar值的Data Sources量度，則無法檢視依eVar劃分的Data Sources量度。 您只能看到「總量度」。

## 交易 ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

交易ID可用來將線上事件連接至離線事件。

## 識別資料來源資料的有效日期範圍 {#section_03AAB1291BDC4403BDC50905A78FDB71}

定義Data Sources量度（自訂事件）和資料維度(eVar)後，請檢閱您要匯入之Data Sources資料的日期範圍。 您無法匯入現有報表資料範圍以外的資料來源。

例如，您無法匯入實施線上資料追蹤之前的資料來源資料。 Data Sources資料應依日劃分。
