---
description: 瞭解如何將Mobile Services處理規則移轉至Adobe Analytics
title: 將Mobile Services處理規則移轉至Adobe Analytics
translation-type: tm+mt
source-git-commit: c2610bf25c960039ca8638cecbd05f3a8b28376f
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 18%

---


# 將Mobile Services處理規則移轉至Adobe Analytics

隨著Adobe Mobile Services功能即將落幕（尚未宣佈），本檔案提供您如何將您在Mobile Services UI中建立的任何其他處理規則（生命週期量度以外）移轉至Adobe Analytics的指示。

處理規則用於將上下文資料變數的值移至 prop 和 eVar。例如，您可以將「搜尋詞」上下文資料變數的值放入「商務變數」eVar的值中，並覆寫每次點擊的值。 若沒有處理規則，上下文資料變數就毫無意義，且不會填入 Analytics 的任何報表。

本檔案也說明分析工作區中的行動使用狀況報告，並討論移轉其他行動服務功能的可行性。

## 移轉處理規則

如果您運用Mobile Services來提供免費功能，例如處理規則和使用狀況報告功能，則可順暢地移至Analytics UI（處理規則UI或分析工作區）以完成這些功能。 對於「生命週期量度」或在AA處理規則UI中設定的規則，您不必進行任何移轉。 生命週期量度是「現成可用」的量度，在您的應用程式中首次實作Mobile SDK時會自動收集。

不過，如果您在Mobile Services UI中設定任何其他處理規則（生命週期量度以外），您應移轉這些規則，以便在失去Mobile Services存取權後，在Analytics中編輯／刪除它們。

1. 登入experience.adobe.com並前往Mobile Services。
1. 按一下您要移轉至Adobe Analytics之行動應用程式的齒輪圖示，其上下文變數對應。
1. 按一下「 **[!UICONTROL 管理變數和量度]** 」功能表項目，然後按一下「 **[!UICONTROL 自訂變數]** 」標籤。 您可在此處查看哪些上下文變數映射（上下文資料）已新增至設定。 記下這些設定（或擷取螢幕擷取）。 範例：

   ![上下文變數](assets/context-var.png)

1. 在Experience Cloud中，請切換至Adobe Analytics，並確定您所在的行動報表套裝與您在Mobile Services中所檢視的報表套裝相同。
1. 前往「管理>報表套裝>編輯設定>一般>處理規則」。
1. 按一下「新增規則」。
1. 忽略條件並繼續新增Mobile Services中存在的相同上下文變數。

   ![處理規則](assets/proc-rule.png)

## 分析工作區中的行動使用狀況報告

除了行動量度和維度（如果報表套裝已啟用Mobile Services）之外，分析工作區還包含數個可協助分析的行動專案範本：

* 傳送訊息：著重於應用程式內及推播訊息的效能。
* 位置：當中的地圖可呈現位置資料。
* 關鍵量度：掌握您應用程式的關鍵量度。
* 應用程式使用情形：應用程式擁有多少使用者和首次啟動次數，而平均工作階段時間長度又如何？
* 收購：行動贏取連結的效能如何？
* 成效：應用程式的成效如何，以及使用者在哪些階段遭遇問題？
* 保留率：我的忠實使用者是哪些人，以及他們都進行什麼活動？
* 歷程：我應用程式中的顯著使用模式為何？

以下是「行動應用程式使用」範本的摘錄：

![行動應用程式使用情形](assets/mobile-app-usage.png)

若要存取範本：

1. 登入experience.adobe.com並選擇「分析」。
1. 請確定您位於已啟用Mobile Services的報表套裝中。
1. 按一下「工作區」標籤。
1. 按一下「建立新專案」。
1. 選取任何行動範本，然後按一下「建立」。

## 移轉其他Mobile Services功能

下列Mobile Services功能也與Adobe Analytics有關聯，但需要購買的Adobe Analytics SKU:

* 「贏取連結」
* 推送訊息
* 應用程式內傳訊
* 地點目標管理

如果您要運用Mobile Services來提供付費功能，則沒有可行的移轉路徑，無法移轉至其他內部／外部工具：

* 若是贏取連結，我們可以將您導向Adobe合作夥伴，以滿足您的需求。
* 雖然Adobe Campaign Standard和Adobe Campaign Classic中有推播訊息和應用程式內訊息的類型（僅限推播），但用於定位的基礎資料集不同，無法移轉資料或訊息活動。
* 針對位置功能，建議您採用全新 [Adobe Experience Platform Location Service](https://www.adobe.com/experience-platform/location-service.html)，此服務對所有AEP客戶都是免費的。
