---
title: 重點審查（在每次發佈網站後）
description: 請遵循下列步驟，以確保您的實作不會出錯，並符合您的KPI。
translation-type: tm+mt
source-git-commit: 769e29e08871d2da704aa4eabe22371148d486bf
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 0%

---


# 重點審查（在每次發佈網站後）

您為何應每幾個月審查一次實施？ 因此，您可以在資料品質仍然很小的時候，解決任何資料品質問題。 如果您在每個網站發行後都一致執行重點審查，您會發現每兩年的[完整審查](/help/implement/review/full-review.md)要容易得多。 您也會防止小問題發展成大資料問題，而這些問題可能會削弱利益相關者的信心。

## 1.從您的前5大KPI開始。

瞭解您的前5大關鍵績效指標(KPI)將有助於您確定您需要檢查的相關量度和維度。 如果您在過去6個月中未更新KPI，或您的企業尚未建立KPI，請依照[這些指示](/help/implement/review/define-kpis.md)執行。

## 2.確定您的KPI量度和變數仍能正常運作。

請記住，程式碼隨著時間的推移而更新，可能會產生意想不到的後果。 您需要確定與[前5個KPI](/help/implement/review/define-kpis.md)相關的所有量度和維度仍能正常運作。 理想情況下，這應該在網站發行後立即完成；如果您在最近幾個月中尚未完成，請立即執行&#x200B;**。 要執行此操作：

* 建立控制面板，以檢視這些重要度量和變數的每小時趨勢檢視（或為每個度量設定智慧提醒）。 然後監視一兩天，以確保您獲得所需的資料，而且資料正確無誤。\
   尋找轉折點。 準備立即修正任何重大問題。 如果您發現任何不一致之處，請在資料層、標籤管理規則和處理規則中查找原因。
* 重新執行[Analytics Health Dashboard](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)，以監控KPI量度和變數的廣泛趨勢。

*如需如何確保量度和變數正常運作的詳細資訊，請閱 [讀Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) 冠軍Sarah Owen的這些資訊。*

## 3.徹底檢查網站更新區段的資料。

請確定最近的網站版本不會對網站該區段的資料收集造成負面影響：檢閱對應至該區段的所有程式碼和變數，以確保新追蹤如設計般運作。

## 4.更新您的檔案。

如果您最近新增或變更了任何量度或變數，您需要更新業務需求檔案(BRD)和解決方案設計參考(SDR)。

如果您沒有實作檔案，請匯出變數清單，並使用[此範本](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation)建立BRD或SDR。

## 5.立即解決您在資料品質方面發現的任何差距。

評估情況並制定修正資料的計畫。 然後進行所需的變更、更新檔案，並告知利益相關者您所做的變更。



*觀看Adobe Analytics Champion Sarah Owen的這段2分鐘影片，瞭解您將實作審核整合在繁忙排程中的自然時間：*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
