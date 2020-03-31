---
title: trackingServer
description: 決定影像要求的傳送位置。
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# trackingServer

Adobe 會接收訪客產生的影像要求，藉此收集您網站上的資料。`trackingServer` 變數決定影像要求的傳送位置。如果此變數未正確定義，您的實施可能會遭遇資料遺失。

> [!IMPORTANT] 變更此值會導致 AppMeasurement 在不同位置尋找 Cookie。由於訪客 Cookie 會設定在新的位置，報表中的獨特訪客計數可能會暫時激增。

## Adobe Experience Platform Launch 中的追蹤伺服器

Tracking Server is a field under the [!UICONTROL General] accordion when configuring the Adobe Analytics extension.

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. 展開accordion [!UICONTROL General] ，以顯示欄 [!UICONTROL Tracking Server] 位。

如果此欄位留空，其預設值為 `[rsid].112.2o7.net`。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.trackingServer

`s.trackingServer` 變數是包含資料傳送位置的字串。

> [!TIP] 有些實施會將資料指向 `2o7.net`。雖然這是有效的資料彙集網域，不過此網域不會使用區域資料彙集。使用 `2o7.net` 的實施會出現略高的影像要求回應時間。

## 決定 trackingServer 的值

此變數的值取決於您是使用第一方 Cookie 或第三方 Cookie。Adobe 強烈建議您在實施中使用第一方 Cookie。

### 第一方 Cookie

如果您使用第一方 Cookie 實施，貴組織中可能已經有人完成第一方 Cookie 處理。如需第一方 Cookie 處理的詳細資訊，請參閱「核心服務」使用指南中的 [Experience Cloud 中的第一方 Cookie](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)。

最初設定第一方 Cookie 實施的個人，也會定義使用的網域和子網域。例如：

```js
s.trackingServer = "data.example.com";
```

CNAME 記錄通常已設定，並且指向 `sc.omtrdc.net`。網域 `2o7.net` 也是有效的 CNAME 目的地，主要用於舊版 Adobe Analytics。

### 第三方 Cookie

> [!TIP] 近代瀏覽器中逐漸增強的隱私權實務會降低第三方 Cookie 的可靠性。Adobe 建議您遵循第一方 Cookie 工作流程。

如果您使用第三方 Cookie 實施，`trackingServer` 的值為 `sc.omtrdc.net` 的子網域。例如：

```js
s.trackingServer = "example.sc.omtrdc.net";
```

挑選貴組織專屬的子網域，也就是其他使用 Adobe Analytics 之組織不太可能挑選的子網域。確定貴組織的所有實施都使用相同的追蹤伺服器。在[解決方案設計文件](../../prepare/solution-design.md)中維護這些資訊會是比較實用的方法。

> [!NOTE] 請勿使用深於的子網域 `example.sc.omtrdc.net`。 例如，不 `custom.example.sc.omtrdc.net` 是有效的追蹤伺服器。
