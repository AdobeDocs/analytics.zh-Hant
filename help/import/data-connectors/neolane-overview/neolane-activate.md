---
description: 使用 Adobe Data Connectors 設定精靈來設定整合。
title: 啟用整合
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
exl-id: d36c26ad-09c4-4a4d-a653-670c18f2ab19
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 96%

---

# 啟用整合{#activate-the-integration}

使用 Adobe Data Connectors 設定精靈來設定整合。

1. 啟動 [ Data Connectors ](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html)，然後按一下&#x200B;**[!UICONTROL 「+ 新增」]**&#x200B;以[新增整合](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/getting-started-data-connectors.html)。
1. 在&#x200B;**[!UICONTROL 「顯示」]**&#x200B;清單中，選取&#x200B;**[!UICONTROL 「依名稱」]**，並將[!DNL ~合作夥伴~]整合拖曳至空的外掛程式插槽。
1. 使用下表中的資訊完成整合精靈：

| 欄位 | 說明 |
|--- |--- |
| 報表套裝 | 從這項整合接收資料的報表套裝。 |
| 整合名稱 | 指定 Data Connectors 在報表套裝的「作用中的整合清單」中顯示的整合名稱。 |
| 已點按 | 電子郵件點按總次數。 |
| 行銷活動 ID | 儲存不重複訊息 ID。此項通常會儲存在促銷活動變數中。 |
| 已開啟 | 已開啟電子郵件總數。 |
| 人員點按次數 | 已點按人數。 |
| 已處理 | 已處理電子郵件的總數。 |
| Broadlog ID | 此 ID 是來自 Neolane 系統之電子郵件地址的編碼或數值表示。此「Broadlog ID」與網站上的下游訪客行為 (放棄購買、購買等) 相關聯，此項目會被拉入 Neolane 系統，且可用於再行銷用途。 |
| 已排程 | 已排程待傳送的電子郵件訊息數。 |
| 已傳送 | 已傳送的電子郵件訊息數。 |
| 總跳出數 | 由於傳遞問題而未傳遞給收件者的電子郵件訊息數目。 |
| 不重複點按次數 | 不同點按的次數。 |
| 不重複開啟次數 | 不同開啟的次數。 |
| 已取消訂閱 | 開啟了電子郵件訊息，但接著按一下「取消訂閱」連結以選擇退出貴組織未來電子郵件訊息的訪客數。 |
| 區段 | 這項整合會建立顯示在「合作夥伴區段」部分中的合作夥伴定義區段。此外，您可以選取要納入整合中的現有報表套裝層級區段。 |
| 存取要求 | 啟用建議的存取權限。 |
| 資料彙集 | 如果您想要使用 s_code.js 外掛程式做為此整合的收集模式，請選取 **JavaScript 外掛程式**。如果您想要針對這項整合使用自動化收集模型，請選取&#x200B;**「自動化解決方案」**，然後指定用於這項整合的唯一識別碼。如果您選取此選項，請指定用於這項整合的唯一識別碼： <ul><li>訊息 ID 查詢字串參數：此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的訊息 ID。</li><li>收件者 ID 查詢字串參數：此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的收件者 ID。</li></ul> |
| 產生控制面板和書籤 | 針對整合自動產生控制面板和書籤。 |
