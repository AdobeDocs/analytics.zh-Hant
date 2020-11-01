---
title: 設定跨裝置分析
description: 設定虛擬報表套裝以啟用 CDA。
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 91%

---


# 設定跨裝置分析

滿足所有必要條件後，請依照下列步驟啟用跨裝置分析。您必須屬於「產品設定檔管理員」群組，或在 Adobe Analytics 中擁有管理員權限，才能依照這些步驟操作。

>[!IMPORTANT]
>
>執行這些步驟之前，必須先滿足所有必要條件。如果未滿足所有必要條件，則無法使用該功能或無法順利運作。如需必要條件和限制，請參閱[概觀頁面](overview.md)及所需的彙整方法 (分別是[依欄位彙整](field-based-stitching.md)或[裝置圖表](device-graph.md))。

## 選擇要啟用 CDA 的跨裝置報表套裝

將貴組織佈建為使用 CDA 時，可以選擇要使用哪個報表套裝。您可透過 Adobe 客戶經理傳達此選擇。然後 Adobe 會啟用您選擇的報表套裝以進行 CDA 處理。

## 建立跨裝置虛擬報表套裝以查看跨裝置檢視

有權限建立虛擬報表套裝的管理員可依下列步驟建立 CDA 虛擬報表套裝：

1. 導覽至 [experiencecloud.adobe.com](https://experiencecloud.adobe.com) 並使用您的 AdobeID 憑證登入。
2. 按一下頂端的 9 格線圖示，然後按一下「Analytics」。
3. 將游標暫留在頂端的「元件」上，然後按一下「虛擬報表套裝」。
4. 按一下「新增」。
5. 輸入虛擬報表套裝的名稱，並確認選取已啟用 CDA 的報表套裝。
6. (選用) 將區段套用至虛擬報表套裝。例如，您可以套用區段來將虛擬報表套裝限制為開啟 CDA 功能及開始連結後的日期。此區段可讓使用者只看到 VRS 中已連結的日期範圍。
7. 按一下「啟用報表時間處理」核取方塊，啟用包括跨裝置分析在內的多個選項。
8. 按一下「連結跨裝置使用者造訪次數」核取方塊。
9. 按一下「繼續」，完成虛擬報表套裝的設定，然後按一下「儲存」。

![CDA 核取方塊](assets/cda-checkbox.png)

## 跨裝置虛擬報表套裝的新增和變更項目

為虛擬報表套裝啟用跨裝置分析時，請留意下列變更：

* 虛擬報表套裝名稱旁會出現新的跨裝置圖示。此圖示是跨裝置虛擬報表套裝的專屬圖示。
* A new dimension labeled [Identified state](../dimensions/identified-state.md) is available. 此維度會決定裝置圖形是否將即時得知該點擊上的 Experience Cloud ID。
* New metrics labeled [People](../metrics/people.md) and [Unique Devices](../metrics/unique-devices.md) are available.
* The metric [Unique Visitors](../metrics/unique-visitors.md) is not available, as it is replaced with &#39;People&#39; and &#39;Unique Devices&#39;.
* 建立區段時，「訪客」區段容器會被「人員」容器取代。
