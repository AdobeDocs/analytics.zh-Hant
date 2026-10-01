---
description: Custom Insight轉換變數（或eVar）會放置在網站所選網頁的Adobe程式碼中。 其主要作用是將自訂行銷報告中的轉換成功量度區段。 eVar能以造訪為基礎，其功能與Cookie類似。 傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。
keywords: eVar
title: 轉換變數 (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1726'
ht-degree: 25%
---
# 轉換變數 (eVar)

Custom Insight轉換變數（或eVar）會放置在網站所選網頁的Adobe程式碼中。 其主要作用是將自訂行銷報告中的轉換成功量度區段。 eVar能以造訪為基礎，其功能與Cookie類似。 傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 轉換變數]**

## 轉換變數 (eVar) 概觀

如需轉換變數的影片概觀，請參閱Analytics教學課程指南中的[轉換變數簡介](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars)。

當eVar設為訪客的值時，Adobe會自動記住該值，直到它過期為止。 eVar值作用中時，訪客遇到的任何成功事件都會計入eVar值。

eVar 最適合用來測量原因和結果，如：

* 哪些內部行銷活動影響了收入
* 最終導致註冊的橫幅廣告
* 訂單前使用內部搜尋的次數

如果需要流量測量或路徑分析，建議使用流量變數。

>[!NOTE]
>
>影像要求的 eVar 中僅可儲存單一數值。 如果eVar值中需要多個數值，請使用[清單變數](/help/implement/vars/page-vars/page-variables.md)。

### 轉換變數 - 說明 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| 元素 | 說明 |
| --- | --- |
| [!UICONTROL 狀態] | 決定eVar是否作用中：<ul><li>**[!UICONTROL 已啟用]**： eVar作用中。</li><li>**[!UICONTROL 已停用]**：停用eVar並將其從轉換變數清單中移除。</li></ul> |
| [!UICONTROL 說明] | eVar的選擇性說明。 用它來記錄eVar擷取的內容及其實施方式。 |
| [!UICONTROL 名稱] | 轉換變數的易記維度名稱。 這是一般報表中參照eVar的方式。 |
| [!UICONTROL 配置] | 如果變數在事件之前接收到多個值，可決定 Analytics 如何為成功事件指派貢獻度。 支援的值包括：<ul><li>**[!UICONTROL 最近（上一個）]**：在該eVar過期以前，最後一個eVar值一律會收到成功事件的評分。</li><li>**[!UICONTROL 原始值（第一個）]**：在該eVar過期以前，第一個eVar一律會收到成功事件的評分。</li><li>**[!UICONTROL 線性]**：所有 eVar 值會收到均分的成功事件評分。 由於線性配置只會在一次造訪中分發值，因此請搭配造訪或更短期間的eVar過期時間使用線性配置。 此選項不適用於銷售eVar。</li></ul>**重要**： Adobe建議您不要切換至[!UICONTROL 線性]配置，或從中切換配置，因為它會隱藏報表中的歷史資料，直到您切換回為止。 若要變更具有重要歷史的eVar上的配置，Adobe建議改用新的eVar。 |
| [!UICONTROL 有效期限] | 指定eVar值何時到期（不再接收成功事件的評分）。 如果成功事件發生在 eVar 過期後，「無」值會獲得該事件的貢獻度 (沒有作用中的 eVar 值)。 支援的值包括：<ul><li>**[!UICONTROL 造訪]**：值會在造訪結束時過期。</li><li>**[!UICONTROL 點選]**：值僅適用於設定它的點選。</li><li>**[!UICONTROL 分鐘]**、**[!UICONTROL 小時]**、**[!UICONTROL 天]**、**[!UICONTROL 周]**、**[!UICONTROL 月]**、**[!UICONTROL 季]**&#x200B;或&#x200B;**[!UICONTROL 年]**：值會在設定後的固定時間內到期，到期時間為秒：<ul><li>分鐘= 60秒</li><li>小時= 3600秒（60分鐘）</li><li>日= 86400秒（24小時）</li><li>周= 604800秒（7天）</li><li>月份= 2678400秒（31天）</li><li>季度= 8035200秒（93天 — 31天中的3個月）</li><li>年= 31536000秒（365天）</li></ul>例如，如果eVar設定在星期一早上7:15，[!UICONTROL 第]天到期日會在星期二早上7:15結束，[!UICONTROL 第]周到期日會在下星期一早上7:15結束，而[!UICONTROL 第]個月到期日會在31天後早上7:15結束。</li><li>**[!UICONTROL 自訂]**：值會在您輸入的天數（每天86400秒）後到期。</li><li>**事件** （[!UICONTROL 購買]、[!UICONTROL 產品檢視]、[!UICONTROL 購物車開啟]、[!UICONTROL 購物車結帳]、[!UICONTROL 購物車新增]、[!UICONTROL 購物車移除]、[!UICONTROL 購物車檢視]或自訂事件）：值會在選取的事件發生時過期。 如果事件從未發生，則值永不過期。</li><li>**[!UICONTROL 從不]**：只要訪客使用相同的識別碼，eVar和事件之間便可以經過任意長的時間。</li></ul> |
| [!UICONTROL Type] | 變數值的類型：<ul><li>**[!UICONTROL 文字字串]**：擷取文字值。 這是最常見的eVar型別，也是預設設定。 它的作用與其他變數類似，其中包含的值是靜態文字字串。 如果您追蹤內部行銷活動或內部搜尋關鍵字等，建議使用此設定。</li><li>**[!UICONTROL 計數器]**：計算成功事件前某個動作發生的次數。 例如，您可以在成功事件之前計算已執行搜尋的次數，無論使用的搜尋字詞為何。</li></ul> |
| [!UICONTROL 重設] | 儲存後，會立即將所有訪客中此變數的所有伺服器端儲存值過期，包括銷售產品繫結。 重新利用eVar時使用[!UICONTROL 重設]，以免將舊值混合到新報表中。 **重設不會清除歷史資料。** |
| [!UICONTROL 啟用銷售] | 支援的值包括：<ul><li>**[!UICONTROL 已停用]**： eVar會將成功事件歸功於訪客持續存在的值。</li><li>**[!UICONTROL 已啟用]**： eVar會變成銷售eVar，將值與個別產品繫結。 每個產品的成功事件都會計入與該產品繫結的值。 啟用銷售會顯示[!UICONTROL 銷售]和[!UICONTROL 銷售繫結事件]設定，並移除[!UICONTROL 線性]配置。</li></ul>僅針對說明如何找到或購買產品的eVar啟用銷售。 銷售eVar不再將成果歸功於未繫結至產品的成功事件。 請參閱[eVar （銷售）](/help/components/dimensions/evar-merchandising.md)。 |
| [!UICONTROL 銷售] | 決定繫結至產品的值來自何處：<ul><li>**[!UICONTROL 產品語法]**：值設定在`products`變數中的每個產品上，並繫結至該點選上的該產品。 每個產品可以有不同的值。 未使用繫結事件，因此[!UICONTROL 銷售繫結事件]已停用。</li><li>**[!UICONTROL 轉換變數語法]**：此值是在eVar中設定，並持續做為階段值，無論是否配置[!UICONTROL 配置]，一律會反映最近傳送的值。 只有在點選包含選取的[!UICONTROL 銷售捆綁事件]時，該值才會與點選上的產品繫結。 該點選上的每個產品都會收到相同的值。</li></ul>若變更此設定但沒有相應地更新實施，會導致資料遺失。 如需實作詳細資料，請參閱[eVar （銷售變數）](/help/implement/vars/page-vars/evar-merchandising.md)。 |
| [!UICONTROL 銷售繫結事件] | 僅當[!UICONTROL 銷售]設定為[!UICONTROL 轉換變數語法]時可用。 決定哪些事件或eVar會將eVar的階段值繫結至相同點選上的產品。 如果您未選取繫結事件，則會使用[!UICONTROL 全部]。 支援的值包括：<ul><li>**[!UICONTROL 全部]**：點選觸發程式繫結上的任何其他事件或eVar。 此設定是預設值。</li><li>**[!UICONTROL 購買事件]**、**[!UICONTROL 產品檢視事件]**、**[!UICONTROL 購物車開啟事件]**、**[!UICONTROL 購物車結帳事件]**、**[!UICONTROL 購物車新增事件]**、**[!UICONTROL 購物車移除事件]**&#x200B;或&#x200B;**[!UICONTROL 購物車檢視事件]**：包含所選事件的點選發生繫結。</li><li>**[!UICONTROL 促銷活動事件]**：包含[追蹤代碼](/help/components/dimensions/tracking-code.md)維度（[`campaign`](/help/implement/vars/page-vars/campaign.md)變數）的執行個體的點選發生繫結。</li><li>**自訂事件**：包含所選自訂事件的點選發生繫結。</li><li>**自訂eVar**：設定所選eVar的點選發生繫結。</li></ul>Prop無法觸發繫結。 按住ctrl鍵(Windows)或cmd鍵(Mac)並按一下清單中的多個專案，以選取多個值。 當已與eVar繫結的特定產品收到與同一eVar的另一個繫結時，[!UICONTROL 配置]會決定要保留哪個值。 |

### 有效期限

`eVars` 會在經過您所指定的時段之後過期。 eVar過期後，將不再接收成功事件的評價。 eVar也可設定為在成功事件時到期。 例如，如果您的內部促銷在造訪結束時到期，則內部促銷只會收到在其啟動造訪期間發生的購買或註冊的評分。

有兩種方式可讓 eVar 過期：

* 您可以設定eVar在指定的時段或事件後到期。
* 您可以透過重設來強制eVar過期，在重新利用變數時非常有用。

例如，如果您將 eVar 的過期時間從 30天變更為 90 天，所收集的 eVar 值會在新設定的過期時間內持續存在 (此案例中為 90 天)。 系統僅會查看目前的過期設定，以及所收集 eVar 值最後設定的時間戳記，以此判斷過期時間。 僅有&#x200B;**[!UICONTROL 重設]**&#x200B;選項能使值過期，而且立即生效。

其他範例：假設在五月使用某個 eVar 反映內部促銷情形，且該值在 21 天後過期。若要在六月使用該 eVar 擷取內部搜尋關鍵字，您應在 6 月 1 日將此變數強制過期或加以重設。 這麼做有助於將內部促銷活動值排除在六月的報表以外。

### 區分大小寫

eVar 不區分大小寫。 報告中使用的大寫或小寫是根據後端系統註冊的第一個值。 此值可能是第一次出現，也可能在某個時段 (例如，每月) 發生變化，具體取決於與報表套裝相關聯的資料種類和數量。

### 計數器

雖然eVar最常用於儲存字串值，但也可將其設定為作為計數器。 當您嘗試在事件之前計算使用者採取的動作次數時，eVar很適合當作計數器。 例如，您可能會使用eVar在購買前擷取內部搜尋次數。 每當訪客進行搜尋時，eVar都應該包含&#39;+1&#39;值。 如果訪客在購買之前做了四次搜尋，您將會看見各個總計數的例項：1.00、2.00、3.00和4.00。 但只有4.00會獲得購買事件的評分（訂購和收入量度）。 僅允許正數作為eVar計數器的值。

## 新增或編輯轉換變數

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報告套裝]**。
1. 選取報表套裝。
1. 按一下&#x200B;**[!UICONTROL 「編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 轉換變數」]**。
1. 在[!UICONTROL 轉換變數]頁面，在您要修改的轉換變數旁按一下&#x200B;**[!UICONTROL 展開]**&#x200B;圖示[「+」]。

   或

   按一下&#x200B;**[!UICONTROL 「新增」]**，以新增未使用的 eVar 至報告套裝。
1. 選擇您要修改的轉換變數欄位。

   請參閱[轉換變數 — 說明](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF)。 有些欄位可讓您直接在欄位中輸入。 其他選項可讓您從支援值的下拉式清單中選取。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
