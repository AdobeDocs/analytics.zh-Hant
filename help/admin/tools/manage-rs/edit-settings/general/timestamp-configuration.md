---
description: 在單一報表套裝中，結合時間戳記與非時間戳記資料。
title: 時間戳記設定
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 6%

---

# 時間戳記設定

&#39;[!UICONTROL 時間戳記設定]&#39;管理頁面可讓您為一個或多個報表套裝啟用&#x200B;**[!UICONTROL 選擇式時間戳記]**。 此設定可讓您將時間戳記與非時間戳記資料合併為單一報表套裝。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝]** > **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 可選時間戳記]**

## 目前時間戳記設定

本區段顯示所選報表套裝的目前時間戳記設定。 它可以是下列三個可能值之一：

* 不允許&#x200B;**時間戳記（設定`visitorID`支援）**
* **需要時間戳記（不支援設定`visitorID`）**
* **可選時間戳記（設定`visitorID`受支援，但不在時間戳記點選上）**

此文字下方是一個標示為&#x200B;**[!UICONTROL 將選取的報表套裝轉換為可選時間戳記]**&#x200B;的核取方塊。 選取此核取方塊，然後選取&#x200B;**[!UICONTROL 儲存]**&#x200B;為選取的報表套裝啟用[!UICONTROL 選擇式時間戳記]。

## 不允許的時間戳記

當您使用此時間戳記設定將資料傳送至報表套裝時，時間戳記即為Adobe的處理伺服器收到點選的時間。 如果您嘗試設定[`timestamp`](/help/implement/vars/page-vars/timestamp.md)變數，則會永久捨棄點選。

## 需要時間戳記

當您使用此時間戳記設定將資料傳送至報表套裝時，每次點選都必須包含[`timestamp`](/help/implement/vars/page-vars/timestamp.md)變數。 如果任何點選遺失`timestamp`實作變數，則會永久捨棄該點選。

啟動時間戳記的作業資料最多可保留 92 日。換言之，造訪將「持續開放」92天，可在同一次造訪/工作階段中包含任何其他點選。 雖然您可以將資料新增至現有工作階段，但Adobe建議依每個訪客的順序新增點選。 個別訪客非依序收到的點選可能會產生非預期的報表結果，不過許多限制可透過報表時間處理來緩解。

## 可選時間戳記

&#39;[!UICONTROL 可選時間戳記]&#39;設定可讓您在多個報表套裝間進行整合與報告，無論是否有[`timestamp`](/help/implement/vars/page-vars/timestamp.md)變數。 [!UICONTROL 可選時間戳記]的理想使用案例包括：

* 在相同的全域報告套裝中，混搭時間戳記與非時間戳記資料
* 從行動應用程式傳送時間戳記資料至全域報表套裝
* 升級應用程式即可使用離線追蹤，無需建立新的報表套裝

所有新報表套裝都會預設啟用這項設定，除非新報表套裝複製自具有不同時間戳記組態設定的報表套裝。

>[!WARNING]
>
>如果您使用[!UICONTROL 可選時間戳記]，請勿在時間戳記資料上設定[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。 此動作可能會導致資料順序錯亂，並影響時間計算（例如逗留時間）、歸因、造訪次數/造訪計數，以及路徑報表。

啟用[!UICONTROL 可選時間戳記]後，您就無法在此介面中停用它。 萬一您希望切換回其他時間戳記設定時，請聯絡Adobe客戶服務。
