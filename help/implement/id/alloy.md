---
title: 使用網頁SDK JavaScript資料庫的訪客身分識別
description: 實作Web SDK JavaScript程式庫時正確識別訪客。
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: 'https://experienceleague.adobe.com/k9u260HKJg6hhs7REAQ3-uE4pHvrUPBv6x8yLjZ5tvc'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 2%

---

# 使用網頁SDK JavaScript資料庫的訪客身分識別

Adobe Experience Platform Web SDK JavaScript資料庫(`alloy.js`)為所有Adobe CX Enterprise應用程式（包括Adobe Analytics）提供統一、最新的資料收集方法。 雖然大多數客戶通常會實作[Web SDK標籤擴充功能](web-sdk-extension.md)，但您可以自行或在協力廠商標籤管理系統中使用Web SDK JavaScript資料庫。 請參閱GitHub上的[Alloy](https://github.com/adobe/alloy)以下載最新版本的程式庫。

身分資料可以延伸，以使用XDM的[`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map)支援自訂ID和多個名稱空間。 Adobe建議使用ECID作為Analytics的主要識別碼，並針對進階案例使用其他識別管理選項。

如果您的組織使用Web SDK JavaScript資料庫將資料傳送至Adobe Analytics，訪客身分識別只需要最少的設定。 Experience Platform Identity Service是以原生方式內建至資料庫，僅需要您在`configure`命令中設定&#x200B;**[!UICONTROL Edge網域]**。 如果此欄位設為所需值，訪客身分識別無需任何其他設定即可運作。
