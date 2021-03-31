---
description: 在 Activity Map 中安裝、設定和使用功能的常問的問題。
title: Activity Map 常見問題集
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
feature: Activity Map
role: 業務從業人員、管理員
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 25%

---


# Activity Map 常見問題集

在 Activity Map 中安裝、設定和使用功能的常問的問題。

## 所有Analytics客戶都可以存取「管理工具ActivityMap啟用」頁面嗎？

擁有Adobe Analytics Standard、Premium和Ultimate合約的組織可以存取Activity Map。

## Activity Map是否提供「檢視」資料？

否，Adobe不會追蹤已檢視的連結。

## Activity Map支援哪些瀏覽器和版本？

Activity Map支援最新版最新的瀏覽器。

## Activity Map是否會增加伺服器呼叫？

Activity Map本身不會傳送伺服器呼叫。 Activity Map上下文資料變數會隨後頁面上的Analytics頁面檢視呼叫而包含。

## 為什麼缺少某些排名項目覆蓋？**

有些排名連結（例如子功能表連結）會隱藏在頁面中。 因此，不會顯示其對應的連結覆蓋。 會計算頁面上所有連結的排名，包括隱藏的連結。

## 如何在「所有連結」報表中決定連結排名？**

* **在漸層和氣泡模式中**:排名由量度欄決定。對於具有相同量度值的連結，再進一步根據連結 ID 的字母順序來排名。
* **在「Gainer &amp; Loser」模式下**:排名主要由「增益%」欄決定。對於具有相同增益的連結，排名會進一步根據連結ID的字母順序。

## Activity Map如何處理使用多個報表套裝的頁面？

依預設，Activity Map會使用與頁面所傳送之第一個標籤相關聯的報表套裝。 但您可透過「**[!UICONTROL Activity Map 設定]** > **[!UICONTROL 其他]**」索引標籤，選取其他已標記報表套裝。

## Activity Map在網頁上掃描Adobe Analytics多久了？

Activity Map會在頁面完成事件後，掃描Adobe Analytics是否存在長達20秒。

## Activity Map如何處理動態內容？

Activity Map每2秒檢查一次，以查看它是否在網頁狀態中發現變更，例如：

* HTML 內容變成可見
* HTML 內容變成隱藏
* 插入新的 HTML 內容

如果內容變成隱藏或顯示，應用程式會自動將受影響的連結狀態 (以及覆蓋圖) 從隱藏變更為顯示，或從顯示變更為隱藏。如果插入新內容，應用程式會擷取相關連結、擷取其分析資料，並新增這些連結的覆蓋圖。

## 「頁面流量」報表以什麼度量為基礎？

所有顯示的資料都以頁面檢視為基礎。

## 我是否可透過資料饋送匯出Activity Map上下文資料變數？

資料饋送中無法使用Activity Map上下文資料變數。

## 區段是否可在即時模式中運作？

否，區段無法在即時模式中運作。 此功能等同於「報告與分析」中不支援區段的即時報告。

## Activity Map是否與虛擬報表套裝相容？

可以。不過，由於虛擬報表套裝本身限制，Activity Map 的即時模式與虛擬報表套裝不相容。
