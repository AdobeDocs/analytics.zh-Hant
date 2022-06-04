---
title: 使用Adobe Experience PlatformWeb SDK實施Adobe Analytics
description: 使用Adobe Experience Platform資料收集中的Web SDK擴展將資料發送到Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 33%

---


# 使用Adobe Experience PlatformWeb SDK實施Adobe Analytics

您可以使用 [Adobe Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html) 向Adobe Analytics發送資料。 該實現方法通過翻譯 [體驗資料模型(XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) 格式。

## 設定

若要將 Analytics 設定為可接受 XDM 資料：

1. 安裝及[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html)。

1. 確保將適用的報告套件映射到所需的資料。 XDM資料自動從Adobe Experience Edge流到報表套件。
