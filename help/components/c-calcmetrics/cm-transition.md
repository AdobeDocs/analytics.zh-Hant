---
description: 這些對計算量度在Analytics中運作方式的變更可能會影響您。
title: 常見問題集
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 常見問題集

[!DNL Analytics] 中的以下計算量度運作方式有所變更，可能會對您造成影響。

[如何存取計算量度產生器？](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[如何存取計算量度管理員？](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[為什麼會看到許多名稱相同的計算量度？](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[全域計算量度有什麼改變？](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[在登入公司間共用的全域計算量度有什麼改變？](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[具有數值或數值 2 分類的計算量度有什麼改變？](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[期限量度有什麼改變？](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[根據每日/每週/每月/每季/每年獨特訪客量度的計算量度有哪些需知事項？](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[使用舊版報表套裝 API 方法建立或管理的計算量度有什麼改變？](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[目前的資料支援所有計算量度類型嗎？](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[「未提供名稱」和移轉的計算量度一起出現代表什麼意思？](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[刪除某個使用者後，該使用者的計算量度會發生什麼事？](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[為什麼會看到對其他報表套裝無效的「未知」計算量度 (即使可對這些報表套裝建立和套用這些量度)？](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[為什麼我對舊式計算量度進行的變更無法儲存？](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[為什麼我的計算量度沒有顯示在行銷管道報表中？](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[為什麼有些計算量度只顯示公式，卻沒有我加入的括號？](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[(僅適用於 Ad Hoc Analysis) 仍支援包含嵌入或內嵌區段定義的計算量度嗎？](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(僅適用於 Report Builder) 為什麼計算量度沒有出現在我的請求中？](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[計算量度總計如何運作？](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## 如何存取計算量度產生器？{#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## 如何存取計算量度管理員？{#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Components]** in the left navigation. 然後按一下 **[!UICONTROL Calculated Metrics]**。

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## 為什麼會看到許多名稱相同的計算量度？{#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(以前，全域計算量度並非由任何特定管理員使用者擁有，而且該報表套裝的所有使用者都看得到。 量度是依報表套裝區分。 如果一個報表套裝中的量度與另一個報表套裝中的量度名稱相同，在使用者切換報表套裝時，該量度就會顯示為相同的量度。)

現在，量度不再依報表套裝區分。 如果一個報表套裝中的量度與另一個報表套裝中的量度名稱相同，它們將同時顯示在計算量度產生器和量度選擇器中，而且即使量度定義可能相同或不相同，也可能顯示為重複量度。

除非您取消勾選此處顯示的「(僅限 `<report suite>`)」核取方塊，否則不會看到數個名稱相同 (但建立在不同的報表套裝中) 的計算量度：

![](assets/report_suite.png)

**您需要做什麼**

請考慮合併名稱和定義相似的計算量度，但在合併時請謹慎。 您可以在計算量度管理員中檢查報表套裝中的計算量度，以確認其原始報表套裝。 刪除潛在重複項時，您也應檢查量度的定義，以確保您正確合併量度。

>[!NOTE] 即使計算量度已不再繫結至特定的報表套裝，且可用於該登入公司可見的所有報表套裝中，建立或上次儲存該計算量度的報表套裝仍會顯示在計算量度管理器中。

>[!NOTE] 即使刪除計算量度，參考該量度的書籤或控制面板報表仍可運作。

## 全域計算量度有什麼改變？{#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(以前，管理員可以透過管理工具在報表套裝中建立計算量度（稱為「全域計算量度」或「報表套裝計算量度」）。

全域計算量度現在由登入公司「管理員」使用者清單中的第一位管理員使用者擁有。 預設會與「每個人」共用。 此模式遵循與區段相同的共用模式和移轉計畫。

**您需要做什麼**

沒什麼。 但是，新管理員擁有者在修改或刪除這些計算量度時應格外小心——這些量度可用於許多書籤化報表和控制面板。

>[!NOTE] 即使刪除計算量度，參考該量度的書籤或控制面板報表仍可運作。

## 在登入公司間共用的全域計算量度有什麼改變？ {#section_59E5CD948ED643AE9AD3D2E4277647F8}

(以前，管理員可以透過管理工具在報表套裝中建立計算量度（稱為「全域計算量度」或「報表套裝計算量度」）。 然後，這些量度可新增至多個登入公司，以「共用」至各個登入公司。)

全域計算量度無法再跨登入公司共用。 它們不再系結或系結至特定報表套裝，而是系結至特定登入公司。 跨登入公司共用的計算量度

* 已移轉至能夠存取該報表套裝的所有登入公司。
* 預設值為「與所有人共用」。
* 在各登入公司中都是獨立的複本。

>[!NOTE] 如果計算量度用於書籤、控制面板、警報或計劃報表中，編輯新複本「不會」影響原本存在的計算量度。

## 具有數值或數值 2 分類的計算量度有什麼改變？{#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. 但套用了區段的報表將不支援這些量度。

此外，下列元件不支援具有數值或數值2分類的計算量度： [!UICONTROL Ad Hoc Analysis]、 [!UICONTROL Analysis Workspace][!UICONTROL Real-Time] 報告 [!UICONTROL Anomaly Detection]和 [!UICONTROL Contribution Analysis]。 當您建立或編輯具有數值或數值2分類的計算量度時，您會看到相容性警告，指出計算量度與產品的特定區域不相容。

**您需要做什麼**

如果量度要用於區段或任何不相容的元件，請避免使用數值1或數值2分類來建立計算量度。

## 期限量度有什麼改變？{#section_AEDB02EF24584DAD8731BED9DDCE4F48}

期限量度 (也稱為所有時間量度) 不再受支援，也不再顯示於 [!UICONTROL Reports & Analytics] UI 或任何其他 UI 中。報表API無法查詢這些報表。

只要報表上至少還有一個其他有效量度，任何包含所有時間量度的書籤、控制面板、計畫報表或警報都會繼續執行，而不含該量度。 如果書籤、控制面板、計畫報表或警報上的唯一量度是全時量度，報表將不再執行。

## 根據每日/每週/每月/每季/每年獨特訪客量度的計算量度有哪些需知事項？{#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

不過，下列元件不支援這些量度： [!UICONTROL Segments]、 [!UICONTROL Analysis Workspace][!UICONTROL Real-Time] 報告 [!UICONTROL Anomaly Detection]和 [!UICONTROL Contribution Analysis]。 當您建立或編輯根據獨特訪客量度的計算量度時，會出現相容性警告，指出該量度和產品的某些區域不相容。

您對具有區段的報表使用基本獨特訪客量度。 您可以建立根據獨特訪客量度的計算量度；但該計算量度無法套用至具有區段的報表，該計算量度也不能內嵌區段。

## 使用舊版報表套裝 API 方法建立或管理的計算量度有什麼改變？ {#section_13ED1BAD02634674BDAEB479B060A4B6}

以前，使用（1.3或1.4）API方法ReportSuite.SaveCalculatedMetrics儲存計算量度與在管理控制台中建立或更新計算量度相同。 套用至ReportSuite.DeleteCalculatedMetrics的相同。 此外，管理控制台中或呼叫ReportSuite.GetCalculatedMetrics時顯示的計算量度清單相同。

目前 ReportSuite CalculatedMetrics API 方法 (1.3 或 1.4 版) 仍可使用舊商店儲存、刪除和擷取計算量度。現有計算量度將移轉至新的計算量度產生器，並可在其中顯示。 **使用API方法建立的新計算量度只會顯示在API中。 它們仍可用於報告API。**

**您需要做什麼**

如果您需要同時使用API和計算量度產生器，應停止使用ReportSuite CalculatedMetrics API方法，而改用新的CalculatedMetrics API方法（Get、Save、Delete和GetFunctions）。

## 目前的資料支援所有計算量度類型嗎？{#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

目前的資料不支援包含區段或統計函式的計算量度。 唯一支援的函式是基本數學函式，例如加、刪除、乘、除和否定(-x)。

## 「未提供名稱」和移轉的計算量度一起出現代表什麼意思？{#section_C90CBB72A67644F38D583301981F8D03}

「未提供名稱」代表沒有量度名稱與此移轉的量度相關聯 (只有公式，沒有說明性名稱)。

## 刪除某個使用者後，該使用者的計算量度會發生什麼事？{#section_42ED4C15830540879C4A161423690E5A}

此使用者建立的任何計算量度也會隨之刪除。 不過，已刪除的計算量度仍可當成儲存書籤、控制面板或排程報表的一部分。

## 為什麼會看到對其他報表套裝無效的「未知」計算量度 (即使可對這些報表套裝建立和套用這些量度)？{#section_6772818EFDED46E9B7095D64C3B77211}

如果計算量度包含對所選報表套裝不存在的基本量度或維度，使用者介面就會將該量度顯示為「未知」。

## 為什麼我對舊式計算量度進行的變更無法儲存？{#section_81CDEFCA1FD542579AF183DA1494EAF0}

這可能是因為移轉至新計算量度資料庫的時間，此時間在2015年6月15日至6月18日之間。

**您需要做什麼**

您必須重做對舊式量度所做的變更。

## 為什麼我的計算量度沒有顯示在行銷管道報表中？{#section_FC350359A775433AB5F43C7CAB304D62}

（以前，所有計算量度都會列在「行銷管道」報表的量度選擇器中，並具有「首次接觸」和「上次接觸」選項。）

現在，只有在「計算量度」產生器中將配置類型特別設定為「首次接觸」或「上次接觸」的計算量度，才可在「行銷管道」報表的量度選擇器中使用。 請注意，任何已套用至行銷渠道報表的計算量度都將繼續套用，並且會如以前般運作。 若要建立行銷渠道的計算量度，請按一下量度產生器中的設定圖示，然後選取「首次接觸」或「上次接觸」作為配置類型。 請記住，這麼做會讓計算量度只與行銷管道報表相容，該量度將無法用於其他報表。

## 為什麼有些計算量度只顯示公式，卻沒有我加入的括號？ {#section_AC0D1E9714AD487F9A1C73359F518B5E}

在移轉期間，Adobe會從某些公式中移除多餘的括弧。 只會移除不影響量度計算方式的括弧。 這不會改變資料，只是簡化公式。

## (僅適用於 Ad Hoc Analysis) 仍支援包含嵌入或內嵌區段定義的計算量度嗎？{#section_B25C924A282F49388AB604E3D826F44C}

在臨機分析中建立的計算量度先前可能包含內嵌區段定義。 這已經不可能了。

**您需要做什麼**

您必須明確儲存區段。包含內嵌區段定義的現有計算量度仍可在 Ad Hoc Analysis 中正確執行並加以檢視，但若未明確儲存區段，將無法儲存該量度。

## (僅適用於 Report Builder) 為什麼計算量度沒有出現在我的請求中？{#section_DA4792FE5D7945218CD5E6328DE08E82}

如果要求是在 5.2 版中建立且包含計算量度，這些量度將無法顯示在 5.1 版 (或更早版本) 中。這是因為計算量度現在使用全域ID（非報表套裝專用ID）。

**您需要做什麼**

您必須升級至v5.2才能查看這些量度。

## 計算量度總計如何運作？{#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it&#39;s just applying the formula to the total. 例如，計算量度「訂購／瀏覽」的總計會取用「訂購總數」，並除以「瀏覽總數」。 不過，在某些情況下，計算量度總計不僅是行項目的總和，而是網站的總計。

範例 1：某個搜尋詞的訪客：同一位訪客可能搜尋了多個詞，所以在這種情況下，訪客總數並不等於行項目總和。

範例 2：產品的頁面檢視：在購物車中可能有多項產品，因此導致該購物車有多個頁面檢視。如需比較行項目總和與報表總計的詳細資訊，請參閱 [此知識庫文章](https://helpx.adobe.com/tw/analytics/kb/sum-line-items-different-from-total.html)。
