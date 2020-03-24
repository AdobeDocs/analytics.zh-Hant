---
description: 使用資料來源的準備步驟
subtopic: Data sources
title: 準備使用資料來源
topic: Developer and implementation
uuid: 876ea069-574b-4e23-93b7-e3828bfd90f5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 準備使用「資料來源」

使用資料來源的準備步驟

* [識別及命名量度](/help/import/c-data-sources/datasrc-preparing.md#section_0D1DA6D7768E4C4CB6E9A2F4639C0135)
* [識別資料維度](/help/import/c-data-sources/datasrc-preparing.md#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A)
* [促銷活動追蹤程式碼](/help/import/c-data-sources/datasrc-preparing.md#section_468222796FF449ABAA90D88EB3264CB1)
* [交易 ID](/help/import/c-data-sources/datasrc-preparing.md#section_D9513C1204B7496C9B738C5B12CCCFC7)
* [識別「資料來源」資料的有效日期範圍](/help/import/c-data-sources/datasrc-preparing.md#section_03AAB1291BDC4403BDC50905A78FDB71)

## 識別及命名量度{#section_0D1DA6D7768E4C4CB6E9A2F4639C0135}

重要的是，要瞭解您的資料來源中的量度和測量，例如 *`Off-line Sales Revenue by Product`*、*`Returns by Product`* 或 *`Ad Impressions by Campaign`*。這些是可以用報表量度關聯的名稱 (event、prop 及 eVar)。

為資料來源的資料決定適當的量度-事件映射後，針對關聯的資料來源量度，以適當的描述名稱重新命名事件。

請參閱「管理工具」說明中的「[成功事件](https://marketing.adobe.com/resources/help/zh_TW/reference/success_event.html)」。

> [!NOTE]Adobe 強烈建議讓「資料來源資料」使用新的空事件，但在少數情形下，使用原先現存的事件可能比較適當。

## 識別資料維度 {#section_8EC6BDC4AA314D9EB85F6FCD8E6ABC0A}

識別及收集您想使用的資料 (報表)，用來劃分透過資料來源匯入的量度。這種資料叫做&#x200B;*`data dimensions`*.

例如，若資料來源量度是測量廣告印象，資料維度可能是促銷活動追蹤代碼。若是測量離線銷售，可能會使用產品代碼 (或 SKU) 做為資料維度。

您可以替一個量度定義多個資料維度，但每個量度必須為每一個關聯的資料維度提供一個相關值或值的組合。例如，如果您匯入「離線銷售」量度，並將其與&#x200B;*`Product`* 和 *`Partner`* 資料維度建立關聯，「離線銷售」量度與產品及合作夥伴的每種組合 (例如，總收入) 必定相關。

> [!NOTE] 可匯入無法以任何維度劃分的總量度。

在定義資料來源要使用的資料維度後，將維度資料映射到變數，即可將其整合到行銷報表中。使用標準報告 (如產品、追蹤代碼、搜尋關鍵字) 或轉換流量變數 (eVar)。

若是 eVar，您可使用現存 eVar 或新的 eVar 做為資料維度。選取接受資料來源資料維度的 eVar 後，確定您將 eVar 正確命名。

請參閱「分析說明」中的「[成功事件](https://marketing.adobe.com/resources/help/zh_TW/reference/success_event.html)」。

## 促銷活動追蹤程式碼 {#section_468222796FF449ABAA90D88EB3264CB1}

除了匯入成功事件，您也可以選擇匯入關聯的 eVar 值。例如，若您以促銷活動追蹤代碼追蹤線上活動，且離線量度有促銷活動追蹤代碼，就可以用促銷活動追蹤代碼匯入量度。這個方法讓您可以在促銷活動報表中檢視線上和離線量度。

如果您匯入資料來源量度時沒有匯入相關聯的 eVar 值，則無法檢視依 eVars 劃分的資料來源量度。只能看到總量度。

## 交易 ID {#section_D9513C1204B7496C9B738C5B12CCCFC7}

交易 ID 是用於將線上事件連結到離線事件。

## 識別「資料來源」資料的有效日期範圍{#section_03AAB1291BDC4403BDC50905A78FDB71}

定義您的資料來源量度 (自訂事件) 和資料維度 (eVar) 後，檢查您要匯入之資料來源資料的日期範圍。您無法匯入現存報表資料範圍以外的資料來源。

例如，您不能匯入實施 線上資料追蹤以前的「資料來源」。資料來源應以天劃分。
