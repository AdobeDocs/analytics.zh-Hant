---
description: 機器人規則可讓您移除報表套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可以提供網站上更準確的使用者活動測量。
seo-description: 機器人規則可讓您移除報表套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可以提供網站上更準確的使用者活動測量。
seo-title: 機器人規則
solution: Analytics
subtopic: 機器人規則
title: 機器人規則
topic: 管理工具
uuid: cb9e29d-1c37-43de-b7 ac-34441093a60 e
translation-type: tm+mt
source-git-commit: 92ac6c03013bd68326e4136a5d512171fc831689

---


# 機器人規則

機器人規則可讓您移除由已知編目程式和機器人產生的報表套裝流量。移除機器人流量可以提供網站上更準確的使用者活動測量。

定義機器人規則後，系統會將所有傳入流量與已定義規則做比較。符合任一規則的流量不會在報表套裝中加以收集，也不會納入流量量度。

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

移除機器人流量通常會減少流量和轉換量度的數量。許多客戶都發現，移除機器人流量可以增加轉換率、提高其他可用性量度。在移除機器人流量前，請先聯絡專案關係人，確定他們能因應此項變更，對關鍵績效指標進行必要調整。如果可行，建議先移除小型報表套裝中的機器人流量，評估可能造成的影響。

>[!NOTE]建議您為每個報表套裝定義 500 個以內的機器人規則。可在使用者介面手動定義 500 個規則。達到上限之後，需透過以下內容來大量管理規則[「匯入檔案」](../../../admin/admin/bot-rules/t-upload-bot-rules.md#task_95868D8564564E6A996163335C119806)與「匯出機器人規則」選項。

機器人流量資料儲存在單獨的儲存庫中，以便顯示在 [!UICONTROL  機器人]和[!UICONTROL 機器人頁面]報告中。

| 規則類型 | 說明 |
|--- |--- |
| IAB | Selecting [!UICONTROL Include IAB] uses the IAB's (International Advertising Bureau's) International Spiders &amp; Bots List to remove bot traffic. IAB 每月更新此清單。<br>若要提交機器人至IAB清單，請造訪 [IAB](https://www.iab.net/sites/spiders/form.php)。<br>Adobe 無法提供詳細的 IAB 機器人清單給客戶，但您可使用「機器人報告」來檢視曾存取您網站之機器人的清單。 |
| 自訂機器人規則 | 請參閱 [建立自訂機器人規則](../../../admin/admin/bot-rules/t-create-bot-rules.md). |

## 機器人規則對資料收集的影響 {#section_F01A3130E7A04A9993371CF26F6586F2}

「機器人規則」會套用至所有分析資料。「機器人規則」移除的資料只會顯示在「機器人」和「機器人頁面」報告中。

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**高點擊瀏覽處理:** 如果一次瀏覽中超過 100 次點擊，報告會判斷瀏覽的秒數是否小於或等於瀏覽的點擊數。在這種情況下，由於處理長時間密集瀏覽的成本，報告會以新瀏覽重新開始。高點擊瀏覽次數通常是因為機器人攻擊造成的，不會視為正常的訪客瀏覽。

>[!NOTE]
>
>標示為 *`bots`*[伺服器呼叫](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html)的點擊會被計算。

## IP 模糊化對機器人篩選的影響 {#section_92E60B95BE8940D983F28C79E0CD6B12}

系統是完全根據使用者代理來建立 IAB 機器人清單，因此根據該清單進行篩選並不會受到 IP 模糊化設定影響。如果是進行非 IAB 的機器人篩選 (自訂規則)，篩選條件可能會包含 IP。如果使用 IP 來篩選機器人，機器人篩選會在最後一個八位元組移除之後 (如果該設定已啟用)，或是其他 IP 模糊化選項之前 (如刪除整個 IP，或使用部分唯一 ID 取代 IP) 進行。

若啟用 IP 模糊化，會在 IP 位址被模糊化前即排除 IP，因此當客戶啟用 IP 模糊化時不必變更任何東西。

如果最後的八位數字己移除，則會在 IP 篩選前進行這項作業。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 * 應符合 0。
