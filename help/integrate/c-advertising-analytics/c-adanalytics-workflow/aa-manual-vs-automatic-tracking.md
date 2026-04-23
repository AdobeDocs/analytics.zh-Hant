---
description: Tracking type determines how the Adobe Analytics implementation tracks your search engine data. This tracking type is a required step to augment the Adobe Analytics data properly with search engine data.
title: Tracking Type
feature: Advertising Analytics
exl-id: 3e2ed26f-dfb2-43ea-8eb6-e332cd10fb29
source-git-commit: cbfe932eecf2e89d72b1aa373d723de4cf0af073
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 26%

---

# Tracking Type

Tracking type determines how the Adobe Analytics implementation tracks your search engine data. This tracking type is a required step to augment the Adobe Analytics data properly with search engine data.

<!--

Here is a video overview of how to implement the Advertising Analytics tracking template:

>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/ad-cloud/implementing-tracking-templates-into-search-engines)

-->

Two tracking modes are supported: [!UICONTROL Auto] and [!UICONTROL Manual].

## [!UICONTROL Auto] Tracking {#concept_C4C6107838C947CFBB7F4E0CB94264F0}

[!UICONTROL Auto] tracking lets the Adobe Advertising engine decide how the search engine data should be handled. Auto tracking is the simpler approach, but may not result in the best integrated dataset.

As a consequence, you need to check an acknowledgment checkbox when you select **[!UICONTROL Auto]** before you can save the account setting.

Note that to configure a search engine account with **[!UICONTROL Auto]** type, you are responsible for taking the following actions:

* `s_kwcid`引數和值已新增至帳戶中的帳戶追蹤範本或登陸頁面URL。 This parameter and value is inserted at the end of the URL. Additional action may be required on your part if your web server requires a certain `key=value` pair at the end of the URL. Or an update to support any new `key=value` pair in the URL. It is your responsibility to ensure that the added URL parameters persist correctly to the final landing page.
* 此外，關鍵字可作為 `s_kwcid` 值的一部分插入至登陸 URL 中。If they contain special characters or symbols, please confirm that your web server can support these characters. For example, a common special character is `+`, which is used in &quot;Broad Match Modified&quot; keywords.

>[!IMPORTANT]
>
>請進一步瞭解您是否應將 `s_kwcid` 參數新增至您的[內容安全性原則](https://experienceleague.adobe.com/en/docs/id-service/using/reference/csp)。

## Manual Tracking {#concept_87B28BA9E7F84BA5972F69E6F3482A33}

Manual tracking enables you to specify how the Advertising Analytics data integration process should treat the search engine data.

### Add Manual tracking to Google Account {#section_41C1EB1AEB034544A5BC291F53C05C67}

以下是需要新增至 Google 帳戶的字串。您需要將字串新增至帳戶使用的所有追蹤範本中。

>[!IMPORTANT]
>
>*`<Advertising Analytics ID>`* 值 (下文中的&#x200B;**粗體字**) 是通用值，**請務必替換為您專屬的帳戶 ID 字串**。You can get your specific account ID string from the account screen under the [!UICONTROL Tracking] section.

**活動的追蹤字串：**

```
s_kwcid=AL! 
<b><Advertising Analytics ID></b>!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

![Google](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/google-account.png)

各種追蹤範本格式的追蹤程式碼範例：

**`{lpurl}`**

```
{lpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**`{lpurl}`及其他 URL 參數**

```
{lpurl}?campaign=PPC&s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

**第三方 (DoubleClick)`{lpurl}`**

To ensure that the string persists through the redirect to the final landing page URL, you need to encode the string sufficiently:

* if the URL goes through a redirect, and
* is not using an &quot;unescapedlpurl&quot; value.


```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!3!{creative}!{matchtype}!{placement}!{network}!{product_partition_id}!{keyword}
```

### Add Manual tracking to Microsoft Advertising account {#section_094F8ACA493C4D65B1F54A695558EBF2}

The string that needs to be added to your Microsoft Advertising account is shown below. 您需要將字串新增至帳戶使用的所有最終 URL 尾碼中。

>[!IMPORTANT]
>
>_`<Advertising Analytics ID>`_值 (下文中的&#x200B;**粗體字**) 是通用值，**請務必替換為您專屬的帳戶 ID 字串**。You can get your specific account ID string from the account screen under the &quot;Tracking&quot; section.

**活動的追蹤字串：**

```
s_kwcid=AL!<Advertising Analytics ID>!10!{AdId}!{OrderItemId} 
```

![Add tracking code parameters](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/assets/bing-account.png)

各種最終 URL 尾碼格式的追蹤程式碼範例：

**{lpurl}**

```
{lpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**`{lpurl}`及其他 URL 參數**

```
{lpurl}?campaign=PPC&
s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方 (DoubleClick)`{unescapedlpurl}`**

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={unescapedlpurl}?s_kwcid=AL!9999!10!{AdId}!{OrderItemId}
```

**第三方 (DoubleClick)`{lpurl}`**

To ensure that the string persists through the redirect to the final landing page URL, you need to encode the string sufficiently:

* if the URL goes through a redirect, and
* is not using an &quot;unescapedlpurl&quot; value.

```
https://clickserve.dartsearch.net/link/click?{_dssagcrid}&{_dssftfiid}&ds_e_adid={creative}&ds_e_matchtype={ifsearch:search}{ifcontent:content}&ds_e_device={device}&ds_e_network={network}&{ifpla:ds_e_product_group_id={product_partition_id}&ds_e_product_id={product_id}&ds_e_product_merchant_id={merchant_id}&ds_e_product_country={product_country}&ds_e_product_language={product_language}&ds_e_product_channel={product_channel}&ds_e_product_store_id={product_store_id}}&ds_url_v=2&ds_dest_url={lpurl}?s_kwcid%3DAL!9999!10!{AdId}!{OrderItemId}
```
