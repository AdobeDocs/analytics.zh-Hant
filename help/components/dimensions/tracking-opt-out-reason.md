---
title: 追蹤選擇退出原因
description: 預覽啟用「隱私權設定」後會排除的資料。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---

# 追蹤選擇退出原因

*此頁面參考[維度](overview.md)，可讓您檢視啟用某些報表套裝設定所造成的潛在資料影響。 它與[Adobe Experience Cloud ID選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)無關。*

「追蹤選擇退出原因」維度可做為資料的預覽，但若您啟用「隱私權設定」則會排除這些資料。 此維度主要用來判斷若您在「報表套裝設定」下啟用「[隱私設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=zh-Hant)」，您的實施是否會受到負面影響。

如果尚未啟用隱私權設定，一般實施會在此維度下看到其整體報表套裝流量的1%或以下。 所有流量中高於1%的百分比表示AppMeasurement可能發生實作問題，而無法設定第一方Cookie。

## 將資料填入此維度中

此維度可立即用於尚未啟用[隱私權設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=zh-Hant)的所有實作。 如果您的組織已啟用&#x200B;**[!UICONTROL 移除已封鎖案頭和行動瀏覽器之所有Cookie]**&#x200B;設定的使用者，則此維度不包含資料。

## 維度項目

維度項目包含 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`

* **案頭瀏覽器已停用Cookie**：訪客使用案頭瀏覽器封鎖了Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖案頭瀏覽器上所有Cookie的使用者]**。
* **行動瀏覽器已停用Cookie**：訪客已使用行動瀏覽器封鎖Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖行動瀏覽器上所有Cookie的使用者]**。
