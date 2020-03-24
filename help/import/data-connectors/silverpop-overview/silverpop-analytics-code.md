---
description: '如果您選取 JavaScript 外掛程式資料收集方法，請複製下列幾行程式碼，然後新增至您頁面上的 Analytics 程式碼中。 '
title: Analytics 外掛程式程式碼
uuid: 534874bd-49d9-4b15-8019-b503dfcf3182
translation-type: ht
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# Analytics 外掛程式程式碼{#analytics-plug-in-code}

如果您選取 JavaScript 外掛程式資料收集方法，請複製下列幾行程式碼，然後新增至您頁面上的 Analytics 程式碼中：

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

> [!NOTE] 上述外掛程式會假設某些自訂商務變數 (eVar) 可供使用。如果上述外掛程式中指定的變數在您的 Analytics 部署中不可使用，只需將其取代為可用的變數即可。
