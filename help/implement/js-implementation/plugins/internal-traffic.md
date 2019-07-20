---
title: 內部流量
description: 內部流量外掛程式可動態識別源自內部網路的訪客。
seo-description: 內部流量外掛程式
seo-title: 內部流量外掛程式
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 內部流量

內部流量外掛程式可動態識別源自內部網路的訪客。

識別內部和外部流量會提供一種機制，提供篩選和區段資料收集的機制，以提高所有報告類型的準確性。實施正確，也不需要VISTA規則或處理規則，也就是識別此類流量的典型方法。

## 內部流量外掛程式如何運作？

外掛程式嘗試載入只能在內部網路/內部網路中使用的檔案(例如1x透明像素)。如果成功載入，則該訪客的流量將被識別為內部。其他任何是外部流量。

## 考量事項

* 此方法唯一的缺點是，在瀏覽的第一頁上，瀏覽器主控台中會顯示404錯誤。這不會影響使用者體驗。
* 強烈建議您在嘗試載入內部代管像素之前，先取得網路或InfoSec團隊的核准。
* 雖然外掛程式不會將流量移動至另一個報表套裝或從報告中排除(如VISTA規則可能完成)，但自訂邏輯可隨其實施而納入，因此此功能可能會發生用戶端。

## 實施

1. 加入您的內部網路像素：您可以在內部網路上新增任何類型的檔案，外掛程式會嘗試存取。建議使用1x透明像素。它應放在您內部網路的位置中，可從內部網路存取。
1. 設定eVar：您必須在目的地報表套裝中新增eVar。「瀏覽」應到期並分配「原始值(第一個)」。
1. 定義內部URL：在AppMeasurement組態變數中以及在doPlugins初始化之前，定義像素或其他檔案的內部URL變數(s. inturl)，以用於流量檢查。例如︰`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to “internal” or “external”.
1. 新增外掛程式原始程式碼：在AppMeasurement檔案的doPlugins區段下方，加入外掛程式代碼。

## 外掛程式原始碼

將此程式碼新增至AppMeasurement程式庫的doPlugins區段下方。

```s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.

