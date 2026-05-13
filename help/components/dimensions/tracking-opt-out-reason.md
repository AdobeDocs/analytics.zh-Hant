---
title: 追蹤選擇退出原因
description: 預覽啟用「隱私權設定」後會排除的資料。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 281
ht-degree: 11%

---

# 追蹤選擇退出原因

*此頁面參考[維度](overview.md)，可讓您檢視啟用某些報表套裝設定所造成的潛在資料影響。 它與[Adobe Experience Cloud ID選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)無關。*

「追蹤選擇退出原因」維度可做為資料的預覽，但若您啟用「隱私權設定」則會排除這些資料。 此維度主要用來判斷若您在「報表套裝設定」下啟用「[隱私設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html)」，您的實施是否會受到負面影響。

如果尚未啟用隱私權設定，一般實施會在此維度下看到其整體報表套裝流量的1%或以下。 所有流量中高於1%的百分比表示AppMeasurement可能發生實作問題，而無法設定第一方Cookie。

## 將資料填入此維度中

此維度可立即用於尚未啟用[隱私權設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html)的所有實作。 如果您的組織已啟用&#x200B;**[!UICONTROL 移除已封鎖案頭和行動瀏覽器之所有Cookie]**&#x200B;設定的使用者，則此維度不包含資料。

## 維度項目

維度項目包含 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`

* **案頭瀏覽器已停用Cookie**：訪客使用案頭瀏覽器封鎖了Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖案頭瀏覽器上所有Cookie的使用者]**。
* **行動瀏覽器已停用Cookie**：訪客已使用行動瀏覽器封鎖Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖行動瀏覽器上所有Cookie的使用者]**。
