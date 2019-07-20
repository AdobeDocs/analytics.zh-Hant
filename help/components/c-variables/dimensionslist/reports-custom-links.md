---
description: 顯示您網站訪客的慣用連結。例如，網站的首頁上可能有多個連結會顯示同一個頁面。可能有一個圖形連結，和一個文字連結，都連結到同一個頁面。這份報告顯示使用圖形連結和使用文字連結的訪客百分比。
seo-description: 顯示您網站訪客的慣用連結。例如，網站的首頁上可能有多個連結會顯示同一個頁面。可能有一個圖形連結，和一個文字連結，都連結到同一個頁面。這份報告顯示使用圖形連結和使用文字連結的訪客百分比。
seo-title: 自訂連結
solution: Analytics
title: 自訂連結
topic: 報表
uuid: 2e0d0175-d5 e4-4919-b601-3f488 ef3 e090
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 自訂連結

顯示您網站訪客的慣用連結。例如，網站的首頁上可能有多個連結會顯示同一個頁面。可能有一個圖形連結，和一個文字連結，都連結到同一個頁面。這份報告顯示使用圖形連結和使用文字連結的訪客百分比。

您想要追蹤的特定連結必須以特殊標記修改，請參閱[連結追蹤](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_linktracking)。

您可以使用[!UICONTROL 自訂連結報告]執行下列工作:

* 知道您的訪客慣用哪些類型的連結，可以將網站設計最佳化
* 驗證對單一頁面採用多餘連結的必要性

## 行動 SDK 連結名稱 {#section_70C91FE794104B5FBF289B19CC02EA8E}

[行動SDK](https://marketing.adobe.com/resources/help/en_US/mobile/home.html) 使用自訂連結來追蹤動作和生命週期度量。在用於測量行動應用程式的報表套裝中，您可能會看到 SDK 設定的下列連結名稱:

| ADBINTERNAL:Lifecycle | 由 4.x SDK 的生命週期呼叫所傳送。 |
|---|---|
| AMACTION:[action name] | 由 4.x SDK 的 trackAction() 方法所傳送，其中 action name 是呼叫方法時設定的名稱。 |
| ADMS BP Event | 由 3.x SDK 的生命週期呼叫所傳送。 |

