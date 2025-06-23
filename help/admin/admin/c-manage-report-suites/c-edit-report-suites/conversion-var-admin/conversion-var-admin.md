---
description: 自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。eVar 可以瀏覽為準，其功能類似於 Cookie。傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。
keywords: eVar
title: 轉換變數 (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: 2cc610205fe3181f55106025e7d7169281fead08
workflow-type: tm+mt
source-wordcount: '1716'
ht-degree: 97%

---

# 轉換變數 (eVar)

自訂分析轉換變數 (或 eVar) 放置於您的網站上所選網頁的 Adobe 程式碼中。其主要作用是將自訂行銷報告中的轉換成功量度區段。eVar 可以瀏覽為準，其功能類似於 Cookie。傳送到 eVar 變數的值，會在預定的期間內跟隨使用者。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 轉換變數]**

## 轉換變數 (eVar) 概觀

如需轉換變數的影片概觀，請參閱Analytics教學課程指南中的[轉換變數簡介](https://experienceleague.adobe.com/zh-hant/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars)。

當 eVar 被設定為某個訪客的值，Adobe 會自動記住該值，直到其過期。訪客在 eVar 值活動期間遇到的任何成功事件都會被計入 eVar 值。

eVar 最適合用來測量原因和結果，如：

* 哪些內部促銷活動影響收入
* 哪些橫幅廣告最終產生註冊
* 下訂單前使用的內部搜尋次數

如果需要流量測量或路徑功能，建議使用流量變數。

>[!NOTE]
>
>影像要求的 eVar 中僅可儲存單一數值。如果 eVar 值中需要多個數值，建議您實施[清單變數 (list vars)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=zh-Hant)。

### 轉換變數 - 說明 {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

[編輯轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)時所用欄位相關說明。

| 元素 | 說明 |
| --- | --- |
| [!UICONTROL 名稱] | 轉換變數的易記名稱。 這個名稱是一般報表中用來參考 eVar 的方式，也會是左側功能表中的報表/維度名稱。 |
| [!UICONTROL 類型] (僅限 eVar) | 變數值的類型：<ul><li>**[!UICONTROL 文字字串]**：擷取您網站上所使用的文字值。 這是最常用的 eVar 類型，也是預設設定。其運作方式與其他變數類似，包含的值是靜態文字字串。如果您要追蹤內部促銷活動或內部搜尋關鍵字等項目，建議使用此設定。</li><li>**[!UICONTROL 計數器]**：計算成功事件前某個動作發生的次數。 例如，如果您使用 eVar 追蹤網站上的內部搜尋，設定此值為「[!UICONTROL 文字字串]」可追蹤搜尋字詞的使用情況。 將此值設定為「[!UICONTROL 計數器]」可計算已執行搜尋的次數，不考慮所使用的搜尋字詞。 例如，您可使用計數器 eVar 來追蹤某個人在進行購買前，使用內部搜尋的次數。</li></ul> |
| [!UICONTROL 配置] | 如果變數在事件之前接收到多個值，可決定 Analytics 如何為成功事件指派評分。支援的值包括：<ul><li>**[!UICONTROL 最近]**：在該 eVar 過期以前，最近一個 eVar 值一律會收到成功事件的評分。</li><li>**[!UICONTROL 原始值]**：在該 eVar 過期以前，第一個 eVar 值一律會收到成功事件的評分。</li><li>**[!UICONTROL 線性]**：所有 eVar 值會收到均分的成功事件評分。 由於線性配置只會在一次造訪中正確地分發值，所以請搭配造訪的 eVar 過期時間使用線性配置。</li></ul> **注意**：切換配置至「線性」或是從「線性」切換配置時，不會顯示歷史資料。 在報告介面混合配置類型可能造成報告中資料誤報。例如，「線性」配置將收入分配給數個不同的 eVar 值。變更回「最近」配置後，該收入的 100% 都關聯至最近的單一值。這種關聯會讓使用者產生不正確的結論。<br><br>為了避免報告產生混淆，Adobe Analytics 會在介面中隱藏歷史資料。 如果您決定將特定 eVar 變更回初始配置設定，仍可檢視這些歷史資料，但您不應僅為了存取歷史資料而變更 eVar 配置設定。如果想對已記錄的資料採用新的配置設定，Adobe 建議使用新的 eVar，而不是變更已建立了大量歷史資料的 eVar 之配置設定。 |
| [!UICONTROL 有效期限] | 指定時段或事件，在此時段或事件後 eVar 值就過期 (不再接收成功事件的評分)。如果成功事件發生在 eVar 過期後，「無」值會接收事件的評分 (沒有作用中的 eVar 值)。 如果您選取事件當做期限值，則變數在事件發生時才會過期。 如果事件未發生，變數永遠不會到期。 可用的過期選項分為 4 種主要類別：<ul><li>**在頁面瀏覽或造訪層級。**&#x200B;在頁面瀏覽或造訪以外轉換事件並不會關聯至 eVar。</li><li>**根據時段，如日、週、月或年。**&#x200B;在指定的時段以外轉換事件並不會關聯至 eVar。過期期間從設定變數時開始。eVar 的過期期限依其設定時間為準，計算至秒 (分鐘、小時、天、月等)： <ul><li>MINUTE=60 秒</li><li>HOUR=3600 秒 (60 分鐘)</li><li>DAY=86400 秒 (24 小時)</li><li>WEEK=604800 秒 (7 天)</li><li>MONTH=2678400 秒 (31 天)</li><li>QUARTER=8035200 秒 (93 天 - 3 個 31 天的月份)</li><li>YEAR=31536000 秒 (365 天)</li><br>如果某個造訪從星期一早上 7:00 開始，且在早上 7:15 於該造訪中設定 eVar，則其期限如下所示：<li>當天過期：eVar 將於星期二早上 7:15 過期。</li><li>當週過期：eVar 將於下星期一早上 7:15 過期。</li><li>當月過期：eVar 將於星期一後第 31 天早上 7:15 過期。</li></ul><li>**特定的轉換事件。**&#x200B;在指定的特定事件之後引發的任何其他轉換事件，都會關聯至 eVar。</li><li>**從不。**&#x200B;只要 visitorID Cookie 是完整的，在 eVar 和事件之間可間隔任何時間量。</li></ul> |
| [!UICONTROL 狀態] (僅限 eVar) | 定義 [!UICONTROL eVar] 狀態：<ul><li>**停用**：停用 [!UICONTROL eVar]。 從轉換變數清單中移除 [!UICONTROL eVar]。</li><li>**無子關聯**：防止您根據維度劃分 [!UICONTROL eVar]。</li><li>**基本子關聯**：可讓您依據任何完整維度 (例如「產品」或「促銷活動」) 劃分 eVar。</li></ul> |
| [!UICONTROL 重設] | 重設 eVar 中的任何現有值。 重新利用eVar時，請使用此設定，以免將舊值混合至新報表中。 重設並不會清除歷史資料。 |
| [!UICONTROL 銷售] (僅限 eVar) | 銷售變數可遵循下列其中一種語法：<ul><li>**[!UICONTROL 產品語法]**：建立 eVar 值與產品的關聯。 **注意**：如果選取了「[!UICONTROL 產品語法]」，便會停用「[!UICONTROL 銷售捆綁事件]」區段，且無法選取它來編輯。 對於此語法，「[!UICONTROL 捆綁事件]」並不適用。</li><li>**[!UICONTROL 轉換變數語法]**：僅在發生「[!UICONTROL 捆綁事件]」時才會建立 eVar 與產品的關聯。 在這種情況下，您要選取做為「[!UICONTROL 捆綁事件]」的事件。 如果變更此設定但沒有相應地更新 JavaScript 程式碼，則會導致資料遺失。 請參閱[銷售變數](/help/components/dimensions/evar-merchandising.md)。</li></ul> |
| [!UICONTROL 銷售捆綁事件] (僅限 eVar) | 如果「銷售」設定為「[!UICONTROL 轉換變數語法]」，則選定的事件會將產品與目前的 eVar 值捆綁。 若要使用「[!UICONTROL 捆綁事件]」，請將「[!UICONTROL 配置]」設定為「[!UICONTROL 最近]」。 如果「[!UICONTROL 配置]」設定為「[!UICONTROL 原始值]」，則保留第一個 eVar 產品捆綁，直到 eVar 到期為止。 按住 ctrl 鍵 (Windows) 或 cmd 鍵 (Mac)，並按一下清單中的多個項目，即可選取多個事件。 只有在選取了「[!UICONTROL 轉換變數語法]」後，才能選取事件。 |

### 有效期限

`eVars` 會在經過您所指定的時段之後過期。eVar 過期後，即不會再獲得成功事件的評價。您也可以將 eVar 設定成隨著成功事件過期。例如，若您有某個內部促銷會在瀏覽結束時過期，此內部促銷將只會因為在購買或註冊啟動的瀏覽期間所發生的購買或註冊，而獲得評價。

有兩種方式可讓 eVar 過期：

* 您可以將 eVar 設定成在指定的時段或事件之後過期。
* 您可以透過重設 eVar 強制使 eVar 過期，此方法在重設變數用途時很實用。

例如，如果您將 eVar 的過期時間從 30天變更為 90 天，所收集的 eVar 值會在新設定的過期時間內持續存在 (此案例中為 90 天)。系統僅會查看目前的過期設定，以及所收集 eVar 值最後設定的時間戳記，以此判斷過期時間。僅有&#x200B;**[!UICONTROL 重設]**&#x200B;選項能使值過期，而且立即生效。

其他範例：假設在在五月使用某個 eVar 反映內部促銷情形，且該值在 21 天後過期。若要在六月使用該 eVar 擷取內部搜尋關鍵字，您應在 6 月 1 日將此變數強制過期或加以重設。這麼做有助於將內部促銷值排除在六月的報表以外。

### 區分大小寫

eVar 不區分大小寫。 報告中使用的大寫或小寫是根據後端系統註冊的第一個值。 此值可能是第一次出現，也可能在某個時段 (例如，每月) 發生變化，具體取決於與報表套裝相關聯的資料種類和數量。

### 計數器

eVar 通常會用來放置字串值，但也可設定作為計數器。當您嘗試計算使用者在某個事件之前所執行的動作數時，即可將 eVar 當作計數器使用。例如，您可以使用 eVar 擷取購買之前的內部搜尋次數。每次訪客搜尋時，eVar 中都應會有 &#39;+1&#39; 值。若訪客在購買之前做了四次搜尋，您將會看見各個總計數的例項：1.00、2.00、3.00、4.00。但只有 4.00 會獲得購買事件的評分 (訂購和收入度量)。eVar 計數器的值必須是正數。

## 新增或編輯轉換變數

1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]**。
1. 選取報告套裝。
1. 按一下&#x200B;**[!UICONTROL 「編輯設定]** > **[!UICONTROL 轉換]** > **[!UICONTROL 轉換變數」]**。
1. 在[!UICONTROL 轉換變數]頁面，在您要修改的轉換變數旁按一下&#x200B;**[!UICONTROL 展開]**&#x200B;圖示[「+」]。

   或

   按一下&#x200B;**[!UICONTROL 「新增」]**，以新增未使用的 eVar 至報告套裝。
1. 選擇您要修改的轉換變數欄位。

   請參閱[轉換變數 - 說明](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF)。一些欄位可讓您直接在欄位中鍵入。其他欄位可讓您從受支援值的下拉式清單中選擇。
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
