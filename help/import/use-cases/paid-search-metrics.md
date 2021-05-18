---
title: 匯入付費搜尋量度
description: 設定Adobe Analytics以追蹤您的付費搜尋量度（例如Google AdWords、MSN、Yahoo等）的步驟 使用資料來源。
exl-id: b25a2a26-d277-4a51-9194-973acb425095
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 8%

---

# 使用[!UICONTROL Data Sources]匯入[!UICONTROL 付費搜尋]量度

對於許多行銷組織而言，付費搜尋是觸及新客戶和維繫現有客戶&#x200B;的最有價值且最可靠的方式之一。 Adobe Analytics的[!UICONTROL Data Sources]功能可讓您輕鬆從數位廣告平台（例如Google AdWords）匯入進階付費搜尋資料。 您可將其與其他行銷資料以及現場行為和客戶屬性資料整合，讓您對組織的付費搜尋工作有更深入的見解。

這些步驟會示範如何設定與AdWords的整合，以匯入關鍵字資料以及度量，例如印象、點按、每次點按成本等。

這些步驟說明如何設定一次性匯入每次點按付費資料。 但是，[!UICONTROL Data Sources]允許使用此處所述的檔案格式持續匯入資料。 視您的付費搜尋平台而定，您可以排程定期匯出（每日、每月等）、設定自動化流程，將這些匯出轉換為Adobe Analytics所需的檔案格式，並將這些檔案上傳至Adobe Analytics，以便進行付費搜尋整合報告。

## 先決條件

* 您已實作付費搜尋偵測。
* 您正在擷取追蹤代碼資料。
* 每個廣告群組都有唯一的追蹤代碼。

## 設定[!UICONTROL 成功事件]

我們的第一步是讓Adobe Analytics做好準備，以接收指標。 若要這麼做，您必須設定一些成功事件。

[!UICONTROL 成功事件是可追蹤的動作。]您可判斷[!UICONTROL 成功事件]是什麼。 為了追蹤[!UICONTROL 付費搜尋]量度，我們想在[!UICONTROL 點按]、[!UICONTROL 印象]、[!UICONTROL 總成本]和啟用[!UICONTROL 追蹤代碼]周圍設定[!UICONTROL 成功事件]。

1. 前往&#x200B;**[!UICONTROL Adobe Analytics>管理>報表套裝]**。
1. 選取報告套裝。
1.  按一下&#x200B;**[!UICONTROL 「編輯設定 > 轉換 > 成功事件」]**。

   ![成功事件](assets/success-events.png)

1. 在「自訂成功事件」下方，使用&#x200B;**[!UICONTROL 新增]**&#x200B;建立3個自訂成功事件：[!UICONTROL 點按]（計數器）、[!UICONTROL 印象]（計數器）和[!UICONTROL 總成本]（貨幣）。

   ![新成功事件](assets/new-success-events.png)

1. 按一下「儲存」。您應該會收到訊息，告知已核准您的儲存。
1. 導覽至&#x200B;**[!UICONTROL 管理>報表套裝>編輯設定>轉換>轉換變數]**。
1. 選取&#x200B;**[!UICONTROL **[!UICONTROL &#x200B;促銷活動>促銷活動變數&#x200B;]**下方的追蹤代碼]**&#x200B;旁的核取方塊，以啟用追蹤代碼。

   ![促銷活動變數](assets/campaign-variable.png)

## 設定資料來源

[!UICONTROL 資料] 來源可讓您與Adobe Analytics共用非點按流資料。在此案例中，我們使用Adobe Analytics來追蹤付費搜尋量度。 我們使用追蹤代碼作為將兩個資料片段(付費搜尋量度和Adobe Analytics量度)連結在一起的關鍵。

1. 導覽至&#x200B;**[!UICONTROL Adobe Analytics>管理>所有管理>資料來源]**。
1. 選擇&#x200B;**[!UICONTROL Create]**&#x200B;標籤以開始啟動新的資料來源。
1. 在&#x200B;**[!UICONTROL 選擇類別]**&#x200B;下，選擇&#x200B;**[!UICONTROL 廣告促銷活動]**。

   ![資料來源](assets/data-sources.png)

1. 在&#x200B;**[!UICONTROL 選擇類型]**&#x200B;下，選擇&#x200B;**[!UICONTROL 一般每次點按付費服務]**。
1. 按一下&#x200B;**[!UICONTROL 「啟用」]**。[!UICONTROL 資料來源啟動精靈]會顯示：

   ![啟用精靈](assets/ds-activation-wizard.png)

1. 按一下&#x200B;**[!UICONTROL Next]**&#x200B;並命名資料源。 此名稱會出現在「資料來源管理員」中。
1. 接受服務協定，然後按一下&#x200B;**[!UICONTROL Next]**。
1. 選取三個標準量度：[!UICONTROL 印象]、[!UICONTROL 點按]和[!UICONTROL 總成本]，然後按一下&#x200B;**[!UICONTROL 下一頁]**。
1. 現在，將此新資料來源「映射」至我們在[設定成功事件](/help/admin/admin/c-success-events/t-success-events.md)中建立的自訂事件。

   ![映射](assets/data-source-mapping.png)

1. 選擇資料維度
勾選「追蹤代碼」旁的方塊，然後按一下「下一步」。****
1. 映射資料Dimension。
將匯入的資料維度（屬性）對應至您要儲存的Adobe Analytics屬性。 這可以是標準尺寸或eVar。 按一下**[!UICONTROL Next]**&#x200B;後，生成的映射將顯示在摘要中：

   ![摘要](assets/data-source-summary.png)

1. 按一下「**[!UICONTROL 儲存]**」。
1. 按一下&#x200B;**[!UICONTROL Download]**下載此資料源的模板檔案。
檔案名與您最初指定的資料源類型相對應——在本例中為「Generic Pay-Per-Click Service template.txt」。
1. 在您最愛的文字編輯器中開啟範本。
檔案已填入量度和維度及其對應。

## 匯出PPC資料並上傳至Analytics

這些步驟類似於Google Adwords、MSN、Yahoo和其他PPC帳戶的工作。

### 匯出資料

1. 登入您的PPC帳戶並建立新報表或匯出。
請確定匯出包含下列欄位：日期、目標URL（著陸頁面）、印象、點按次數和成本。 匯出可包含其他欄位，但您會刪除下列步驟。
1. 如果可能，請將報表儲存為`.csv`或Tab分隔檔案。 如此可讓您在下列步驟中更輕鬆地使用。
1. 在Microsoft Excel中開啟檔案。

### 在Microsoft Excel中編輯檔案

1. 在Microsoft Excel中，刪除上述欄以外的所有欄。
1. 刪除頂端的任何額外行。
1. 若要將追蹤代碼與目標URL隔離：
a.從所有欄複製及貼上資料。
b.按一下**[!UICONTROL 資料>文本到列]**。
c.在精靈的步驟1中，請確定已選取**[!UICONTROL Delimited]**，然後按一下&#x200B;**[!UICONTROL Next]**。
d.在精靈的步驟2中，根據您建立URL的方式指定分隔字元(以？ 或&amp;)，然後按一下**[!UICONTROL Next]**。
e.在精靈的步驟3中，預覽您的資料，並確定其中一欄是「trackingcoodename=trackingcode」。 如果您有其他變數，請重複這些步驟（使用&amp;作為分隔字元）。
f.除追蹤代碼、印象、點按和成本外，刪除所有欄。 新增名為「日期」的欄，並依下列順序組織欄：日期：追蹤代碼：:印象：點按次數：成本。
1. 將此資料新增至您在上述「設定資料來源」區段中下載的範本。
現在，您已準備好上傳檔案。

### 透過FTP將檔案上傳至Adobe Analytics

返回「資料來源」精靈以取得指示，並透過FTP上傳檔案：

![上傳FTP](assets/upload-ftp.png)

## 建立計算量度

新增計算量度有助於做出每次點按付費決策。

例如，您可以新增下列[計算量度](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| 名稱 | 公式 | 量度類型 | 說明 |
| --- | --- | --- | --- |
| 每次瀏覽頁面檢視次數 | 頁面檢視次數/瀏覽次數 | 數值 | 套用至網站級別時: 顯示每次瀏覽的平均頁數。套用至「人氣最高的頁面」報告時: 顯示每次瀏覽特定頁面的平均檢視次數。 |
| 平均訂購值 | 收入/訂購量 | 貨幣 | 顯示每次訂購的平均收入。 |
| 每次瀏覽收入 | 收入／瀏覽 | 貨幣 | 顯示每次瀏覽的平均收入。 |
| 點進率(CTR) | 點按次數／印象 | 數值 | 測量線上廣告或電子郵件行銷促銷活動的點按次數與曝光次數的比率。 |
| 利潤 | 收入——成本 | 貨幣 | 顯示促銷活動的收入減去成本。 |
| 每次曝光的利潤(PPI) | （收入——成本）/印象 | 貨幣 | 顯示每次顯示廣告時產生多少收入，並與成本平衡。 |
| 廣告支出報酬率(ROAS) | 銷售額／廣告支出 | 貨幣 | (ROI)代表在相應廣告上花費的美金。 |

## 設定並執行報表

最後一個步驟是將資料來源量度和任何計算量度新增至「追蹤代碼」報表，並深入探究促銷活動，以立即檢視每個廣告群組的執行情形。

1. 在&#x200B;**[!UICONTROL Adobe Analytics>報表]**&#x200B;中，選取您已匯入資料來源的報表套裝。
1. 導覽至&#x200B;**[!UICONTROL 報表>促銷活動>追蹤代碼>追蹤代碼]**。
1. 選擇日期範圍。
1. 按一下「**[!UICONTROL 量度>新增]**」，並從「標準量度」清單中新增您的資料來源量度（點按、印象、總成本）。
1. 對您新增的任何計算量度執行相同動作。 您新增量度時，報表將會更新。
