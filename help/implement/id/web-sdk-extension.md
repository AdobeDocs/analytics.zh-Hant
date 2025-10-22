---
title: 使用網頁SDK標籤擴充功能識別訪客
description: 實作網頁SDK標籤擴充功能時，正確識別訪客。
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# 使用網頁SDK標籤擴充功能識別訪客

Adobe Experience Platform Data Collection中的Web SDK標籤擴充功能可讓組織使用標籤管理介面實施Web SDK。 您可透過擴充功能規則和動作，輕鬆設定跨網域ID共用和訪客設定檔移轉等進階案例。 使用Web SDK可驗證您的實作，並支援順暢升級至Customer Journey Analytics。

身分資料可以延伸，以使用XDM的`identityMap`支援自訂ID和多個名稱空間。 Adobe建議使用Adobe Experience Cloud ID Service做為Analytics的主要識別碼，並針對進階案例使用其他識別管理選項。

由於訪客ID服務是以原生方式內建至標籤擴充功能，因此您只需將&#x200B;**[!UICONTROL Edge網域]**&#x200B;設定為所要的值。 如果此欄位設定正確，訪客身分識別無需任何其他設定即可運作。

>[!NOTE]
>
>如果使用Web SDK標籤擴充功能，請勿包含訪客ID服務標籤擴充功能。 只有在您使用[Adobe Analytics擴充功能](analytics-extension.md)時，才需要訪客ID服務標籤擴充功能。
