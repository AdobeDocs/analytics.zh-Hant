---
title: 廣告平台同意
description: 請參閱第三方廣告提供者的廣告同意設定。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 342
ht-degree: 3%

---

# 廣告平台同意

「廣告平台同意」 [維度](overview.md)會顯示是否收集同意資料，以傳送資料給第三方廣告提供者，例如Google、Meta等。

此維度目前僅用於Google。 由於歐洲的隱私權法規，數位市場法(DMA)要求Google傳送至其伺服器並在歐洲收集的資料必須指出是否獲得同意。 部分Analytics客戶會透過Adobe Advertising將事件資料當作轉換事件傳送至Google。

未來，此維度可用於支援其他協力廠商廣告提供者的其他同意資訊編碼。

## 將資料填入此維度中

此維度會從下列[內容資料變數](/help/implement/vars/page-vars/contextdata.md)收集資料

* `contextData.['adConsent']`

您可以使用Google同意欄位的相關值填入內容資料變數

* `ad_user_data` （第1個字元）和
* `ad_personalization` （第二個字元）。

如需詳細資訊，請參閱Google Ads API參考中的[同意](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent)。

每個欄位可能的值可以是：

| 值 | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | 針對廣告使用者資料授與Google的同意。 | 授與Google的同意以進行廣告個人化。 |
| `N` | 拒絕同意使用Google的廣告使用者資料。 | 同意使用Google進行廣告個人化。 |
| `U` | 未指定。 | 未指定。 |

下列範例會針對廣告使用者資料授予Google的同意，但不針對廣告個人化授予：

```
contextData.['adConsent'] = "YN..."
```

目前會忽略第一個和第二個字元以外的字元。

## 使用資料

您可以使用收集的廣告同意資料：

* 資料摘要：廣告同意資料可使用`dataprivacydmaconsent` [欄](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md)取得。
* Data Warehouse報告：可以使用&#x200B;**[!UICONTROL 廣告平台同意]**&#x200B;維度取得廣告同意資料。

您的組織會決定實作此內容資料變數的邏輯。 值在其設定所在的點選過後即不存在，因此您必須在每個頁面上設定內容資料變數。

當您透過Adobe Advertising將廣告資料作為轉換事件傳送到Google時，請洽詢Adobe Analytics團隊以協助整合。

如需詳細資訊，請參閱[隱私權報告](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md)。
