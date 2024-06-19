---
title: trackInlineStats
description: （已淘汰）在您的實施中啟用或停用ClickMap。
keywords: 停用clickmap
feature: Variables
exl-id: a52adc1d-1be7-4002-b393-7ce66332b483
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 30%

---

# trackInlineStats

>[!IMPORTANT]
>
>此變數已淘汰。另請參閱 [啟用Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md) 而非。

ClickMap是Adobe Analytics已淘汰的功能，可收集訪客點按位置及點按內容的資料。 功能已取代為 [Activity Map](/help/analyze/activity-map/activity-map.md).

啟用後，AppMeasurement 會收集連結的相關資訊，並在下一個影像要求中傳送該資料。每次點按的資訊都會儲存在標示為 `s_sq`.

## 使用Adobe Analytics擴充功能啟用ClickMap

[!UICONTROL 啟用ClickMap] 是底下的核取方塊 [!UICONTROL 連結追蹤] 設定Adobe Analytics擴充功能時的摺疊式功能表。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
4. 展開 [!UICONTROL 連結追蹤] 摺疊式功能表，可顯示 [!UICONTROL 啟用ClickMap] 核取方塊。

>[!NOTE]
>
>此核取方塊與 [!UICONTROL 使用Activity Map] 核取方塊，位於下方的 [!UICONTROL 程式庫管理] 摺疊式面板。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.trackInlineStats

此 `s.trackInlineStats` 是布林值，可啟用或停用ClickMap追蹤。 由於功能已淘汰，Adobe不建議設定此變數。 其預設值為 `false`。

```js
s.trackInlineStats = false;
```
