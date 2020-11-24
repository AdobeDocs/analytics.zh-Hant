---
title: 次要實作審查（在每個網站發行後）
description: 請遵循下列步驟，以確保您的實作不會出錯，並符合您的KPI。
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# 次要實作審查（在每個網站發行後）

為何在每次發佈網站後都應檢閱實作？ 因為您需要確保您的程式碼更新不會產生任何意外的後果，而且您應在資料品質仍然很小時，解決資料品質的問題。 如果您每次發佈網站後都一致執行此次「小評論」，您會發現「大評 [論](/help/implement/review/major-review.md) 」（每6個月）要容易得多。 您也會防止小問題發展成大資料問題，而這些問題可能會削弱利益相關者的信心。

## 1.此版本對網站該區段的資料有何影響？

進行徹底的單元測試：檢閱與您剛更新之網站區段對應的所有程式碼和變數，以確保新追蹤能如設計般運作。

## 2.更新檔案

使用您新增／變更的任何變數來更新您的業務需求檔案(BRD)和解決方案設計參考(SDR)，以配合啟動。

沒有您實作的檔案嗎？ 匯出變數清單，並使用此範本建立BRD或SDR [](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)。

## 3.從您的前5大KPI開始

瞭解您的前5大關鍵績效指標(KPI)將有助於您確定您需要檢查的相關量度和維度。 如果您在過去6個月中未更新KPI，或您的企業尚未建立KPI，請依照下列 [指示](/help/implement/review/define-kpis.md)。

## 4.發行後，所有KPI量度和變數是否仍能正常運作？

請記住，任何程式碼更新都可能產生意想不到的後果。 您需要確定與前5個KPI相關的所有量度 [和維度](/help/implement/review/define-kpis.md) ，仍能正常運作。 要執行此操作：

* **建立控制面板** ，以檢視這些關鍵量度和變數的每小時趨勢檢視您也可以針對每個量度設定智慧提醒)，並在發行後的一兩天內加以監控，以確保您獲得預期的資料，而且資料正確無誤。 尋找轉折點。 準備立即修正任何重大問題。 如果您發現任何不一致之處看起來不正確，請查看您的資料層、標籤管理規則和處理規則，以找出原因。
* **重新執行Analytics Health Dashboard** ，以監控KPI量度和變數的廣泛趨勢。
如需如何確保量度和變數正常運作的詳細資訊，請閱讀Adobe Analytics Champion Sarah Owen的這些秘訣。

## 5.您的資料品質是否存在差距？

評估情況並制定修正資料的計畫。 然後進行所需的變更、更新檔案，並告知利益相關者您所做的變更。

觀看Adobe Analytics Champion Sarah Owen的這段影片，瞭解您將實作審核與繁忙排程整合的自然時間：

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
