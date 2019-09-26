---
description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
keywords: Analytics 實作
seo-description: 動態變數可讓您直接在變數之間複製值，而無須在網站的影像請求中多次輸入完整值。
solution: null
title: 動態變數
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement]JavaScript 適用的 可動態選取其資料所要傳送到的報表套裝。 變數包含用來決定目標報表套裝的規則。

| 最大尺寸 | 偵錯器參數 | 填充報表 | 預設值 |
|---|---|---|---|
| 不適用 | 不適用 | 不適用 | "" |

此變數在使用時會搭配  和 *`dynamicAccountSelection`* 變 *`dynamicAccountMatch`* 數。 若將中 *`dynamicAccountList`* 的規則設 *`dynamicAccountSelection`* 為'true'，則會套用至中指定之URL的區段 *`dynamicAccountMatch`*。

如果中的任何規則都 *`dynamicAccountList`* 不符合頁面的URL，則會使用中識別的報 `s_account` 表套裝。 此變數中所列的規則會以由左至右的順序套用。若頁面 URL 符合多個規則，則會使用最左側的規則來決定報表套裝。因此，您應將較通用的規則移至清單的右側。

在下列範例中，頁面URL是 `www.mycompany.com/path1/?prod_id=12345` 且 `dynamicAccountSelection` 設為 *true* , `s_account` 且設為 `mysuitecom.`

| DynamicAccountList 值 | DynamicAccountMatch 值 | 要接收資料的報表套裝 |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1、mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom、mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## 語法和可能的值

 此`dynamicAccountList` 變數是以分號分隔的「名稱=值」配對 (規則) 清單。清單中的每一項均應包含下項目: 

* 一或多個報表套裝 ID (以逗號分隔)
* 一個等號
* 一或多個 URL 篩選器 (以逗號分隔)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

字串中只應使用標準 ASCII 字元 (無空格)。

## 範例

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## 組態設定

無

## 缺陷、問題和提示

* 動態帳戶選擇不受下列項目支援: [JavaScript 適用的 AppMeasurement](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* 若頁面 URL 符合多項規則，將會使用最左側的規則。
* 若沒有相符的規則，則會使用預設報表套裝。
* 若您的頁面儲存至某人的硬碟，或透過網頁型翻譯引擎進行翻譯 (例如 Google 的翻譯頁面)，可能將無法使用動態帳戶選項。如需更精確的追蹤，請在伺服器端填入 `s_account` 變數。
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* 使用動態帳戶選擇時，請務必在每次 *`dynamicAccountList`* 取得新網域時更新。
* Use the [!DNL DigitalPulse Debugger] when trying to identify the destination report suite. The `dynamicAccountSelection` variable always overrides the value of `s_account`.
