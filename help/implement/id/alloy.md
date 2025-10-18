---
title: 使用網頁SDK JavaScript資料庫的訪客身分識別
description: 實作Web SDK JavaScript程式庫時正確識別訪客。
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 0%

---

# 使用網頁SDK JavaScript資料庫的訪客身分識別

Adobe Experience Platform Web SDK (`alloy.js`)為所有Adobe Experience Cloud應用程式（包括Analytics）提供統一、最新的資料收集方法。 身分資料可以延伸，以使用XDM的`identityMap`支援自訂ID和多個名稱空間。 Adobe建議使用Adobe Experience Cloud ID Service做為Analytics的主要識別碼，並針對進階案例使用其他識別管理選項。

如果您的組織使用Web SDK JavaScript資料庫將資料傳送至Adobe Analytics，訪客身分識別只需要最少的設定。 訪客ID服務是以原生方式內建至資料庫，僅需要您在&#x200B;**[!UICONTROL 命令中設定]** Edge網域`configure`。 如果此欄位設為所需值，訪客身分識別無需任何其他設定即可運作。
