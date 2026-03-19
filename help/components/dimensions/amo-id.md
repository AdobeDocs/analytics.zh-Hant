---
title: AMO ID
description: Adobe Media Optimizer ID，用於Adobe Advertising整合。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 3%

---

# AMO ID

**[!UICONTROL AMO ID]**&#x200B;是用於Adobe Advertising整合中的串連識別碼集合。 儲存在此維度中的值會自動組織為個別、更人類看得懂的分類維度，以用於Analytics報表。 啟用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)整合時，會自動建立維度。

## 將資料填入此維度中

此維度會以多種方式收集其值：

* 針對點進流量，資料會從`s_kwcid`頁面URL[中的](page-url.md)查詢字串引數收集，通常是在廣告驅動流量進入網站的頁面上。
* 當URL不包含追蹤程式碼，但Adobe Advertising JavaScript在前兩分鐘內偵測到點選時，也可擷取點進流量。
* 對於支援的檢視流量，Adobe Advertising會使用補充ID (`SDID`)補充後端上的值。

## 維度項目

Dimension專案包含AMO ID，也稱為`s_kwcid`值。 確切的格式取決於流量是來自DSP還是來自搜尋、社交和Commerce。 AMO ID的精細度不如EF ID，主要用於Analytics中的分類與內嵌Adobe Advertising量度。

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**：表示顯示頻道。
* **`ad key`**： Adobe Advertising產生的廣告英數字元識別碼。
* **`placement key`**：位置的Adobe Advertising產生的英數字元識別碼。

範例值：

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### 搜尋、社交和Commerce廣告

搜尋、社交和Commerce AMO ID的開頭為`AL`，後面接著廣告商使用者ID、廣告網路帳戶ID，然後是網路特定識別碼。 共用的廣告網路帳戶ID包括：

* **`3`**： Google Ads
* **`10`**： Microsoft Advertising
* **`45`**： Meta
* **`86`**： Yahoo！ 顯示網路
* **`87`**：導覽
* **`88`**：百度
* **`90`**： Yandex
* **`94`**： Yahoo！ 日本廣告
* **`105`**： Yahoo Native （已棄用）
* **`106`**： Pinterest （已棄用）

#### Google Ads

Google Ads使用兩種相關格式。 較新的帳戶可以包含行銷活動ID和廣告群組ID，這支援最高績效和草稿/實驗行銷活動的行銷活動和廣告群組層級報告。

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**： Google Ads創意ID。
* **`matchtype`**：關鍵字元合型別（`e`表示完全符合，`p`表示片語，`b`表示廣泛）。
* **`placement`**：廣告被點按的網域。
* **`network`**：發生點選的網路（`g`用於Google搜尋，`s`用於搜尋夥伴，`d`用於顯示）。
* **`product partition`**：產品廣告的產品群組識別碼。
* **`keyword`**：在搜尋網站上觸發關鍵字，或在內容網站上最佳比對關鍵字。
* **`campaign id`**：Google Ads促銷活動ID （若存在）。
* **`ad group id`**：Google Ads廣告群組ID （如果存在）。

對於動態搜尋廣告，關鍵字欄位會填入自動鎖定目標。

範例：

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### Microsoft Advertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**： Microsoft Advertising創意ID。
* **`keyword/order item id`**： Microsoft Advertising關鍵字識別碼。
* **`campaign id`**： Microsoft Advertising行銷活動ID。
* **`ad group id`**： Microsoft Advertising廣告群組識別碼。

部分未移轉的帳戶仍可保留舊版Microsoft格式。

範例：

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### 百度

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**：百度創意ID。
* **`placement`**：廣告被點按的網站。
* **`keyword id`**：百度關鍵字識別碼。

#### Yahoo! 日本廣告

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**： Yahoo！ Japan Ads創意ID。
* **`matchtype`**：關鍵字元合型別（`be`個精確，`bp`個片語，`bb`廣泛）。
* **`network`**：發生點選的網路（`n`原生，`s`搜尋）。
* **`keyword`**：正在觸發關鍵字。

#### Yandex

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**： Yandex創作ID。
* **`source type`**：顯示廣告的網站型別（`b`搜尋、`c`內容/內容、`ct`類別）。
* **`phrase id`**： Yandex關鍵字識別碼。

## 分類

啟用[Analytics for Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview)整合時，會自動建立下列分類。 整合會自動維護分類值。

| 分類 | 說明 | DSP | 搜尋，<br>社交， &amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL 帳戶]** | 帳戶名稱。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 廣告顯示URL]** | 廣告中顯示的URL。 | | &amp;amp；檢查； |
| **[!UICONTROL 廣告說明]** | 廣告說明(DSP)或廣告內文（搜尋、社交和Commerce）。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 廣告目的地URL]** | 廣告的目的地URL。 | | &amp;amp；檢查； |
| **[!UICONTROL 廣告群組]** | 廣告群組名稱。 | | &amp;amp；檢查； |
| **[!UICONTROL 廣告平台]** | 廣告DSP或搜尋引擎名稱。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 廣告標題]** | 廣告型別(DSP)或廣告標題（搜尋、社交和Commerce）。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 廣告型別]** | 廣告型別，例如`text`、`video`、`display`或`native`。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL AdCloud屬性1]** -<br>**[!UICONTROL AdCloud屬性5 &#x200B;]** | 預留位置分類以供未來自訂屬性使用。 目前未使用。 | | |
| **[!UICONTROL Campaign]** | 行銷活動名稱。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL Creative體驗名稱]** | 和廣告互動相關聯的創意體驗名稱，代表測試或個人化中使用的一組創意變體。 | &amp;amp；檢查； | |
| **[!UICONTROL Creative分支名稱]** | 創意體驗中的分支名稱，代表創意實驗中的特定變數或路徑。 | &amp;amp；檢查； | |
| **[!UICONTROL Creative分支ID]** | 指派給創意體驗中創意分支的唯一識別碼。 | &amp;amp；檢查； | |
| **[!UICONTROL Creative名稱]** | 提供給使用者的特定廣告創意資產名稱。 | &amp;amp；檢查； | |
| **[!UICONTROL Creative變體名稱]** | 在創意體驗或分支中使用的創意的特定變體名稱。 | &amp;amp；檢查； | |
| **[!UICONTROL 關鍵字]** | 關鍵字。 | | &amp;amp；檢查； |
| **[!UICONTROL 關鍵字元合型別]** | 關鍵字和相符型別。 | | &amp;amp；檢查； |
| **[!UICONTROL 登陸型別]** | 登入頁面專案是瀏覽還是點進。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 符合型別]** | 搜尋相符型別。 | | &amp;amp；檢查； |
| **[!UICONTROL 網路]** | RTB (DSP)或廣告網路名稱（搜尋、社交和Commerce）。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 最佳化]** | 套件名稱(DSP)或產品組合名稱（搜尋、社交和Commerce）。 | &amp;amp；檢查； | &amp;amp；檢查； |
| **[!UICONTROL 位置]** | 位置名稱。 | &amp;amp；檢查； | |
| **[!UICONTROL 產品目標]** | 產品清單廣告的產品目標。 | | &amp;amp；檢查； |
