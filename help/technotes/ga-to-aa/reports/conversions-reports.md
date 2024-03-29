---
title: Adobe Analytics 中的轉換報表
description: 瞭解如何在 Adobe Analytics 中使用轉換報表。
feature: Third-party Integration
exl-id: 315b7dc0-1cd9-4beb-8203-88e205375f84
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 100%

---

# 轉換報表

「轉換」是訪客在您網站上執行的動作，可直接轉譯為貴組織的關鍵指標。轉換報表會顯示訪客轉換方式的詳細資訊。

本頁假設使用者具備使用 Analysis Workspace 的基本知識。如果您尚不熟悉 Adobe Analytics 中的工具，請參閱[在 Analysis Workspace 中建立基本報表 (Google Analytics 使用者適用)](create-report.md)。

## 目標報表

Google Analytics 使用者可透過目標來定義網站的轉換。目標是建立漏斗、反向行為流量、多管道漏斗和歸因的預設方式。Google Analytics 中的目標不具可回溯性，且只能在管理頁面上設定。此外，它們僅以頁面、事件、逗留時間或平均頁數為基礎。

在 Adobe Analytics 中，目標的概念並非必要，因為量度可以套用在任何情境中。只要您的實施符合您要追蹤的事件，您就可以調整任何轉換報表，並立即取得歷史資料的結果。

### 漏斗視覺效果

漏斗視覺效果報表可協助分析人員專注在轉換時所需的一系列特定步驟。例如，在進行購買之前，電子商務網站上的訪客需要存取購物車、帳單和運送頁面、付款頁面和訂單審核頁面。

在 Analysis Workspace 中，此資料可使用「流失」視覺效果來檢視。

1. 按一下左側的視覺效果圖示，然後將「流失」視覺效果拖曳至自由表格上方的工作區
2. 按一下左側的元件圖示，然後找出&#x200B;**頁面**&#x200B;維度。
3. 按一下「頁面」維度旁的箭頭圖示，即可顯示頁面值。維度項目是黃顏色。
4. 找出要當作第一個接觸點的頁面，並拖曳至視覺效果中標示為「新增接觸點」的空間。
5. 將頁面值拖曳至視覺效果上，繼續新增所需的接觸點。

「流失」視覺效果不僅限於「頁面」維度。任何維度、量度或區段都可用來量身打造您的流失報表，以符合貴組織的需求。

![流失視覺效果](/help/technotes/ga-to-aa/assets/fallout.png)

## 電子商務報表

銷售產品或服務的網站通常會使用電子商務報表，來測量購買項目的訂購作業和收入。Adobe Analytics 中提供此功能，稱為「產品」報表。

Google Analytics 中的電子商務報表和 Adobe Analytics 中的產品報表都需要自訂實施變更才能使用。如需詳細資訊，請參閱「元件」使用指南中的[產品](/help/components/dimensions/product.md)維度。

## 多管道漏斗報表

多管道漏斗報表提供的行銷管道資料超過贏取報表的範疇。這些報表著重於訪客的轉換方式，而非訪客到達您網站的方式。

>[!NOTE]
>
> 在 Adobe Analytics 中使用多管道報表時，需要設定「行銷管道」和自訂實施，以採用產品變數和購買事件。如果您尚未針對報表套裝設定這些功能，Adobe 建議您與實施顧問合作。

### 多管道 - 輔助轉換

輔助轉換會顯示每個管道協助轉換的次數。在 Analysis Workspace 中，可以使用&#x200B;**訂購協助**&#x200B;量度。

1. 在「元件」功能表中找出&#x200B;**行銷管道**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由表格區域。
2. 將&#x200B;**訂購協助**&#x200B;量度拖曳至自動建立的&#x200B;**發生次數**&#x200B;量度標頭上，即可加以取代。如有需要，可將其他量度拖曳至工作區上。

### 多管道 - 最上層轉換路徑

最上層轉換路徑報表會顯示使用者在轉換前所採用的最上層管道路徑。Analysis Workspace 使用流量報表來視覺化最上層轉換路徑。

1. 按一下左側的「面板」圖示，並將「歸因」面板拖曳至自由表格上方。
2. 按一下左側的「元件」圖示，找出&#x200B;**行銷管道**&#x200B;維度，並將其拖曳至標示為「新增維度」的方塊。
3. 在「量度」(例如「訂購」) 下找出所需的轉換事件，並將其拖曳至標示為「新增量度」的方塊。請注意，「歸因」面板不支援計算量度。
4. 按一下「建立」。
5. 在產生的報表中，找出「管道流量」視覺效果。此流量顯示訪客在購買前所接觸的最上層路徑。

此流量視覺效果為互動式。按一下每個管道，以朝任一方向將流量展開。

![流量視覺效果](/help/technotes/ga-to-aa/assets/flow.png)

### 多管道 - 時間延遲

時間延遲報表會顯示訪客在您網站上轉換時所花費的時間 (以天數為單位)。在 Analysis Workspace 中，此資料可使用&#x200B;**首次購買間隔天數**&#x200B;維度。它僅適用於正確實施的購買事件。

1. 在「元件」功能表中，找出&#x200B;**首次購買間隔天數**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由表格區域。
2. 將所需的量度與自動建立的&#x200B;**發生次數**&#x200B;量度一併拖曳至工作區。如需瞭解如何取得各個量度的詳細資訊，請參閱[量度轉譯指南](common-metrics.md)。

Adobe 建議將此維度與&#x200B;**訂購**、**件數**&#x200B;或&#x200B;**收入**&#x200B;等量度搭配使用。

對於其他類型的轉換，包括自訂事件，可使用&#x200B;**事件之前時間**&#x200B;維度。它會顯示訪客在造訪期間觸發事件所花的時間，以分鐘為單位。

1. 在「元件」功能表中，找出&#x200B;**事件之前時間**&#x200B;維度，並將其拖曳至標示為「將維度放置在此處」的大型自由表格區域。
2. 將所需的量度與自動建立的&#x200B;**發生次數**&#x200B;量度一併拖曳至工作區。如需瞭解如何取得各個量度的詳細資訊，請參閱[量度轉譯指南](common-metrics.md)。

Adobe 建議將此維度與自訂事件或購買事件搭配使用。

### 多管道 - 路徑長度

路徑長度報表會顯示轉換事件前接觸的管道數。在 Analysis Workspace 中，「歸因」面板會將此資料包含在其中一個視覺效果中。

1. 按一下左側的「面板」圖示，並將「歸因」面板拖曳至自由表格上方
2. 按一下左側的「元件」圖示，找出&#x200B;**行銷管道**&#x200B;維度，並將其拖曳至標示為「新增維度」的方塊。
3. 在「量度」(例如「訂購」) 下找出所需的轉換事件，並將其拖曳至標示為「新增量度」的方塊。請注意，「歸因」面板不支援計算量度。
4. 按一下「建立」。
5. 在產生的報表中，找出「每個歷程的接觸點」視覺效果。此長條圖顯示訪客在購買前所接觸的管道數。
