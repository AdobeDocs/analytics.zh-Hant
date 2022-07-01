---
title: 追蹤選擇退出原因
description: 預覽啟用「隱私設定」後將排除哪些資料。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# 追蹤選擇退出原因

*此頁指的是維，通過該維可查看啟用某些報告套件設定對資料的潛在影響。 與 [Adobe Experience CloudID選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)。*

「跟蹤退出選擇原因」維用作在啟用「隱私設定」時將被排除的資料的預覽。 此維主要用於確定啟用後實施是否會受到負面影響 [隱私設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 在「報告套件設定」下。

如果尚未啟用隱私設定，則典型實施會查看此維下其總體報告套件通信量的1%或更少。 百分比高於所有通信量的1%表明存在潛在的實施問題，使AppMeasurement無法設定第一方cookie。

## 將資料填入此維度中

此維適用於所有尚未啟用的實現 [隱私設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html)。 如果您的組織已啟用 **[!UICONTROL 刪除已阻止所有Cookie的用戶]** 設定案頭和移動瀏覽器，此維不包含資料。

## 維度項目

維度項目包含 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`

* **案頭瀏覽器禁用Cookie**:訪問者使用案頭瀏覽器阻止Cookie, **[!UICONTROL 刪除在案頭瀏覽器上阻止所有Cookie的用戶]** 已禁用。
* **Cookie被移動瀏覽器禁用**:訪問者使用移動瀏覽器阻止Cookie, **[!UICONTROL 刪除在移動瀏覽器上阻止所有Cookie的用戶]** 已禁用。
