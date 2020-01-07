---
title: 建立解決方案設計文件
description: 瞭解解決方案設計文件是什麼，以及可如何將其用於您的組織。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 建立解決方案設計文件

本質上，解決方案設計文件 (也稱為解決方案設計參考資料或業務需求文件) 是分析實施的藍圖。該文件定義整個組織的相關人員所識別的準則，並在 Adobe Analytics 內將其轉譯為變數。如果沒有這樣的文件，組織會很難協調報表需求，並且往往會遺漏收集重要的資料。

## 必備條件

[驗證 Analytics 實施並發佈至生產環境](../implement-with-launch/validate-publish-prod.md) - 雖然並非直接必要，但 Adobe 建議您建立基本實施，這樣就能在建立及實作其他業務需求時收集重要資料。

## 設計文件的擁有權與位置

* **決定組織中的哪個人員將負責維護解決方案設計文件。**&#x200B;此角色可由個人或團隊擔任。確保甚至在角色變更或組織重組期間，仍會保持維護解決方案設計。這是一份不斷修訂的文件，且必須妥善維護。
* **決定解決方案文件將位於哪個位置。**&#x200B;很難定義一個適合存放解決方案設計文件的最佳位置，但這類文件通常會存放於可廣泛存取的內部位置。例如，共用的試算表或協作工作區，例如 SharePoint 或內部 Wiki。文件未必要能讓所有人編輯，但至少讓可存取報表的人員能夠進行檢視會是有利的做法。

## 定義業務需求

在決定要收集哪些資料時，說要收集「所有內容」可能很簡單，但這麼做會迅速讓資料變得龐雜而難以管理，而且提供的價值甚至會比收集較精簡的資料量來得更低。

1. **決定關鍵績效指標。**&#x200B;您最終希望訪客執行什麼動作? 此問題的答案因不同的產業與行業而異，而且可能有多個答案。例如，購買、註冊或廣告點擊。
1. **找出要收集的最重要的資料。**&#x200B;提出您想要獲得具體答案的業務問題。這些問題的答案可提供如何改善 KPI 的相關分析。
1. **請回答這些問題，並決定您的追蹤需求。**&#x200B;將其分組為維度和量度。
   * 維度是包含文字的變數。例如，內部搜尋詞、產品類別或訪客點按的區域名稱。
   * 量度是您希望訪客執行的具體事件，當訪客執行您想要的動作時，數字則會往上加一。例如，提交訂單、訂閱電子報或提交調查回應。
1. **將維度與量度對映至某個頁面或試算表。**&#x200B;此頁面或表格最終會變成您的解決方案設計文件。某些實用的欄或項目符號圓點包括:
   * 實施狀態: 已規劃、作用中、非作用中、問題等這會通知文件檢視者變數的狀態 (若已實作)，或是否有資料收集的相關問題。
   * 變數名稱: 例如「內部搜尋詞」。此值會是分析師在 Analytics 中使用時所看到的內容。
   * Analytics 變數的對映目標: 您選擇將值指派給哪個預設或自訂 Analytics 變數。維度通常屬於 eVar 之下，而量度則屬於事件之下。
   * 邏輯: 如何設定變數的相關說明，以及決定變數值的項目。例如，「僅在內部搜尋頁面上設定。使用 q 查詢字串參數的值。」
   * 任何您想要包含的其他變數相關注意事項。

## 其他資源

定義解決方案設計文件是相當複雜的專案，對未曾建立這類文件的組織來說更是如此。如需其他協助，Adobe 可提供專業諮詢服務，協助您的組織快速上手並開始執行 Adobe Analytics。若要獲得 Adobe 的專業服務，請聯絡您的客戶經理。您可以填寫[技術預先實施問卷](assets/technical-pre-implementation-questionnaire.pdf)，讓 Adobe 確切瞭解如何根據您的組織需求提供協助。

此外，也有一些 Adobe 合作夥伴可專門協助您建立解決方案設計文件，以及在您的網站上實作 Adobe Analytics。

> [!NOTE] 雖然 Analytics 社群的會員已發現下列實用連結，但 Adobe 並非這些連結的擁有者。檢視其內容時，請將此備註列入考量。

* [設定網站 Analytics 解決方案設計的 大步驟](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance)/7-；文章來源: ObservePoint
* [數位分析程序的架構](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/)；文章來源: Analytics Demystified
* [解決方案設計參考資料其實是您的 BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/)；文章來源: Numeric Analytics
* [如何建立 Adobe Analytics 標籤對映](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/)；文章來源: Antti Koski
* [解決方案設計文件的重要性](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document)；文章來源: Ebiquity

## 後續步驟

在解決方案設計文件中實作變數。

* eVar 簡介: 瞭解 eVar 是什麼、其運作方式，以及如何在實施中使用 eVar
* 事件簡介: 瞭解成功事件是什麼、其運作方式，以及如何在實施中使用成功事件
