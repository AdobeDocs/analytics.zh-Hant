---
title: visitorNameSpace
description: 決定Cookie網域的已淘汰變數。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# visitorNamespace

> [!IMPORTANT] 此變數已停用。 請改 `trackingServer` 用。

在舊版Adobe Analytics中，AppMeasurement使用變 `visitorNameSpace` 數協助判斷訪客Cookie `2o7.net` 儲存位置的子網域。 在現代瀏覽器中增加隱私權實務會降低協力廠商Cookie的可靠性。 隨著和變數的 `trackingServer` 引 `trackingServerSecure` 入， `visitorNameSpace` 您不再需要。

> [!TIP] Adobe建議在您的網站上使用第一方Cookie。 第一方Cookie不會使用此變數。

## Adobe Experience Platform Launch中的訪客命名空間

[!UICONTROL 「訪客命名空間] 」是設定Adobe Analytics擴充功能時， [!UICONTROL Cookie] accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開 [!UICONTROL Cookies accordion] ，以顯示「訪客 [!UICONTROL 命名空間」欄位] 。

Adobe建議您不要使用此欄位。 請改 `trackingServer` 用 `trackingServerSecure` 和。

## AppMeasurement和Launch自訂代碼編輯器中的s.visitorNamespace

變 `s.visitorNamespace` 數是一個字串，每個組織包含唯一值。 從舊版Adobe Analytics下載時，舊版AppMeasurement程式庫會自動包含此唯一值。 目前的AppMeasurement程式庫不會使用此變數， `trackingServer` 除非 `trackingServerSecure` 未設定。

如果您的組織仍需要此變數，請選取代表您組織的值。 您可以將此值儲存在解決方案 [設計檔案中](../../prepare/solution-design.md)。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
