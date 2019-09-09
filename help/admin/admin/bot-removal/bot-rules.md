---
description: 機器人規則可讓您移除報表套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可以提供網站上更準確的使用者活動測量。
seo-description: 機器人規則可讓您移除報表套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可以提供網站上更準確的使用者活動測量。
seo-title: 機器人規則
solution: Analytics
subtopic: 機器人規則
title: 機器人規則概觀
topic: 管理工具
uuid: cb9e29d-1c37-43de-b7 ac-34441093a60 e
translation-type: tm+mt
source-git-commit: 5574b9e37e68971f7ecaa05056a30dab0b3d5d47

---


# 機器人規則概觀

機器人規則可讓您移除由已知編目程式和機器人產生的報表套裝流量。移除機器人流量可以提供網站上更準確的使用者活動測量。

定義機器人規則後，系統會將所有傳入流量與已定義規則做比較。符合任一規則的流量不會在報表套裝中加以收集，也不會納入流量量度。

To update or upload bot rules, navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Select the correct Report Suite, and then go to **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

移除機器人流量通常會減少流量和轉換量度的數量。許多客戶都發現，移除機器人流量可以增加轉換率、提高其他可用性量度。在移除機器人流量前，請先聯絡專案關係人，確定他們能因應此項變更，對關鍵績效指標進行必要調整。如果可行，建議先移除小型報表套裝中的機器人流量，評估可能造成的影響。

機器人流量資料儲存在單獨的儲存庫中，以便顯示在  機器人和機器人頁面報告中。啓用機器人篩選有兩個選項：

| 規則類型 | 說明 |
|--- |--- |
| 標準IAB機器人規則 | 選取 [!UICONTROL 「啓用IAB機器人篩選規則] 」會使用 [IAB(](https://www.iab.com) 國際廣告局的)國際編目程式與機器人清單來移除機器人流量。大多數客戶至少選擇此選項。 |
| 自訂機器人規則 | 您可以根據使用者代理、IP位址或IP範圍，定義並新增自訂機器人規則。 |

## 標準IAB機器人規則

您可以勾選 [!UICONTROL 「啓用IAB機器人篩選規則] 」核取方塊，開啓標準IAB機器人規則。此選項會移除IAB(國際廣告局的)國際編目程式與機器人清單中的機器人，以移除機器人流量。IAB會每月更新此清單。

![](assets/bot-iab-checkbox.png)

Adobe 無法提供詳細的 IAB 機器人清單給客戶，但您可使用「機器人報告」來檢視曾存取您網站之機器人的清單。若要提交機器人至IAB清單，請造訪 [IAB](https://www.iab.com)。

## 自訂機器人規則

>[!Nte te]
>可在使用者介面手動定義 500 個規則。達到上限之後，需透過以下內容來大量管理規則「匯入檔案」與「匯出機器人規則」選項。

自訂機器人規則可讓您根據自行定義的條件，來篩選流量。

自訂機器人規則是使用下列條件類型來定義。

* 使用者代理
* IP 位址
* IP 範圍

單一規則可以定義多個條件。請使用「或」("or") 來比對多個條件。例如，如果您提供「使用者代理」和「IP 位址」的值，當任一條件符合時就會將流量視為機器人流量。

### 使用者代理

使用者代理條件會檢查使用者代理值，查看其是否&#x200B;**[!UICONTROL 開頭為]**&#x200B;或&#x200B;**包含]指定之字串。[!UICONTROL **&#x200B;如果選取了&#x200B;**[!UICONTROL 包含]，則子字串出現在使用者代理中任何位置都算符合。**

可以在&#x200B;**[!UICONTROL 不包含]清單中加入選用值，定義使用者代理不應包含該值，才能算是成功符合。**&#x200B;可以加入多個值，一行指定一個值。如果使用者代理滿足符合字串中指定的標準，但也含有不包含清單中的字串，則不視為符合。

「**[!UICONTROL 包含]」欄位限制在 100 個字元。**&#x200B;不包含清單上限為 255 個字元，扣除每一新行的分隔符號字元。(這等於字串數目 - 1。如果您指定 4 個&#x200B;*不包含*&#x200B;字串，則需要 3 個分隔符號字元)。所有字串比對不分大小寫。

### IP 位址 (包括萬用字元符合)

比對 IP 位址或使用萬用字元 (*) 比對同一區塊中的多個位址。提供您要比對之 IP 位址的數值。使用 * 替換您要以萬用字元來比對的值。下表包含 IP 位址符合字串的範例:

```
10.10.10.1
10.10.10.*
```

### IP 位址範圍

提供要比對之 IP 位址的開始和結束範圍。使用 * 替換您要以萬用字元來比對的值。

### 定義自訂機器人規則

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。30 分鐘內變更就會生效。

## 上傳 Bot 規則

若要大量上傳機器人規則，您可上傳用於定義規則的 CSV 檔。

以下列順序建立CSV檔案：

| 欄目 1 | 欄目 2 | 欄目 3 | 欄目 4 | 欄目 5 |
|--- |--- |---|---|---|
| 機器人名稱 | IP 開頭 | IP 結尾 | Agent Match Rule<br>(contains or starts with)</br> | 代理排除(<br>255個字元限制)</br> |

您可以定義 3 種機器人規則:

* 使用者代理包含或開頭為
* 單一 IP 位址或萬用字元符合
* IP 範圍符合

匯入檔案中每一列都只能包含下列其中一種機器人定義:

* **使用者代理包含或開頭為**: 提供單一使用者代理字串，與「代理包含」欄比對。在「代理符合規則」欄位中加入&#x200B;*「包含」*&#x200B;或&#x200B;*「開頭為」*，指定符合類型。An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. 字串比對不分大小寫。「IP 開頭」和「IP 結尾」欄都必須為空。

* **單一IP位址或萬用字元符合**：若要比對單一IP位址( `10.10.10.1`)或萬用字元IP位址( `10.10.*.*`)，請在「IP開頭」和「IP結尾」欄中放置相同的值。「符合規則」、「代理包含」和「代理排除」必須為空。

* **IP 範圍符合**: 使用「IP 開頭」和「IP 結尾」欄，定義 IP 位址的範圍。Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. 「符合規則」、「代理包含」和「代理排除」必須為空。

### 多個規則結合 OR

若要結合 OR 和一組規則來比對機器人 (例如，使用者代理或 IP 位址)，請在機器人名稱欄位中提供您要組合使用之所有規則的完整名稱。不支援 AND 比對。

### 以上傳檔案覆寫所有規則

選取&#x200B;**[!UICONTROL 「覆寫現有規則」]核取方塊，刪除所有現有規則並以上傳檔案中定義的規則加以取代。**

### 匯出規則

**[!UICONTROL 「匯出已上載機器人檔案」]按鈕可將 UI 中定義的所有規則匯出維 CSV 格式。**


## Impact of bot rules on data collection {#section_F01A3130E7A04A9993371CF26F6586F2}

「機器人規則」會套用至所有分析資料。「機器人規則」移除的資料只會顯示在「機器人」和「機器人頁面」報告中。

VISTA rules are applied after Bot Rules (see [Processing Order](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**高點擊瀏覽處理:** 如果一次瀏覽中超過 100 次點擊，報告會判斷瀏覽的秒數是否小於或等於瀏覽的點擊數。在這種情況下，由於處理長時間密集瀏覽的成本，報告會以新瀏覽重新開始。高點擊瀏覽次數通常是因為機器人攻擊造成的，不會視為正常的訪客瀏覽。

>[!NOTE]
>
>標示為 *`bots`*[伺服器呼叫](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html)的點擊會被計算。

## Impact of IP Obfuscation on bot filtering {#section_92E60B95BE8940D983F28C79E0CD6B12}

系統是完全根據使用者代理來建立 IAB 機器人清單，因此根據該清單進行篩選並不會受到 IP 模糊化設定影響。如果是進行非 IAB 的機器人篩選 (自訂規則)，篩選條件可能會包含 IP。如果使用 IP 來篩選機器人，機器人篩選會在最後一個八位元組移除之後 (如果該設定已啟用)，或是其他 IP 模糊化選項之前 (如刪除整個 IP，或使用部分唯一 ID 取代 IP) 進行。

若啟用 IP 模糊化，會在 IP 位址被模糊化前即排除 IP，因此當客戶啟用 IP 模糊化時不必變更任何東西。

如果最後的八位數字己移除，則會在 IP 篩選前進行這項作業。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 * 應符合 0。
