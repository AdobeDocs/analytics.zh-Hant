---
title: 設定 Cross-Device Analytics
description: 瞭解在您符合必要條件後如何設定跨裝置分析。
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# 設定 Cross-Device Analytics

> [!NOTE] 跨裝置分析檔案可能會隨著功能的進一步開發而變更。 請定期回訪以取得更新。

滿足所有必要條件後，請使用下列步驟來啟用跨裝置分析。 您必須屬於「產品設定檔管理員」群組，或在Adobe Analytics中擁有管理員權限，才能遵循這些步驟。

> [!IMPORTANT] 在執行這些步驟之前，必須滿足所有先決條件。 如果未滿足所有先決條件，則功能不可用或無法運作。 如需 [必要條件和限制](cda-home.md) ，請參閱跨裝置分析。

## 選擇將啟用CDA的跨裝置報表套裝

當您的組織被布建為使用CDA時，您可以選擇要使用哪個報表套裝。 您可透過Adobe客戶經理來傳達此選擇。 然後Adobe會啟用您選擇的報表套裝以進行CDA處理。

## Create a cross-device virtual report suite to see the cross-device view

Administrators with access to create virtual report suites can create CDA virtual report suites as follows:

1. 導覽至 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) ，並使用您的AdobeID認證登入。
2. Click the 9-grid icon at the top, then click Analytics.
3. Hover over Components at the top, then click Virtual Report Suites.
4. 按一下「新增」。
5. 輸入虛擬報表套裝的名稱，並確定已選取啟用CDA的報表套裝。
6. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
7. Click the checkbox 'Stitch User Visits Across Devices'.
8. 按一下「繼續」，完成虛擬報表套裝的設定，然後按一下「儲存」。

![CDA核取方塊](assets/cda-checkbox.png)

## Additions and changes to cross-device virtual report suites

在虛擬報表套裝上啟用「跨裝置分析」時，請注意下列變更：

* A new cross-device icon appears next to the virtual report suite name. 此圖示是跨裝置虛擬報表套裝的專屬圖示。
* 標示為「人員」和「獨特裝置」的新量度已推出。
* 「獨特訪客」量度不可用，因為它已取代為「人員」和「獨特裝置」。
* 建立區段時，「訪客」區段容器會以「人員」容器取代。

## The Compression calculated metric

跨裝置分析將裝置接合在一起的能力取決於各種因素。 使用稱為壓縮的計算量度來測量功能接合資料的效能。 造成壓縮的因素包括：

* 使用合作圖或私人圖：一般而言，使用裝置合作社的組織看到的壓縮率，會比使用私人圖表的組織好。
* 登入率：登入您網站的使用者越多，Adobe越能識別並將訪客連結到各種裝置上。 Sites with a low log in rate also have low compression rates.
* Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
* Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
* Reporting granularity: Compression by day is typically smaller than compression by month or year. 個人在一天內使用多種裝置的機率，會比整個月的機率小。 劃分、篩選或使用劃分維度也可以顯示較低的壓縮率。

To see your organization's compression for a given time period:

1. 按一下頂端的「工作區」，然後按一下「建立新專案」。
2. 從空白專案開始，然後按一下「建立」。
3. 將「獨特裝置」量度拖曳至標示為「拖曳量度到此處」的畫布區域。
4. 將「人員」量度直接拖曳至「獨特裝置」量度標題右側的畫布上，如此兩個量度便會並排。
5. 按一下左`+`側可用量度旁的''符號，以開啟計算量度產生器。
6. 為此計算量度提供下列設定：
   * 名稱：跨裝置壓縮
   * 格式：百分比
   * 小數位數：2
   * 定義: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] 按一下定義區域右上角的「新增」，新增靜態數字。 從左側可用度量清單中拖曳「人員」和「獨特裝置」。
7. 按一下「儲存」。
8. 將新的計算量度直接拖曳至「人物」量度標題右側的畫布上，因此這三個量度都是並排的。
9. 可選：工作區會依預設載入「日」維度。 如果需要不同的時間詳細程度，請將替代日期維度（例如周或月）拖曳至「日」維度之上。
