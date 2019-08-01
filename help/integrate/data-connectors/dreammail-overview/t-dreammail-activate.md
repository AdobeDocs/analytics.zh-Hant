---
description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-title: 啓動整合
title: 啓動整合
uuid: 9084b691-291d-49f7-1fa4-abda507 e060 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration{#activate-the-integration}

使用Adobe Data Connectors設定精靈來設定整合。

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. 使用下表中的資訊完成整合精靈：

| 欄位 | 說明 |
|--- |--- |
| 報表套裝 | 接收此整合資料的報表套裝。 |
| 整合名稱 | 指定資料連接器在報表套裝的作用中整合清單中顯示的整合名稱。 |
| 整合UUID | 指定您的DREAMmail整合UUID。 |
| 用戶端名稱 | 指定您的DREAMmail用戶端名稱。 |
| 網站名稱 | 指定您的DREAMmail網站名稱。 |
| 反彈回溯 | 由於傳送問題而未傳送給收件者的電子郵件訊息數量。 |
| 遞送內容 | 成功傳送訊息的次數。 |
| 傳送錯誤 | 未成功傳送訊息。 |
| HTML開啓 | 開啓電子郵件訊息的訪客人數。 |
| Invalid | 無效的電子郵件地址數。 |
| 促銷活動 | 行銷活動ID。 |
| Pass Age | 點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 |
| Email eVar | DREAMmail系統的電子郵件地址。此「電子郵件eVar」與網站上下游訪客行為(購物車放棄、購買等)關聯它會被提取到DREAMmail系統中，並可用來進行再行銷。 |
| 精選事件 | 可在重新行銷區段中匯出的事件。 |
| 精選購買 | 可在重新行銷區段中匯出的事件。 |
| 精選值 | 可在重新行銷區段中匯出的收入事件。 |
| totalClicks | 點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 |
| 區段 | 此整合會建立合作夥伴定義區段中顯示的合作夥伴定義區段。此外，您還可以選取要納入整合的現有報表套裝層級區段。 |
| 存取要求 | 啓用建議的存取權限。 |
| 資料彙集 | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration (see ). Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. 如果您選取此選項，請指定用於此整合的唯一識別碼：<ul><li>訊息ID查詢字串參數：此值代表電子郵件合作夥伴附加給著陸頁面URL的訊息ID。</li><li>收件者ID查詢字串參數：此值代表電子郵件合作夥伴的「收件者ID」附加至著陸頁面URL。</li></ul> |
| 控制面板和書簽產生 | 自動產生整合的控制面板和書簽。 |