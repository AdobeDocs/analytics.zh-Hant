---
title: 追蹤選擇退出原因
description: 預覽啟用「隱私權設定」後會排除的資料。
feature: Dimensions
exl-id: f0521f4f-b11e-4ce3-b0fe-60788be6b120
TQID: https://experienceleague.adobe.com/mFYYrj4iBWBi87sErHnWTYXce3lUhV0pwUt63x3vfnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 13%
---
# 追蹤選擇退出原因

>[!BEGINSHADEBOX]

*此頁面參考[維度](overview.md)，可讓您檢視啟用某些報表套裝設定所造成的潛在資料影響。 它與[Adobe Experience Cloud ID選擇加入服務](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=zh-Hant)無關。*

>[!ENDSHADEBOX]

「追蹤選擇退出原因」維度可做為資料的預覽，但若您啟用「隱私權設定」則會排除這些資料。 此維度主要用來判斷若您在「報表套裝設定」下啟用「[隱私設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=zh-Hant)」，您的實施是否會受到負面影響。

如果尚未啟用隱私權設定，一般實施會在此維度下看到其整體報表套裝流量的1%或以下。 所有流量中高於1%的百分比表示AppMeasurement可能發生實作問題，而無法設定第一方Cookie。

## 將資料填入此維度中

此維度可立即用於尚未啟用[隱私權設定](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/browser-cookie-settings.html?lang=zh-Hant)的所有實作。 如果您的組織已啟用&#x200B;**[!UICONTROL 移除已封鎖案頭和行動瀏覽器之所有Cookie]**&#x200B;設定的使用者，則此維度不包含資料。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（立即可用；沒有變數可設定） |
| **網頁SDK / XDM欄位** | 無 |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含 `"Cookies disabled by Desktop Browser"` 和 `"Cookies disabled by Mobile Browser"`

* **案頭瀏覽器已停用Cookie**：訪客使用案頭瀏覽器封鎖了Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖案頭瀏覽器上所有Cookie的使用者]**。
* **行動瀏覽器已停用Cookie**：訪客已使用行動瀏覽器封鎖Cookie，而且&#x200B;**[!UICONTROL 已停用移除已封鎖行動瀏覽器上所有Cookie的使用者]**。
