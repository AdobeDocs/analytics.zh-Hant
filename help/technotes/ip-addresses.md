---
title: Adobe Analytics使用的IP位址
description: 如果貴組織的防火牆封鎖來自 Adobe 的 IP 位址，請使用此清單來更新您的防火牆設定。
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 35%

---

# Adobe Analytics使用的IP位址

有些防火牆設定會封鎖來自 Adobe 的資料收集伺服器或負責存取資料的伺服器 IP 位址。 您可以使用此範圍清單來變更組織的防火牆設定，以允許存取並在組織內傳送資料。

除「中國效能最佳化」附加元件套件外，Adobe Analytics使用的所有IP位址都是Adobe Experience Cloud[使用的](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)IP位址的一部分。

## 中國效能最佳化IP位址

中國效能最佳化附加元件套件是額外的付費服務，可改善中國境內訪客的AppMeasurement資料收集效能。 請聯絡您的Adobe客戶團隊，以進一步瞭解使用此功能。

>[!IMPORTANT]
>
>中國RDC不適用於Web SDK資料收集。 這些伺服器僅適用於AppMeasurement資料庫。

中國的地區資料收集伺服器會使用下列IP位址：

| 位置 | 主機 |
| --- | --- |
| 中國 | `52.80.168.159` |
| 中國 | `52.80.199.104` |
| 中國 | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>Adobe Experience Cloud使用的[個IP位址](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>[Adobe Analytics使用的網域](domains.md)
