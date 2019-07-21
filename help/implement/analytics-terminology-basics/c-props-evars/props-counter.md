---
description: 計數器可儲存 (有時也可顯示) 特定事件或程序的發生次數。
keywords: Analytics實作；prop；s. prop；自訂流量；計數器
seo-description: 計數器可儲存 (有時也可顯示) 特定事件或程序的發生次數。
seo-title: 將prop當做計數器
solution: Analytics
title: 將prop當做計數器
topic: 開發人員和實施
uuid: ab83bd7e-10d9-49f9-b9 e7-c50397 e95 c17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 將prop當做計數器

計數器可儲存 (有時也可顯示) 特定事件或程序的發生次數。

您可以使用 prop 計算某個事件的發生次數。例如，您想要追蹤 Real Player 和 Windows Media Player 在您網站上的使用情形比較。每個頁面都包含[!UICONTROL 「貼上程式碼」]，您可以在此處檢視 [!UICONTROL s.prop] 變數。使用 [!UICONTROL s.prop]1 來追蹤播放器。為頁面 A 在 [!UICONTROL s.prop]1 中輸入一個值，以代表 Real Player。

```js
s.prop1="RealPlayer"
```

為頁面 B 在 [!UICONTROL s.prop]1 中輸入類似的值，以代表 Windows Media Playe，如下所示。

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

當訪客進入您的網站，並瀏覽包含 Real Player 或 Windows Media Player 的頁面時，[!DNL Analytics] 將可根據使用者瀏覽的頁面來劃分使用者。接著，[!UICONTROL 「自訂流量」]報表會顯示每個頁面的瀏覽數。

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. 例如，[!UICONTROL 「自訂流量」]報表可重新命名為「播放器類型報表」。

