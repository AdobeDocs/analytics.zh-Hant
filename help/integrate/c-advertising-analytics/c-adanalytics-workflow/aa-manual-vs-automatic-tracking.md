---
description: 「追蹤」可決定 Adobe Analytics 實作追蹤搜尋引擎資料的方式。這是以搜尋引擎資料適度增加 Adobe Analytics 資料的必要步驟。
title: 追蹤手動模式和自動模式
uuid: c6ce7901-7b65-48b6-b65f-f29cc47b7454
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 追蹤：手動模式和自動模式

「追蹤」可決定 Adobe Analytics 實作追蹤搜尋引擎資料的方式。這是以搜尋引擎資料適度增加 Adobe Analytics 資料的必要步驟。

支援兩種追蹤模式：自動模式和手動模式。

## 自動模式追蹤 {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

在自動模式中，讓 Advertising Cloud 引擎決定如何處理搜尋引擎資料。這是比較簡單的方法，但可能不會產生最佳的整合資料集。

因此，在選取自動模式時，需要先勾選確認核取方塊，才能儲存帳戶設定。


請注意，若要在「自動模式」中設定搜尋引擎帳戶，您必須執行以下動作：

* 「S_kwcid」參數和值會新增至帳戶中的帳戶追蹤範本或登陸頁面 URL。參數和值會插入 URL 末端。如果您的網站伺服器在 URL 末端需要某個索引鍵/值組，或是需要更新以支援 URL 中的任何新索引鍵/值組，您可能需要執行額外的動作。**您還是必須負責確認新增的 URL 參數正確無誤，才能順利前往最終的登陸頁面。**
* 此外，關鍵字可以作為「S_kwcid」值的一部份，插入至登陸 URL 中。若關鍵字中包含特殊字元或符號，請確認您的網站伺服器可以支援這些字元。例如：常見的特殊字元為「+」，用於「加上廣泛比對修飾符」的關鍵字中。

## 手動模式追蹤{#concept_87B28BA9E7F84BA5972F69E6F3482A33}

在手動模式中，您需要指定 Advertising Analytics 資料整合程序該如何處置搜尋引擎資料。

### 將手動追蹤新增至 Google 帳戶 {#section_41C1EB1AEB034544A5BC291F53C05C67}

以下是需要新增至 Google 帳戶的字串。您需要將字串新增至帳戶使用的所有追蹤範本中。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 值 (下文中的&#x200B;**粗體字**) 是通用值，**請務必替換為您專屬的帳戶 ID 字串**。您可以在帳戶設定畫面的「追蹤」區段下方取得專屬的帳戶 ID。

**活動的追蹤字串：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![](assets/Google.png)

各種追蹤範本格式的追蹤程式碼範例：

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`及其他 URL 參數&#x200B;**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{lpurl}`**

如果 URL 需經過重新導向，而且未使用「unescapedlpurl」值，則您為字串編碼的次數必須夠多，使其能存留至完成重新導向，順利抵達最終的登陸頁面 URL。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### 將手動追蹤新增至 Bing 帳戶 {#section_094F8ACA493C4D65B1F54A695558EBF2}

以下是需要新增至 Bing 帳戶的字串。您需要將字串新增至帳戶使用的所有最終 URL 尾碼中。

>[!IMPORTANT]
>
>`<Advertising Analytics ID>` 值 (下文中的&#x200B;**粗體字**) 是通用值，**請務必替換為您專屬的帳戶 ID 字串**。您可以在帳戶設定畫面的「追蹤」區段下方取得專屬的帳戶 ID。

**活動的追蹤字串：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![](assets/Bing.png)

各種最終 URL 尾碼格式的追蹤程式碼範例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}`
```

**`{lpurl}`及其他 URL 參數&#x200B;**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方 (DoubleClick) `{unescapedlpurl}**

```https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}

```

**第三方 (DoubleClick)`{lpurl}`**

如果 URL 需經過重新導向，而且未使用「unescapedlpurl」值，則您為字串編碼的次數必須夠多，使其能存留至完成重新導向，順利抵達最終的登陸頁面 URL。

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
