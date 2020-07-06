---
title: 具有 Experience Cloud ID 的訪客
description: 使用Adobe Experience Cloud ID服務的獨特訪客數。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# 具有 Experience Cloud ID 的訪客

「具有Experience Cloud ID的訪客」量度顯示Adobe使用 [Experience Cloud ID服務識別的獨特訪客數量](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)。 此維度有助於與「獨特訪客 [](unique-visitors.md) 」量度進行比較，以確保網站的大部份訪客都使用ID服務。 如果大部分訪客不使用ID服務Cookie，則可指出您實作中的問題。

>[!NOTE]
>
>如果您使用多個Experience Cloud服務（例如Adobe Target或Adobe Audience Manager），此度量對除錯特別重要。 跨Experience Cloud產品共用的區段不包括沒有Experience Cloud ID的訪客。

## 此度量的計算方式

此量度是以「獨特訪客」量度為基 [礎](unique-visitors.md) ，但僅包含使用查詢字串(根據 `mid`[`s_ecid`](https://docs.adobe.com/content/help/zh-Hant/core-services/interface/ec-cookies/cookies-analytics.html) Cookie)識別的個人。

## 除錯您的Experience Cloud ID設定

「具有Experience Cloud ID的訪客」量度可用於疑難排解Experience Cloud整合，或識別未部署ID服務的網站區域。

將「具有Experience Cloud ID的訪客」與「獨特訪客」並排拖曳以比較：

![獨特訪客比較](assets/metric-mcvid1.png)

在此範例中，請注意，每個頁面的「獨特訪客」數目與「具有Experience Cloud ID的訪客」相同。 但是，「獨特訪客」的總數卻大於「具有 Experience Cloud ID 的訪客」總數。您可以建立計 [算量度](../c-calcmetrics/cm-overview.md) ，以找出哪些頁面未設定ID服務。 您可以使用下列定義：

![計算量度定義](assets/metric-mcvid2.png)

將計算量度加入報表後，您便可為「頁面」報表排序，進而顯示沒有 MCID 的訪客最多頁面：

![無ID服務的頁面](assets/metric-mcvid3.png)

請注意，「產品快速檢視」維度值無法與Identity Service正確實作。 您可以與組織內的適當團隊合作，盡快更新這些頁面。 您可以使用任何類型的維度(例如瀏覽器類型、網站區 [段或任何](../dimensions/browser-type.md)eVar [)來建構類似的報表](../dimensions/site-section.md)[](../dimensions/evar.md)。
