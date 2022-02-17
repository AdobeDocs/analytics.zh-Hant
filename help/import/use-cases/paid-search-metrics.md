---
title: 導入付費搜索度量
description: 配置Adobe Analytics以跟蹤您的付費搜索指標(如GoogleAdWords、MSN、雅虎等)的步驟 使用資料源。
exl-id: b25a2a26-d277-4a51-9194-973acb425095
source-git-commit: 7c5bfadabe2ea851bb881d067d48b4f4700a53c7
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 8%

---

# 導入 [!UICONTROL 付費搜索] 度量 [!UICONTROL 資料源]

對於許多市場營銷組織來說，付費搜索是接觸新客戶和保留現有客戶&#x200B;的最有價值和最可靠的方法之一。 的 [!UICONTROL 資料源] Adobe Analytics的功能使從GoogleAdWords等數字廣告平台導入高級付費搜索資料變得容易。 您可以將其與其他營銷資料以及現場行為和客戶屬性資料整合，以便更好地洞察您組織付費搜索工作。

這些步驟將向您說明如何配置與AdWords的整合以導入關鍵字資料以及諸如印象、按一下、每次按一下成本等度量。

這些步驟說明了如何設定一次性導入按點擊付費資料。 但是， [!UICONTROL 資料源] 允許使用此處描述的檔案格式持續導入資料。 根據您的付費搜索平台，您可能可以安排定期導出（每日、每月等），設定自動化流程，將這些導出轉換為Adobe Analytics要求的檔案格式，並將這些檔案上載到Adobe Analytics，以便進行付費搜索整合報告。

## 先決條件

* 您已實施付費搜索檢測。
* 您正在捕獲跟蹤代碼資料。
* 每個廣告組都有唯一的跟蹤代碼。

## 配置 [!UICONTROL 成功事件]

我們的第一步是讓Adobe Analytics準備好接收指標。 為此，您需要設定一些成功事件。

[!UICONTROL 成功事件是可追蹤的動作。]你決定 [!UICONTROL 成功事件] 。 為了跟蹤 [!UICONTROL 付費搜索] 度量，我們要設定 [!UICONTROL 成功事件] 繞 [!UICONTROL 點擊]。 [!UICONTROL 印象]。 [!UICONTROL 總成本] 啟用[!UICONTROL 跟蹤碼]。

1. 轉到 **[!UICONTROL Adobe Analytics>管理>報告套件]**。
1. 選取報表套裝。
1.  按一下&#x200B;**[!UICONTROL 「編輯設定 > 轉換 > 成功事件」]**。

   ![成功事件](assets/success-events.png)

1. 在自定義成功事件下，使用 **[!UICONTROL 添加新]** 要建立3個自定義成功事件： [!UICONTROL 按一下] （計數器）, [!UICONTROL 印象] （計數器）和 [!UICONTROL 總成本] （貨幣）。

   ![新成功事件](assets/new-success-events.png)

1. 按一下「儲存」。您應收到已批准保存的消息。
1. 導航到 **[!UICONTROL 「管理」>「報表套件」>「編輯設定」>「轉換」>「轉換變數」]**。
1. 通過選中旁邊的複選框啟用跟蹤代碼 **[!UICONTROL 跟蹤代碼]** 在 **[!UICONTROL 市場活動>市場活動變數]**。

   ![促銷活動變數](assets/campaign-variable.png)

## 設定資料源

[!UICONTROL 資料源] 允許您與Adobe Analytics共用非點擊流資料。 在這種情況下，我們使用Adobe Analytics跟蹤付費搜索指標。 我們使用跟蹤代碼作為關鍵，將兩個資料 — 付費搜索指標和Adobe Analytics指標 — 聯繫在一起。

1. 導航到 **[!UICONTROL Adobe Analytics>管理>所有管理>資料源]**。
1. 選擇 **[!UICONTROL 建立]** 頁籤，以開始激活新資料源。
1. 下 **[!UICONTROL 選擇類別]**&#x200B;選中 **[!UICONTROL 廣告活動]**。

   ![資料來源](assets/data-sources.png)

1. 下 **[!UICONTROL 選擇類型]**&#x200B;選中 **[!UICONTROL 一般按點擊付費服務]**。
1. 按一下&#x200B;**[!UICONTROL 「啟用」]**。的 [!UICONTROL 資料源激活嚮導] 顯示：

   ![啟用精靈](assets/ds-activation-wizard.png)

1. 按一下 **[!UICONTROL 下一個]** 並命名資料源。 此名稱顯示在資料源管理器中。
1. 接受服務協定，然後按一下 **[!UICONTROL 下一個]**。
1. 選擇三個標準度量： [!UICONTROL 印象]。 [!UICONTROL 按一下] 和 [!UICONTROL 總成本] 按一下 **[!UICONTROL 下一個]**。
1. 現在，將此新資料源「映射」到我們在中建立的自定義事件 [配置成功事件](/help/admin/admin/c-success-events/t-success-events.md)。

   ![映射](assets/data-source-mapping.png)

1. 選擇資料維選中跟蹤代碼旁邊的框，然後按一下 **[!UICONTROL 下一個]**。
1. 映射資料Dimension。
將導入的資料維（屬性）映射到要將其儲存在的Adobe Analytics屬性。 這可能是標準尺寸或eVar。 按一下後 **[!UICONTROL 下一個]**，生成的映射顯示在摘要中：

   ![摘要](assets/data-source-summary.png)

1. 按一下「**[!UICONTROL 儲存]**」。
1. 按一下 **[!UICONTROL 下載]** 下載此資料源的模板檔案。
檔案名與您最初指定的資料源類型對應 — 在本例中為「Generic Pay-Per-Click Service template.txt」。
1. 在最喜愛的文本編輯器中開啟模板。
檔案已填充度量和維及其映射。

## 導出PPC資料並將其上載到分析

類似於GoogleAdwords、MSN、Yahoo和其他PPC帳戶的這些工作步驟。

### 導出資料

1. 登錄到PPC帳戶並建立新報告或導出。
確保導出包含以下欄位：日期、目標URL（登錄頁）、印象、按一下和成本。 導出可以包括其他欄位，但您將刪除下面的步驟。
1. 如果可能，將報告另存為 `.csv` 或制表符分隔的檔案。 這將使在以下步驟中更容易使用。
1. 在MicrosoftExcel中開啟檔案。

### 在MicrosoftExcel中編輯檔案

1. 在MicrosoftExcel中，刪除上述列以外的所有列。
1. 刪除頂部的任何額外行。
1. 要將跟蹤代碼與目標URL隔離，請：a.從所有列複製和貼上資料。
b.按一下 **[!UICONTROL 資料>文本到列]**。
c.在嚮導的步驟1中，確保 **[!UICONTROL 分隔]** 已選中並按一下 **[!UICONTROL 下一個]**。
d.在嚮導的步驟2中，根據您建立URL的方式指定分隔符(或？ 或&amp;，然後按一下 **[!UICONTROL 下一個]**。
e.在嚮導的步驟3中，預覽資料並確保其中一列是「trackingcodename=trackingcode」。 如果有其他變數，請重複這些步驟（使用&amp;作為分隔符）。
f刪除除跟蹤代碼、印記、按一下和成本之外的所有列。 添加名為「日期」的新列並按以下順序組織列：日期：:跟蹤代碼：:印象：按一下：成本。
1. 將此資料添加到您在上面「設定資料源」部分下載的模板中。
現在，您已準備好上載檔案。

### 通過FTP將檔案上傳到Adobe Analytics

返回「資料源」嚮導以獲取說明，並通過FTP上傳檔案：

![上載FTP](assets/upload-ftp.png)

## 建立計算量度

添加計算的度量在做出按點擊付費的決策時會很有幫助。

例如，您可以添加這些 [計算度量](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=en#calculated-metrics):

| 名稱 | 公式 | 量度類型 | 說明 |
| --- | --- | --- | --- |
| 每次瀏覽頁面檢視次數 | 頁面檢視次數/瀏覽次數 | 數值 | 套用至網站級別時: 顯示每次瀏覽的平均頁數。套用至「人氣最高的頁面」報告時: 顯示每次瀏覽特定頁面的平均檢視次數。 |
| 平均訂購值 | 收入/訂購量 | 貨幣 | 顯示每次訂購的平均收入。 |
| 每次訪問的收入 | 收入/訪問 | 貨幣 | 顯示每次訪問的平均收入。 |
| 點擊率(CTR) | 點擊/印象 | 數值 | 衡量線上廣告或電子郵件營銷活動的點擊率與印象的比率。 |
| 利潤 | 收入 — 成本 | 貨幣 | 顯示市場活動的收入減去成本。 |
| 每印象利潤(PPI) | （收入 — 成本）/印象 | 貨幣 | 顯示每次顯示廣告時產生的收入與成本平衡。 |
| 廣告支出退貨(ROAS) | 銷售金額/廣告支出 | 貨幣 | (ROI)表示在相應廣告上每美元所得的美元。 |

## 配置和運行報告

最後一步是將資料源度量和任何計算的度量添加到跟蹤代碼報告中，並細化到市場活動，以立即查看每個廣告組的執行情況。

1. 在 **[!UICONTROL Adobe Analytics>報告]**，選擇已導入資料源的報表套件。
1. 導航到 **[!UICONTROL 報表>市場活動>跟蹤代碼>跟蹤代碼]**。
1. 選擇日期範圍。
1. 按一下 **[!UICONTROL 度量>添加]** 並從標準度量清單中添加資料源度量（按一下、印象、總成本）。
1. 對您可能添加的任何計算度量執行同樣操作。 在添加度量時，報告將更新。
