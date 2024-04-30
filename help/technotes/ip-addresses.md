---
title: Adobe Analytics 使用的 IP 和網域
description: 如果貴組織的防火牆封鎖來自 Adobe 的 IP 位址，請使用此清單來更新您的防火牆設定。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# Adobe Analytics 使用的 IP 和網域

有些防火牆設定會封鎖Adobe Analytics賴以取得產品介面的網域。 您可以使用此網域清單來變更組織的網路設定，以允許從組織內部存取產品。

## 允許相關技術網域

Adobe Analytics 會使用下列主機來改善效能和產品體驗。Adobe建議允許這些網域通過貴組織的防火牆，以獲得使用Adobe Analytics的最佳體驗。

| 技術 | 網域 |
| --- | --- |
| Adobe Analytics 網域 | `adobe.com`、`adobe.net`、`adobe.io` |
| Adobe Analytics 舊網域 | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`、`esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft Azure Blob 儲存體 | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Adobe Experience Cloud IP位址區塊

除了上述網域外，Adobe Analytics還仰賴數個IP位址區塊來收集資料和匯出報表。

如需IP範圍的完整清單，請參閱Adobe Experience Cloud IP位址。

## 中國效能最佳化IP位址

中國效能最佳化附加元件套件是額外的付費服務，可改善中國境內訪客的AppMeasurement資料收集效能。 請聯絡您的Adobe客戶團隊，以進一步瞭解使用此功能。

>[!IMPORTANT]
>
>中國RDC不適用於Web SDK資料收集。 這些伺服器僅適用於AppMeasurement程式庫。

中國的地區資料收集伺服器會使用下列IP位址：

| 位置 | 主機 |
| --- | --- |
| 中國 | `52.80.168.159` |
| 中國 | `52.80.199.104` |
| 中國 | `54.223.199.8` |

{style="table-layout:auto"}
