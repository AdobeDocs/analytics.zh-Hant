---
description: 新版的 JavaScript AppMeasurement 已變更其外掛程式支援。
keywords: Analytics實作；appmeasurement；javascript；外掛程式；外掛程式
seo-description: 新版的 JavaScript AppMeasurement 已變更其外掛程式支援。
seo-title: AppMeasurement外掛程式支援
solution: Analytics
subtopic: JavaScript AppMeasurement
title: AppMeasurement外掛程式支援
topic: 開發人員和實施
uuid: e048e16b-994a-4079-bde4-3fa3 df3 c96 d
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# AppMeasurement外掛程式支援

目前版本JavaScript AppMeasurement中的外掛程式支援。

## 經過測試的外掛程式 {#section_48415FB895E6455FAC34B0B96DE6EBE7}

下列外掛程式已經過測試而證明可相容: 

* [s.abort 標幟](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md)
* [doPlugins函數](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](../../../implement/js-implementation/plugins/getdayssincelastvisit.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](../../../implement/js-implementation/plugins/getnewrepeat.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF)
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](../../../implement/js-implementation/plugins/gettimeparting.md#concept_3746EA1D1EF746049AE84105B911F44A)
* [getValOnce](/help/implement/js-implementation/plugins/getvalonce.md)
* [getVisitNum](/help/implement/js-implementation/plugins/getvisitnum.md)
* [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md)
* [hitGovernor](/help/implement/js-implementation/plugins/hitgovernor.md)
* [內部流量](/help/implement/js-implementation/plugins/internal-traffic.md)
* [效能計時](/help/implement/js-implementation/plugins/performancetiming.md)
* [trackTNT](/help/implement/js-implementation/plugins/tracktnt.md)

## 未經測試的外掛程式 {#section_32BA7CAB37554A278170A728F1D65CE9}

下列外掛程式應可繼續運作，因為其基礎功能仍受支援，但外掛程式本身未經過測試而證明可相容。在移轉之前，您應先在開發環境中測試這些外掛程式。

* getActionDepth
* getCookiesAccepted
