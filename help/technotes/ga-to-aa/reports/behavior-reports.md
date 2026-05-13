---
title: Adobe Analytics 中的行為報表
description: 瞭解如何在 Adobe Analytics 中建立行為報表
feature: Third-party Integration
exl-id: ea441afa-e595-4ffa-b446-d67e87f8a7c9
TQID: https://experienceleague.adobe.com/pNdyXgcpZ9TWU2WFnXTlkDeeFv3exefKSJRF6CbB2Nc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: dcae653e-62c6-4cc8-84e6-ee110b848296id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 805
ht-degree: 95%

---

# 行為報表

行為報表會顯示使用者與您網站互動的相關資訊。

本頁假設使用者具備使用 Analysis Workspace 的基本知識。 如果您尚不熟悉 Adobe Analytics 中的工具，請參閱[在 Analysis Workspace 中建立基本報表 (Google Analytics 使用者適用)](create-report.md)。

## 行為流量

行為流量報表可使用「流量」視覺效果重新建立。

1. 按一下左側的視覺效果圖示，然後將「流量」視覺效果拖曳至自由格式表格上方的工作區
2. 找出&#x200B;**頁面**&#x200B;維度，然後按一下「箭頭」圖示以顯示頁面值。 維度項目是黃顏色。
3. 找出所需的頁面值，並將其拖曳至中心標示為「維度或項目」的空格中
4. 此流量報告為互動式。 按一下任何值，即可將流量展開至接續或先前的頁面。 使用右鍵功能表來展開或收合欄。 同一流量報告中也可使用不同的維度。

![流量報表](/help/technotes/ga-to-aa/assets/flow.png)

## 網站內容 - 所有頁面

頁面報表會顯示您網站上個別頁面的效能。

1. 在「元件」功能表中，找出&#x200B;**頁面**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由格式表格區域。
2. 將所需的量度與自動建立的&#x200B;**發生次數**&#x200B;量度一併拖曳至工作區。 如需瞭解如何取得各個量度的詳細資訊，請參閱[量度轉譯指南](common-metrics.md)。

另外，Adobe 提供數個預先建立的工作區，稱為範本。 「內容使用 (網頁)」範本提供與所有頁面報表類似的值。

1. 按一下&#x200B;*[!UICONTROL 專案] > [!UICONTROL 新增]*，以開啟包含專案選項的模組視窗。
2. 按一下「內容使用 (網頁)」範本，然後按一下「建立」。

## 網站內容 - 內容深入分析

內容深入分析報表可讓您依 URL 結構來檢視頁面流量。 Analysis Workspace 中需要額外實施。 Adobe 建議您與實施顧問合作，以確保準確收集這些資料。

## 網站內容 - 登陸頁面

登陸頁面報表會顯示您網站上最上層的登陸頁面。 在 Analysis Workspace 中，登陸頁面是以&#x200B;**登入頁面**&#x200B;維度的形式提供。

1. 在「元件」功能表中，找出&#x200B;**登入頁面**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由格式表格區域。
2. 將所需的量度與自動建立的&#x200B;**發生次數**&#x200B;量度一併拖曳至工作區。 如需瞭解如何取得各個量度的詳細資訊，請參閱[量度轉譯指南](common-metrics.md)。

Adobe 建議對此維度使用&#x200B;**造訪**&#x200B;量度。

## 網站內容 - 退出頁面

退出頁面報表會顯示成為個別使用者造訪最後一頁的最上層頁面。 在 Analysis Workspace 中，它以相同名稱提供。

1. 在「元件」功能表中，找出&#x200B;**退出頁面**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由格式表格區域。
2. 將所需的量度與自動建立的&#x200B;**發生次數**&#x200B;量度一併拖曳至工作區。 如需瞭解如何取得各個量度的詳細資訊，請參閱[量度轉譯指南](common-metrics.md)。

Adobe 建議對此維度使用&#x200B;**造訪**&#x200B;量度。

## 網站速度報表

網站速度報表會顯示頁面載入的速度，顯示增加頁面載入時間的機會。

這項功能需要在這兩種平台上進行額外的實施；Adobe 建議您與實施顧問合作，以確保此資料已針對 Analysis Workspace 正確設定。 通常會將 [getPageLoadTime 外掛程式](/help/implement/vars/plugins/getpageloadtime.md)指派給 eVar，以在 Adobe Analytics 中取得效能資料。

## 網站搜尋報表

網站搜尋報告可提供訪客如何使用您網站內部搜尋功能的洞察。

這項功能需要在這兩種平台上進行額外的實施；Adobe 建議您與實施顧問合作，以確保此資料已針對 Analysis Workspace 正確設定。 通常，內部搜尋詞會從查詢字串參數中提取，並放入 eVar 中進行報表。

## 事件報表

在 Google 和 Adobe Analytics 之間，「事件」有一些重大的結構差異。 這兩種「事件」都需要進行額外的實施變更，才能在各自的平台上正常運作。

* 在 Google Analytics 中，事件在您的實施中定義為文字。 事件擁有類別、動作和標籤。
* 在 Adobe Analytics 中，事件會先在 Admin Console 中設定，並在其中指派識別碼。 該識別碼用於實施程式碼。 例如：
   1. 您可以在 Admin Console 中將 event1 設為「註冊」。
   2. 在您的實施中，您會在註冊確認頁面上的事件變數中包含 event1。 每次顯示註冊確認頁面時，event1 都會增加。
   3. 在 Analysis Workspace 中，「註冊」會以量度的形式顯示，以供任何報表使用。

因為這項功能需要進行實施變更；Adobe 建議您與實施顧問合作，以確保資料已針對 Analysis Workspace 正確設定。

## 發佈者報表

與Google需要連線Google Ad Manager類似， Adobe提供專門的產品來提供insight，稱為Adobe Advertising。 如果您的組織有興趣使用本產品，請聯絡您的Adobe客戶團隊。
