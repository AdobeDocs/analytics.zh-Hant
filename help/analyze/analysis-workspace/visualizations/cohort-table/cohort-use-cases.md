---
description: 瞭解同類群組分析的一些使用案例範例。
keywords: Analysis Workspace
title: 同類群組分析使用案例
feature: Visualizations
role: User, Admin
exl-id: fc7e7bad-ab57-4bb8-a448-60b9397ef5af
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 99%

---

# 同類群組分析使用案例

[!UICONTROL 同類群組分析]的使用案例範例。

## 應用程式參與使用案例

假設您想分析已安裝您應用程式的用戶，在一段時間內參與應用程式的情形。用戶是否安裝應用程式後就不曾使用？還是使用一陣子後不用了？或是一段時間後仍持續使用？

您可以建立六個月的同類群組分析。

**詳細程度**: 每月，從 2015 年 1 月到 2015 年 6 月。

**包含量度**：應用程式安裝。

**回訪量度**：作業階段或啟動次數

後續月份的訪客必須具有工作階段或至少啟動此應用程式，否則不會計算為&#x200B;*`engaged`*。[!UICONTROL 同類群組分析]接著會顯示使用模式，其中 *`App Install`* 一律發生在第 0 個月。您可能發現無論用戶於何時安裝應用程式，使用量都在第 2 個月下降。(對於在 2015 年 1 月安裝應用程式的用戶，第 2 個月是指 2015 年 3 月。針對 2015 年 2 月安裝應用程式的使用者，第 2 個月是 2015 年 4 月，依此類推。) 此分析可讓您在所有使用者安裝應用程式後的第二個月內，向他們傳送電子郵件或推播訊息，以提醒他們使用此應用程式。

## 訂閱使用案例

您在 Adobe.com 工作並提供免費 Creative Cloud 訂閱。您的目標是讓用戶從免費版本升級至 30 天試用版，最終升級至付費版本。

**詳細程度**：每月

**包含量度**：下載連結

**回訪量度**：購買付費 Creative Cloud

使用此[!UICONTROL 同類群組分析]，假設您發現 8% 到 10% 的免費 Creative Cloud 用戶在安裝後第一個月進行升級 (無論用戶於何時進行安裝)。12-15% 於使用第二個月進行升級。之後升級率顯著下降：4-5% 在第三個月，3-4% 在第四個月，1-2% 在第五個月。

發現您必須在第三個月挽留潛在客戶後，即可設定在第三個月期中針對一組抽樣用戶發送電子郵件促銷活動，對尚未升級的用戶提供 $50 的優惠券。

幾個月後再次執行同類群組分析報表。對於推出行銷活動後形成的同類群組，在第三個月轉換為付費 Creative Cloud 訂閱的比率從 4-5% 提高為 13-14%，針對從該點以後到達第三個月的每個每月同類群組，代表每個同類群組產生數十萬美元的收入。

## 複雜同類群組區段使用案例

一家大型連鎖飯店針對多個客戶群組推出行銷活動，並追蹤其成效。為找出要鎖定的最佳用戶同類群組，他們希望建立非常明確的同類群組。他們能使用[!UICONTROL 同類群組表格]中增強的[!UICONTROL 包含]和[!UICONTROL 回訪]標準，以多個量度和區段設定合適的同類群組，找出表現不佳的客戶群組，進而利用促銷活動和產品建議鎖定這些客戶，增加訂單量。

## 應用程式版本採用使用案例

一家大型保險公司透過其行動應用程式，提升大量客戶參與。然而，隨著他們的應用程式增加了新功能，其客戶是否升級至最新的應用程式版本至關重要。他們可以透過[!UICONTROL 自訂維度]同類群組，並排分析和比較其所有應用程式版本，以瞭解要鎖定使用哪個應用程式版本的客戶。此外，他們也可以追蹤保留率和流失率，查看在一段時間中，特定應用程式版本是否讓客戶不想使用該應用程式。他們能透過行動傳訊重新與這些用戶互動，並讓用戶升級至最新版本，以使用他們最新的功能。

## 行銷活動黏著度使用案例

一家跨國媒體公司推出目標式行銷活動，吸引用戶前往其各平台，以提升客戶參與。每個平台的廣告花費皆根據客戶參與度和保留率，因此，成功的行銷活動對於其業務的成功至關重要。他們可使用[!UICONTROL 同類群組]表格中新的[!UICONTROL 自訂維度]同類群組功能，並排比較各種行銷活動，找出哪些行銷活動最能有效吸引和保留用戶，進而提升參與度。接著，他們便能找出讓行銷活動成功的關鍵，並將其套用至其他行銷活動，以提升各平台的參與度。

## 產品上市使用案例

一家大型服裝零售業者擁有許多特定客戶區段，為其業務帶來大部分的收入。每個區段皆有針對該區段設計和打造的特定產品。隨著每次產品上市，他們想知道在一段時間中，新產品如何促進各同類群組的銷售量。 他們可以使用[!UICONTROL 同類群組分析]中新的[!UICONTROL 延時表格]設定，分析指定客戶區段在產品上市前後的行為和帶來的收入。使用此資訊，他們可以找出哪些產品創造新收入，以及哪些產品無法吸引客戶。

## 個人黏著度 - 最忠實的使用者使用案例

一家大型航空公司的成功和收入大部分來自重複和忠實的客戶。在許多情況下，他們的忠實旅客佔其收入的大部分，而保留這些客戶對他們的長期成功至關重要。找出他們最忠實和一致的客戶通常很困難。但是，[!UICONTROL 同類群組分析]中新的[!UICONTROL 滾動式計算]設定，讓他們能分析忠實客戶區段，並找出哪些旅客為每月重複購買者。接著，他們便可用獎勵和福利來鎖定這些忠實旅客。 此外，他們還能將「同類群組」類型從保留率切換至流失率，找出不是每月重複購買者的客戶，並透過行銷活動鎖定這些區段，進而重新與客戶互動，確保其日後仍會是忠實客戶。
