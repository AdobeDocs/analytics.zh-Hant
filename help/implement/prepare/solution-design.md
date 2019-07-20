---
title: 建立解決方案設計文件
seo-title: 建立解決方案設計文件
description: 瞭解解決方案設計文件的用途，以及如何在組織中使用它。
seo-description: 瞭解解決方案設計文件的用途，以及如何在組織中使用它。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 建立解決方案設計文件

解決方案設計文件(也稱為解決方案設計參考或商業需求文件)本質上是您的分析實作的藍圖。它定義所有組織中的利益相關者識別的標準，並將它們轉換為Adobe Analytics中的變數。沒有一個組織，組織就難以協調報告需求，並且傾向於錯失重要資料。

## 必備條件

[驗證您的Analytics實作並發佈至生產](../implement-with-launch/validate-publish-prod.md) 環境-雖然並非直接需要，Adobe建議您實施基本實施，以便在建立並實施其他業務需求時收集重要資料。

## 設計文件的所有權和位置

* **確定組織中誰負責維護解決方案設計文件。** 此角色可以是個人或團隊。確保即使透過角色變更或組織重新架構，仍能保留解決方案設計。它是一份即時文件，必須妥善維護。
* **確定解決方案文件的常駐位置。** 解決方案設計文件沒有單一最佳地方，但通常居住在易於存取的內部位置。範例包括共用試算表或協作工作區，例如SharePoint或內部Wiki。它不需要讓每個人都能編輯，但是可以存取報告的人員也可以檢視它。

## 定義業務需求

決定要收集哪些資料時，可以輕鬆地說「一切」，但是可以快速地管理無法管理，甚至可以比收集更簡潔的資料金額更少。

1. **確定關鍵績效指標。** 您最終希望訪客做甚麼？此問題的答案因產業和垂直而異，可能是多方面的。範例包括購買、註冊或廣告點按。
1. **找出要收集的最重要資料。** 詢問您想要特定答案的商業問題。這些問題的解答將提供如何改善KPI的見解。
1. **進行這些問題並決定追蹤需求。** 將它們分組至維度和度量。
   * 維度是包含文字的變數。範例將包括內部搜尋詞、產品類別或訪客點按區域的名稱。
   * 度量是您希望訪客執行的特定事件-當他們執行您要執行的動作時，數目會增加一。例如提交訂單、訂閱電子報或提交調查回應。
1. **將維度和度量對應至頁面或試算表。** 此頁面或表格最終會變成您的解決方案設計文件。一些有用的欄或項目符號，以納入：
   * 實作狀態：計劃、活動、非活動、問題等。這會通知文件的檢視器變數的狀態、實施的狀態，或是資料收集的問題。
   * 變數名稱：例如，「內部搜尋詞」。分析人員在Analytics中工作時會看到這個值。
   * 映射至下列項目的Analytics變數：您選擇要指派值的預設或自訂Analytics變數。維度通常落在eVar下方，而量度位於事件下方。
   * 邏輯：說明變數的設定方式，以及決定變數的值。例如，「僅在內部搜尋頁面上設定」。請使用q查詢字串參數的值」。
   * 您想要包含與變數相關的其他附註

## 其他資源

定義解決方案設計文件是相當複雜的專案，對於尚未建立過的組織而言尤其如此。如果需要額外的協助，Adobe會提供專業諮詢，協助您的組織開始使用Adobe Analytics。如果您想要註冊Adobe的專業服務，請聯絡您的客戶經理。A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

此外，還有一些Adobe合作夥伴專門協助建立解決方案設計文件，並在您的網站上實施Adobe Analytics。

> [!NOTE] 雖然Analytics社群成員發現下列連結有用，但並不屬於Adobe所有。檢視其內容時，請考量此附註。

* [使用SearchPoint設定網頁分析解決方案設計](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) 的步驟
* [Analytics DemyStitfied的Framework for Digital Analytics程序](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/)
* [Solution Design Reference實際上是您BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) 的數值分析
* [如何由Antti Koski製作Adobe Analytics標記圖](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/)
* [Ebiquity的解決方案設計文件](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) 重要性

## 後續步驟

在您的解決方案設計文件中實施變數。

* eVar簡介：瞭解eVar的用途、運作方式以及如何在實施中使用
* 活動簡介：瞭解成功事件是甚麼，它如何運作，以及如何在實施中使用一個事件
