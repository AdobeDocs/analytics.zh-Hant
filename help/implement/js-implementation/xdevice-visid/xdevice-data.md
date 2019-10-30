---
description: 概述在啟用跨裝置訪客身分識別後，您在報告中檢視的資料會受到哪些影響。
keywords: Analytics 實作
seo-description: 概述在啟用跨裝置訪客身分識別後，您在報告中檢視的資料會受到哪些影響。
seo-title: 跨裝置訪客身分識別對資料的影響
solution: Analytics
subtopic: 訪客
title: 跨裝置訪客身分識別對資料的影響
topic: 開發人員和實作
uuid: 1db4d149-cd50-4b41-a850-988901f25051
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# 跨裝置訪客身分識別對資料的影響

>[!IMPORTANT]
>
>不建議您繼續使用這種跨裝置識別訪客的方法。詳情請參閱[Adobe Experience Cloud Device Co-op 文件](https://marketing.adobe.com/resources/help/zh_TW/mcdc/)。

概述在啟用跨裝置訪客身分識別後，您在報告中檢視的資料會受到哪些影響。

若要瞭解此功能對資料收集有何影響，先瞭解訪客資料中的訪客資料欄位，會有所幫助: 

| 資料欄位 | 說明 |
|---|---|
| 訪客 ID Cookie | 在第一次從裝置或瀏覽器瀏覽時自動產生、並儲存在 `s_vi` Cookie 中的 ID。 |
| 訪客 ID 變數 | 使用 [!UICONTROL  變數設定的選用]訪客 ID`s.visitorID`。此值會在使用者進行驗證後填入，並且可能會符合您的公司用來在多個數位行銷管道間追蹤使用者的 ID。 |
| 有效訪客 ID | 有效[!UICONTROL 訪客 ID] 是使用者個人資料的實際 ID。此值會設為[!UICONTROL 訪客 ID] Cookie，或設為[!UICONTROL 訪客 ID] 變數 (若有提供)。 |

