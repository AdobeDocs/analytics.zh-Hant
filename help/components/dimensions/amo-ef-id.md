---
title: AMO EF ID
description: Adobe Media Optimizer EF ID，用於Adobe Advertising整合。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# AMO EF ID

**[!UICONTROL AMO EF ID]**&#x200B;是Adobe Advertising整合中使用的廣告點選識別碼。 這是Adobe Advertising用來將活動與訪客層級的線上點選或廣告曝光度建立關聯的唯一Token。 啟用[Analytics for Advertising](https://experienceleague.adobe.com/zh-hant/docs/advertising/integrations/analytics/overview)整合時，會自動建立維度。

## 將資料填入此維度中

此維度會以多種方式收集其值：

* 針對點進流量，資料會從`ef_id`頁面URL[中的](page-url.md)查詢字串引數收集，通常是在廣告驅動流量進入網站的頁面上。
* 當URL不包含追蹤程式碼，但Adobe Advertising JavaScript在前兩分鐘內偵測到點選時，也可擷取點進流量。
* 對於支援的檢視流量，Adobe Advertising會使用補充ID (`SDID`)補充後端上的值。

>[!NOTE]
>
>EF ID區分大小寫。 如果您的實施強制將URL追蹤轉換為小寫，則Adobe Advertising無法辨識EF ID。

## 維度項目

Dimension專案包含由支援的廣告網路產生的廣告點選識別碼。 字串格式取決於產生它的網路和頻道。

### Google Ads搜尋廣告

```text
{gclid}:G:{s}
```

* **`gclid`**： Google點按識別碼(GCLID)。
* **`s`**：網路型別（`"s"`用於搜尋）。

### Microsoft Advertising搜尋廣告

```text
{msclkid}:G:{s}
```

* **`msclkid`**： Microsoft點按識別碼(MSCLKID)。
* **`s`**：網路型別（`"s"`用於搜尋）。

### 在其他搜尋引擎上顯示廣告和搜尋廣告

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**： Adobe Advertising訪客ID，也稱為瀏覽者ID。
* **`ts`**： Adobe Advertising產生的時間戳記。
* **`channel`**：負責點選或曝光的管道型別：
   * **`d`**：按一下DSP顯示廣告（顯示點進）。
   * **`i`**： DSP顯示廣告（顯示閱覽）的曝光。
   * **`s`**：按一下搜尋廣告（搜尋點進）。

### 範例

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
