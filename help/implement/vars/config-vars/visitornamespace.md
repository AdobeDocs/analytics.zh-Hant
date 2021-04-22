---
title: visitorNameSpace
description: 決定 Cookie 網域的淘汰變數。
exl-id: 4fea35c0-9998-4438-a2ca-af65a35a449e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '213'
ht-degree: 100%

---

# visitorNamespace

>[!IMPORTANT]
>
>此變數已淘汰。請改用 [`trackingServer`](trackingserver.md)。

在舊版 Adobe Analytics 中，AppMeasurement 使用 `visitorNameSpace` 變數來協助判斷儲存訪客 Cookie 的 `2o7.net` 子網域。近代瀏覽器中逐漸增強的隱私權實務會降低協力廠商 Cookie 的可靠性。隨著 `trackingServer` 和 [`trackingServerSecure`](trackingserversecure.md) 變數的引入，您不再需要 `visitorNameSpace`。

>[!TIP]
>
> Adobe 建議您在網站上使用第一方 Cookie。第一方 Cookie 不使用此變數。

## Adobe Experience Platform Launch 中的訪客命名空間

[!UICONTROL 「訪客命名空間」]是在設定 Adobe Analytics 擴充功能時，於[!UICONTROL 「Cookie」]設定追蹤器下方的欄位。

1. 使用您的 AdobeID 憑證登入 [launch.adobe.com](https://launch.adobe.com)。
2. 按一下所需的屬性。
3. 前往[!UICONTROL 擴充功能]標籤，然後按一下 Adobe Analytics 底下的[!UICONTROL 「設定」]按鈕。
4. 展開[!UICONTROL 「Cookie」]設定追蹤器，如此可顯示[!UICONTROL 「訪客命名空間」]欄位。

Adobe 建議您不要使用此欄位。請改用 `trackingServer` 和 `trackingServerSecure`。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s.visitorNamespace

`s.visitorNamespace` 變數是字串，其中包含每個組織特有的獨特值。從舊版 Adobe Analytics 下載舊版 AppMeasurement 程式庫時，此獨特值會自動包含在內。除非 `trackingServer` 和 `trackingServerSecure` 未設定，否則目前的 AppMeasurement 程式庫不會使用此變數。

如果貴組織仍需要此變數，請挑選能代表貴組織的值。您可以將此值儲存在[解決方案設計文件](../../prepare/solution-design.md)中。

```js
// If trackingServer is not set, cookies are stored under example.112.2o7.net
s.visitorNameSpace = "example";
```
