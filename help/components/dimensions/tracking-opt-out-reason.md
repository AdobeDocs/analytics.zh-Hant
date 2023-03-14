---
title: 追蹤選擇退出原因
description: 預覽若您啟用「隱私權設定」，會排除哪些資料。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
source-git-commit: b7209b914695423099266f5c507eaa34c2b98bc5
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# 追蹤選擇退出原因

*此頁面會參考的維度，可讓您查看啟用某些報表套裝設定對資料可能造成的影響。 與 [Adobe Experience Cloud ID選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant).*

「追蹤選擇退出原因」維度可作為資料的預覽，若您啟用隱私權設定，則會排除這些資料。 此維度主要用來判斷若您已啟用，您的實作是否會受到負面影響 [隱私權設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html) 在「報表套裝設定」下。

若尚未啟用隱私權設定，一般實作會在此維度下看到其整體報表套裝流量的1%或以下。 高於所有流量1%的百分比表明可能會發生實施問題，使AppMeasurement無法設定第一方Cookie。

## 將資料填入此維度中

此維度可立即用於所有尚未啟用的實作 [隱私權設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html). 如果貴組織已啟用 **[!UICONTROL 移除已封鎖所有Cookie的使用者]** 針對案頭和行動瀏覽器進行設定時，此維度不會包含資料。

## 維度項目

維度項目包含 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`

* **案頭瀏覽器停用的Cookie**:訪客使用案頭瀏覽器封鎖Cookie，並 **[!UICONTROL 移除已封鎖案頭瀏覽器上所有Cookie的使用者]** 已停用。
* **行動瀏覽器停用的Cookie**:訪客使用行動瀏覽器封鎖Cookie，並 **[!UICONTROL 移除已封鎖行動瀏覽器上所有Cookie的使用者]** 已停用。
