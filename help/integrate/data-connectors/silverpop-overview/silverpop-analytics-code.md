---
description: '如果您選取JavaScript外掛程式資料收集方法，請複製下列程式碼行並將其新增至頁面上的Analytics程式碼 '
seo-description: '如果您選取JavaScript外掛程式資料收集方法，請複製下列程式碼行並將其新增至頁面上的Analytics程式碼 '
seo-title: Analytics外掛程式程式碼
title: Analytics外掛程式程式碼
uuid: 534874bd-49d9-4b15-8019-b503 dfcf3182
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Plug-In Code{#analytics-plug-in-code}

如果您選取JavaScript外掛程式資料收集方法，請複製下列程式碼行並將其新增至頁面上的Analytics程式碼：

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>以上外掛程式假設某些自訂商務變數(eVar)已推出。如果上述增效模組中指定的變數無法在您的Analytics部署中使用，只需將其取代為可用的變數即可。

