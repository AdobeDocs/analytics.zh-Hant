---
title: trackingServer
description: 確定傳送的位置影像要求。
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# trackingServer

Adobe會接收訪客產生的影像要求，以收集您網站上的資料。 變 `trackingServer` 數會決定傳送影像要求的位置。 如果此變數未正確定義，您的實作可能會遭遇資料遺失。

> [!IMPORTANT] 變更此值會讓AppMeasurement尋找不同位置的Cookie。 獨特訪客計數會隨著訪客Cookie設定在新位置，在報告中暫時尖峰。

## Adobe Experience Platform Launch中的追蹤伺服器

「追蹤伺服器」是設定Adobe Analytics擴充功能時， [!UICONTROL 「一般] 」accordion下方的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往「延伸 [!UICONTROL 模組] 」標籤，然後按一下「 [!UICONTROL Adobe Analytics] 」下的「設定」按鈕。
4. 展開「 [!UICONTROL 一般] 」accordion，以顯示「追 [!UICONTROL 蹤伺服器」欄位] 。

如果此欄位留空，則預設為 `[rsid].112.2o7.net`。

## AppMeasurement和Launch自訂代碼編輯器中的s.trackingServer

變 `s.trackingServer` 數是包含傳送資料位置的字串。

> [!TIP] 有些實作會將資料指向 `2o7.net`。 雖然這是有效的資料收集網域，但不使用區域資料收集。 使用的實 `2o7.net` 施會看到略高的影像要求回應時間。

## 判斷trackingServer的值

此變數的值取決於您是使用第一方Cookie或第三方Cookie。 Adobe強烈建議在實作中使用第一方Cookie。

### 第一方 Cookie

如果您使用第一方Cookie實作，您組織中的某人可能已完成第一方Cookie處理。 如需 [有關第一方Cookie程式的詳細資訊，請參閱核心服務使用指南中](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html) 「Experience cloud中的第一方Cookie」。

最初設定第一方Cookie實作的個人也會定義使用的網域和子網域。 例如:

```js
s.trackingServer = "data.example.com";
```

通常已設定CNAME記錄並指向 `sc.omtrdc.net`。 網域也 `2o7.net` 是有效的CNAME目的地，主要用於舊版Adobe Analytics。

### 協力廠商Cookie

> [!TIP] 在現代瀏覽器中增加隱私權實務會降低協力廠商Cookie的可靠性。 Adobe建議您遵循第一方Cookie工作流程。

如果您使用第三方Cookie實作，則值 `trackingServer` 為的子網域 `sc.omtrdc.net`。 例如:

```js
s.trackingServer = "example.sc.omtrdc.net";
```

挑選您組織專屬的子網域，不太可能由使用Adobe Analytics的其他組織挑選。 請確定您組織中的所有實施都使用相同的追蹤伺服器。 在解決方案設計檔案中保留這些資訊 [會很有幫助](../../prepare/solution-design.md)。
