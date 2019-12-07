---
description: 新版的 JavaScript AppMeasurement 已變更其外掛程式支援。
keywords: Analytics Implementation;appmeasurement;javascript;plugin;plug-in
subtopic: JavaScript AppMeasurement
title: AppMeasurement 外掛程式支援
topic: Developer and implementation
uuid: e048e16b-994a-4079-bde4-3faa3df8c96d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# AppMeasurement 外掛程式支援

JavaScript AppMeasurement 目前版本的外掛程式支援。

## 經過測試的外掛程式 {#section_48415FB895E6455FAC34B0B96DE6EBE7}

下列外掛程式已經過測試而證明可相容: 

* [s.abort 標幟](/help/implement/js-implementation/plugins/abort.md)
* [appendList](/help/implement/js-implementation/plugins/appendlist.md)
* [doPlugins 函數](/help/implement/js-implementation/plugins/function-doplugins.md)
* [getAndPersistValue](/help/implement/js-implementation/plugins/getandpersistvalue.md)
* [getDaysSinceLastVisit](/help/implement/js-implementation/plugins/getdayssincelastvisit.md)
* [getLoadTime](/help/implement/js-implementation/plugins/getloadtime.md)
* [getNewRepeat](/help/implement/js-implementation/plugins/getnewrepeat.md)
* [getPageVisibility](/help/implement/js-implementation/plugins/pagevisibility.md)
* [getPercentPageViewed](/help/implement/js-implementation/plugins/getpercentpageviewed.md)
* [getPreviousValue](/help/implement/js-implementation/plugins/getpreviousvalue.md)
* [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md)
* [getTimeParting](/help/implement/js-implementation/plugins/gettimeparting.md)
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
