---
description: 內部 URL 篩選器可識別您認為是屬於網站內部的反向連結。這可協助流量來源報表填入資料並協助篩選內部流量。
title: 內部 URL 篩選器
feature: 管理工具
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# 內部 URL 篩選器

**[!UICONTROL 「管理 > 報表套裝 > 編輯設定 > 一般 > 內部 URL 篩選器 > 新增篩選器」]**

內部 URL 篩選器可識別您認為是屬於網站內部的反向連結。這可協助流量來源報表填入資料並協助篩選內部流量。

反向連結或反向連結頁面通常是訪客進入您網站的頁面。若要避免造成資料偏差，您可以篩選掉內部反向連結。報告會從以下報告中排除已篩選的反向連結：[反向連結](/help/components/dimensions/referrer.md)維度、[反向連結網域](/help/components/dimensions/referring-domain.md)維度，以及其他流量來源維度。

流量來源報表未填入資料的最常見原因是未定義內部 URL 篩選器清單。若要查看報表套裝已設定哪些內部 URL 篩選器，請遵循下列步驟。若要避免此問題，請移除將句號 (.)列為篩選條件的規則，並新增您自己的網站。

將句號列為預設內部 URL 篩選器的原因是為了允許在頁面報表中收集資料。如果點擊不符合內部 URL 篩選器，所有頁面都會顯示為「其他」。URL 中一定會有句號，因此可保證一定會填入頁面報表。
