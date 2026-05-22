---
title: 使用網頁SDK標籤擴充功能識別訪客
description: 實作網頁SDK標籤擴充功能時，正確識別訪客。
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 0%

---

# 使用網頁SDK標籤擴充功能識別訪客

Adobe Experience Platform Data Collection中的Web SDK標籤擴充功能可讓組織使用標籤管理介面實施Web SDK。 您可透過擴充功能規則和動作，輕鬆設定跨網域ID共用和訪客設定檔移轉等進階案例。 使用Web SDK可驗證您的實作，並支援順暢升級至Customer Journey Analytics。

身分資料可以延伸，以使用XDM的`identityMap`支援自訂ID和多個名稱空間。 Adobe建議使用Adobe Experience Cloud ID Service做為Analytics的主要識別碼，並針對進階案例使用其他識別管理選項。

由於訪客ID服務是以原生方式內建至標籤擴充功能，因此您只需將&#x200B;**[!UICONTROL Edge網域]**&#x200B;設定為所要的值。 如果此欄位設定正確，訪客身分識別無需任何其他設定即可運作。

>[!NOTE]
>
>如果使用Web SDK標籤擴充功能，請勿包含訪客ID服務標籤擴充功能。 只有在您使用[Adobe Analytics擴充功能](analytics-extension.md)時，才需要訪客ID服務標籤擴充功能。
