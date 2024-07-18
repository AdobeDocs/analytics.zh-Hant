---
title: 廣告平台同意
description: 請參閱第三方廣告提供者的廣告同意設定。
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
source-git-commit: 5df5cffbb6abf712cb36fd807ef54b8ebaae1c73
workflow-type: tm+mt
source-wordcount: '331'
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

Adobe Analytics當您透過Adobe Advertising將廣告資料作為轉換事件傳送到Google時，請洽詢Adobe Advertising團隊以協助整合。

如需詳細資訊，請參閱[隱私權報告](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)。
