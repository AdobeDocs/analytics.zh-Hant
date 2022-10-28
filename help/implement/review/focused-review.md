---
title: 重點審視 (每次網站發佈後)
description: 請按照下列步驟，確認您的實施作業沒有任何錯誤，並且符合您的 KPI。
feature: Implementation Basics
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 84%

---

# 重點審視 (每次網站發佈後)

為何應每幾個月審視實施作業一次？您可把關資料品質，趁問題還不嚴重時儘早解決。如果能在每次網站發佈後重點審視一番，您會發現兩年一次的[完整審視](/help/implement/review/full-review.md)比較輕鬆。這麼做也能防止小問題惡化，進而影響相關人員的信心。

## 1. 從您的 5 大 KPI 開始

明瞭 5 大關鍵績效指標 (KPI) 有助於確定必須檢查哪些相關量度和維度。如果您已有 6 個月未更新 KPI，或您的企業尚未建立 KPI，請依照[這些指示](/help/implement/review/define-kpis.md)處理。

## 2.確認KPI量度和變數仍正常運作

請記住，隨時間更新程式碼可能會有無預期的影響。請確定與 [5大KPI](/help/implement/review/define-kpis.md) 仍正常運作。 理想情況下，這會在網站發佈後立即完成；如果你最近幾個月沒做過，那就做吧 *now*. 執行方法：

* 建立控制面板，檢視這些重要度量和變數每小時的趨勢 (或為每個度量設定[智慧型提醒](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace))。監控一兩天，確認資料走勢符合預期，且資料正確無誤。尋找轉折點。做好準備，以便在發現任何重大問題時能立即解決。如果有任何不一致的地方，請檢查資料層、標籤管理程式規則和處理規則，從中尋找原因。
* 重新執行 [Analytics 運作狀態控制面板](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252)，監控 KPI 量度和變數的主要趨勢。

*如需如何確認量度和變數正常運作的詳細資訊， [閱讀這些秘訣](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) 來自Adobe Analytics冠軍莎拉·歐文。*

## 3. 徹底檢查網站更新區段的資料

確認最新的網站版本不會對網站該區段的資料收集作業造成負面影響：檢視該區段所對應的所有程式碼和變數，確保新追蹤機制的運作成效符合預期。

## 4. 更新您的文件

如果您最近曾新增或變更任何量度或變數，請務必更新業務需求文件 (BRD) 和解決方案設計參考資料 (SDR)。

如果您沒有這些實施作業文件，請先匯出變數清單，再使用[此範本](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=zh-Hant#implementation)建立 BRD 或 SDR。

## 5. 立即解決資料品質不如預期的問題

評估情況並制定資料修復計畫。執行所需的變更、更新文件，並告知相關人員您所做的變更。

*觀看 Adobe Analytics Champion 專家 Sarah Owen 的這部 2 分鐘影片，了解如何在繁忙的工作中安排審視實施作業項目的時間：*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
