---
description: 機器人規則可讓您移除報告套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可針對使用者在您網站上的活動提供更準確的測量。
title: 機器人規則概觀
feature: Bot Removal
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '1369'
ht-degree: 96%

---

# 機器人規則概觀

機器人規則可讓您移除報告套裝中，由已知編目程式和機器人產生的流量。移除機器人流量可針對使用者在您網站上的活動提供更準確的測量。

以下是有關設定機器人規則的影片：

>[!VIDEO](https://video.tv.adobe.com/v/335738/?quality=12)

定義機器人規則後，所有連入流量都將與定義的規則做比較。 符合任一規則的流量不會在報告套裝中加以收集，也不會納入流量量度。

若要更新或上傳機器人規則，請導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報告套裝」]**。選取正確的報告套裝，然後前往「**[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 機器人規則]**」。

移除機器人流量通常會減少流量和轉換量度的數量。許多客戶都發現，移除機器人流量可以增加轉換率、提高其他可用性量度。在移除機器人流量前，請先聯絡專案關係人，確定他們能因應此項變更，對關鍵績效指標進行必要調整。如果可行，建議先移除小型報告套裝中的機器人流量，評估可能造成的影響。

機器人流量資料儲存在單獨的儲存庫中，以便顯示在機器人和機器人頁面報表中。啟用機器人篩選的選項有兩種：

| 規則類型 | 說明 |
|--- |--- |
| 標準 IAB 機器人規則 | 選取[!UICONTROL 「啟用 IAB 機器人篩選規則」]，系統會使用 [IAB](https://www.iab.com) (國際廣告局) 的「國際編目程式與機器人清單」來移除機器人流量。多數客戶至少都會選取此選項。 |
| 自訂機器人規則 | 您可以根據使用者代理、IP 位址或 IP 範圍來定義與新增自訂機器人規則。 |

## 標準 IAB 機器人規則

勾選[!UICONTROL 「啟用 IAB 機器人篩選規則」]核取方塊，即可開啟標準 IAB 機器人規則 。這個選項會移除 IAB (國際廣告局) 國際編目程式與機器人清單中的機器人，藉此移除機器人流量。Adobe 每月會利用 IAB 更新此清單。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-iab-checkbox.png)

Adobe 無法提供詳細的 IAB 機器人清單給客戶，但您可使用「機器人報表」來檢視曾存取您網站之機器人的清單。若要提交機器人給 IAB 清單，請造訪 [IAB](https://www.iab.com)。

## 自訂機器人規則

>[!NOTE]
>
>使用者介面可允許手動定義 500 個規則。達到上限之後，必須透過「匯入檔案」和「匯出機器人規則」選項來大量管理規則。

自訂機器人規則可讓您根據自行定義的條件，來篩選流量。

自訂機器人規則是使用下列條件類型來定義。

* 使用者代理
* IP 位址
* IP 範圍

單一規則可以定義多個條件。請使用「或」(&quot;or&quot;) 來比對多個條件。例如，如果您提供「使用者代理」和「IP 位址」的值，當任一條件符合時就會將流量視為機器人流量。

### 使用者代理

使用者代理條件會檢查使用者代理值，查看其是否&#x200B;**[!UICONTROL 開頭為]**&#x200B;或&#x200B;**[!UICONTROL 包含]**&#x200B;指定之字串。如果選取了&#x200B;**[!UICONTROL 包含]**，則子字串出現在使用者代理中任何位置都算符合。

可以在&#x200B;**[!UICONTROL 不包含]**&#x200B;清單中加入選用值，定義使用者代理不應包含該值，才能算是成功符合。可以加入多個值，一行指定一個值。如果使用者代理滿足符合字串中指定的標準，但也含有不包含清單中的字串，則不視為符合。

**[!UICONTROL 「包含」]**&#x200B;欄位限制在 100 個字元。不包含清單上限為 255 個字元，扣除每一新行的分隔符號字元。(這等於字串數目 - 1。如果您指定 4 個&#x200B;*不包含*&#x200B;字串，則需要 3 個分隔符號字元)。所有字串比對不分大小寫。

### IP 位址 (包括萬用字元符合)

使用萬用字元(&#42;)。 提供您要比對之 IP 位址的數值。替代 &#42; ，以符合您要使用萬用字元來比對的任何值。 下表包含 IP 位址符合字串的範例：

```
10.10.10.1
10.10.10.*
```

### IP 位址範圍

提供要比對之 IP 位址的開始和結束範圍。替代 &#42; ，以符合您要使用萬用字元來比對的任何值。

### 定義自訂機器人規則

1. 前往&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員」]**，選取一或多個報告套裝並按一下&#x200B;**[!UICONTROL 「一般]** > **[!UICONTROL 機器人規則」]**。
1. 按一下&#x200B;**[!UICONTROL 「新增規則」]**，定義一或多個符合條件。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。30 分鐘內變更就會生效。

## 上傳機器人規則

若要大量上傳機器人規則，您可上傳用於定義規則的 CSV 檔。

建立 CSV 檔案，依下列順序加入以下各欄：

| 欄目 1 | 欄目 2 | 欄目 3 | 欄目 4 | 欄目 5 |
|--- |--- |---|---|---|
| 機器人名稱 | IP 開頭 | IP 結尾 | 代理符合規則 <br>(包含或開頭為)</br> | 代理排除 <br>(255 字元上限)</br> |

您可以定義 3 種機器人規則：

* 使用者代理包含或開頭為
* 單一 IP 位址或萬用字元符合
* IP 範圍符合

匯入檔案中每一列都只能包含下列其中一種機器人定義：

* **使用者代理包含或開頭為**：提供單一使用者代理字串，與「代理包含」欄比對。在「代理符合規則」欄位中加入&#x200B;*「包含」*&#x200B;或&#x200B;*「開頭為」*，指定符合類型。可以在「代理排除」欄中加上選用值，定義代理不可包含的一或多個垂直號分隔 (`|`) 字串。字串比對不分大小寫。「IP 開頭」和「IP 結尾」欄都必須為空。

* **單一 IP 位址或萬用字元符合**：若要比對單一 IP 位址 (`10.10.10.1`) 或萬用字元 IP 位址 (`10.10.*.*`)，請在「IP 開頭」和「IP 結尾」欄中放置相同的值。「符合規則」、「代理包含」和「代理排除」必須為空。

* **IP 範圍符合**：使用「IP 開頭」和「IP 結尾」欄，定義 IP 位址的範圍。您可以使用萬用字元來比對 IP 範圍，例如 `10.10.10.*` 到 `10.10.20.*`。「符合規則」、「代理包含」和「代理排除」必須為空。

### 多個規則結合 OR

若要結合 OR 和一組規則來比對機器人 (例如，使用者代理或 IP 位址)，請在機器人名稱欄位中提供您要組合使用之所有規則的完整名稱。不支援 AND 比對。

### 以上傳檔案覆寫所有規則

選取&#x200B;**[!UICONTROL 「覆寫現有規則」]**&#x200B;核取方塊，刪除所有現有規則並以上傳檔案中定義的規則加以取代。

### 匯出規則

**[!UICONTROL 「匯出已上載機器人檔案」]**&#x200B;按鈕可將 UI 中定義的所有規則匯出維 CSV 格式。

## 機器人規則對資料收集的影響 {#section_F01A3130E7A04A9993371CF26F6586F2}

「機器人規則」會套用至所有分析資料。「機器人規則」移除的資料只會顯示在「機器人」和「機器人頁面」報表中。

VISTA規則是在機器人規則之後套用。 請參閱 [處理順序](/help/technotes/processing-order.md) （在Technotes使用手冊中）。

**高點擊瀏覽處理：**&#x200B;如果一次瀏覽中超過 100 次點擊，報告會判斷瀏覽的秒數是否小於或等於瀏覽的點擊數。在這種情況下，由於處理長時間密集瀏覽的成本，報告會以新瀏覽重新開始。高點擊瀏覽次數通常是因為機器人攻擊造成的，不會視為正常的訪客瀏覽。

>[!NOTE]
>
>標示為 *`bots`* 的點擊會在帳單中計為[伺服器呼叫](/help/admin/admin/c-server-call-usage/overage-overview.md)。

## IP 模糊化對機器人篩選的影響 {#section_92E60B95BE8940D983F28C79E0CD6B12}

系統是完全根據使用者代理來建立 IAB 機器人清單，因此根據該清單進行篩選並不會受到 IP 模糊化設定影響。如果是進行非 IAB 的機器人篩選 (自訂規則)，篩選條件可能會包含 IP。如果使用 IP 來篩選機器人，機器人篩選會在最後一個八位元組移除之後 (如果該設定已啟用)，或是其他 IP 模糊化選項之前 (如刪除整個 IP，或使用部分唯一 ID 取代 IP) 進行。

若啟用 IP 模糊化，會在 IP 位址被模糊化前即排除 IP，因此當客戶啟用 IP 模糊化時不必變更任何東西。

如果最後的八位數字己移除，則會在 IP 篩選前進行這項作業。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。相符 &#42; 應符合0。