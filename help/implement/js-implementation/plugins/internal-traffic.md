---
title: 內部流量
description: 內部流量外掛程式會動態識別源自於內部網路的訪客。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 內部流量

內部流量外掛程式會動態識別源自於內部網路的訪客。

識別內部和外部流量可提供篩選和區隔收集到的資料的機制，藉此促進提升所有類型的報表作業的正確性。若正確地實作，也就不需要 VISTA 規則或處理規則，這些是識別此類流量的一般方法。

## 內部流量外掛程式如何運作?

外掛程式會嘗試載入只能在內部網路中取得的檔案，亦即 1x1 透明像素。若成功載入，則會將該訪客的流量識別為內部。任何其他流量均會識別為外部流量。

## 考量事項

* 此方法的唯一缺點是，在外部訪客瀏覽的第一個頁面上，其瀏覽器控制台會顯示 404 錯誤。這不會影響使用者體驗。
* 強烈建議您在嘗試載入內部託管像素前，先取得網路或 InfoSec 團隊的核准。
* 雖然外掛程式不會將流量移轉至其他報表套裝或將其從報表中排除 (VISTA 規則可能就會這麼做)，但可將自訂邏輯包含在其實施中，讓此功能在用戶端進行。

## 實施

1. 新增內部網路像素: 您可以在外掛程式嘗試存取之內部網路上新增任何類型的檔案。建議使用 1x1 透明像素。此像素應放置在可從內部網路廣泛存取的內部網路上的位置。
1. 設定 eVar: eVar 必須在目標報表套裝內新增。您應將過期設定為「造訪」，並將配置設定為「原始值 (第一個)」。
1. 定義內部 URL: 在 AppMeasurement 設定變數內以及在具現化 doPlugins 前，請定義可用於流量檢查的像素或其他檔案的內部 URL 變數 (s.intURL)。例如︰`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. 修改 doPlugins 並設定 eVar: 接著，您可使用步驟一所定義的 eVar，將這一行程式碼加入 AppMeasurement 程式庫程式碼的 doPlugins 區段內，藉此初始化外掛程式: `s.eVarXX = s.intCheck();`
變數值將設為「內部」或「外部」。
1. 新增外掛程式原始碼: 將外掛程式程式碼加入至 AppMeasurement 檔案的 doPlugins 區段下方。

## 外掛程式原始程式碼

將此程式碼新增至 AppMeasurement 程式庫的 doPlugins 區段下方。

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## 其他附註

* 在部署至生產環境前，請務必對外掛程式安裝進行測試，以確保資料收集可如預期發生。
* 您的實施可能會使用與預設 Adobe Analytics「s」物件不同的物件名稱。若是如此，請據以更新物件名稱。
* 若您使用標籤管理系統，請按照其步驟更新 doPlugins 和其他自訂外掛程式。
