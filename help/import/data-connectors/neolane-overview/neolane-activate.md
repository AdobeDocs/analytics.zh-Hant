---
description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-title: 啓動整合
title: 啓動整合
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 啓動整合{#activate-the-integration}

使用Adobe Data Connectors設定精靈來設定整合。

1. 啓動 [「資料連接器](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) 」並按一下 **[!UICONTROL 「新增」]** 以 [新增整合](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在 **[!UICONTROL 「顯示]** 」清單中，選取 **[!UICONTROL 「依名稱」]** 並將 [!DNL ~合作夥伴~] 整合拖曳至空白外掛程式槽。
1. 使用下表中的資訊完成整合精靈：

| 欄位 | 說明 |
|--- |--- |
| 報表套裝 | 接收此整合資料的報表套裝。 |
| 整合名稱 | 指定資料連接器在報表套裝的作用中整合清單中顯示的整合名稱。 |
| 點按 | 電子郵件點按總數。 |
| 行銷活動 ID | 儲存唯一訊息ID。這通常會儲存在促銷活動變數中。 |
| 已開啓 | 電子郵件開啓總次數。 |
| 人員點按次數 | 已點按的人數。 |
| 已處理 | 處理的電子郵件總數。 |
| Broadlog ID | 此ID是來自Neolane系統電子郵件地址的編碼或數字表示。此「Broadlog ID」與網站上下游訪客行為相關(購物車ID放棄、購買等)它會被提取到Neolane系統中，並可用來進行再行銷。 |
| 已排程 | 已排程進行傳送的電子郵件訊息數。 |
| 已傳送 | 傳送的電子郵件訊息數。 |
| 彈回數總計 | 由於傳送問題而未傳送給收件者的電子郵件訊息數量。 |
| 獨特點按次數 | 不同點按次數。 |
| 獨特開啓 | 獨特開啓次數。 |
| 取消訂閱 | 開啓電子郵件訊息，但接著按一下「取消訂閱」連結，即可選擇退出您組織未來電子郵件訊息的訪客數量。 |
| 區段 | 此整合會建立合作夥伴定義區段中顯示的合作夥伴定義區段。此外，您還可以選取要納入整合的現有報表套裝層級區段。 |
| 存取要求 | 啓用建議的存取權限。 |
| 資料彙集 | 如果您想要使用s_ code. js外掛程式做為此整合的系列模型，請選取 **JavaScript外掛程式** 。如果您想要針對此整合使用自動化收集模型，請選取 **「自動化解決方案** 」，然後指定用於此整合的唯一識別碼。如果您選取此選項，請指定用於此整合的唯一識別碼： <ul><li>訊息ID查詢字串參數：此值代表電子郵件合作夥伴附加給著陸頁面URL的訊息ID。</li><li>收件者ID查詢字串參數：此值代表電子郵件合作夥伴的「收件者ID」附加至著陸頁面URL。</li></ul> |
| 控制面板和書簽產生 | 自動產生整合的控制面板和書簽。 |