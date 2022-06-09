---
title: 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics
description: 在 Adobe Experience Platform 資料彙集中使用 Web SDK 擴充功能傳送資料給 Adobe Analytics。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: ht
source-wordcount: '142'
ht-degree: 100%

---


# 使用 Adobe Experience Platform Web SDK 實作 Adobe Analytics

您可以使用 [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=zh-Hant) 傳送資料給 Adobe Analytics。 此實作方法的運作方式是將[體驗資料模型 (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hant) 轉譯成 Analytics 所使用的格式。

## 設定

若要將 Analytics 設定為可接受 XDM 資料：

1. 安裝及[設定](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=zh-Hant) [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=zh-Hant)。

1. 確定適用的報表套裝已對應至您想要的資料。 XDM 資料會自動從 Adobe Experience Edge 流入報表套裝。
