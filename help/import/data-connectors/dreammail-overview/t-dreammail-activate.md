---
description: 使用 Adobe Data Connectors 設定精靈來設定整合。
title: 啟用整合
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 啟用整合{#activate-the-integration}

使用 Adobe Data Connectors 設定精靈來設定整合。

1. 啟動 [ Data Connectors ](https://marketing.adobe.com/resources/help/zh_TW/genesis/c_overview.html)，然後按一下&#x200B;**[!UICONTROL 「+ 新增」]**&#x200B;以[新增整合](https://marketing.adobe.com/resources/help/zh_TW/genesis/t_add_integration.html)。
1. 在&#x200B;**[!UICONTROL 「顯示」]**&#x200B;清單中，選取&#x200B;**[!UICONTROL 「依名稱」]**，並將[!DNL ~合作夥伴~]整合拖曳至空的外掛程式插槽。
1. 使用下表中的資訊完成整合精靈：

| 欄位 | 說明 |
|--- |--- |
| 報表套裝 | 從這項整合接收資料的報表套裝。 |
| 整合名稱 | 指定 Data Connectors 在報表套裝的「作用中的整合清單」中顯示的整合名稱。 |
| 整合 UUID | 指定您的 DreamMail 整合 UUID。 |
| 用戶端名稱 | 指定您的 DreamMail 用戶端名稱。 |
| 網站名稱 | 指定您的 DreamMail 網站名稱。 |
| 退回 | 由於傳遞問題而未傳遞給收件者的電子郵件訊息數目。 |
| 已傳遞 | 成功傳遞訊息的次數。 |
| 傳遞錯誤 | 訊息傳遞失敗次數。 |
| HTML 開啟 | 開啟電子郵件訊息的訪客人數。 |
| 無效 | 無效的電子郵件地址數目。 |
| 促銷活動 | 行銷促銷活動 ID。 |
| 傳遞 | 「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 |
| Email eVar | DreamMail 系統的電子郵件地址。此「電子郵件 eVar」與網站上的下游訪客行為 (購物車放棄、購買等等) 相關聯這些資料會被提取至 DreamMail 系統中，並可用於再行銷目的。 |
| 焦點事件 | 可匯出至再行銷區段的事件。 |
| 焦點購買 | 可匯出至再行銷區段的事件。 |
| 焦點值 | 可匯出至再行銷區段的收入事件。 |
| 點按總次數 | 「已點按」事件可讓您查看已點按電子郵件訊息的訪客數。 |
| 區段 | 這項整合會建立顯示在「合作夥伴區段」部分中的合作夥伴定義區段。此外，您可以選取要納入整合中的現有報表套裝層級區段。 |
| 存取要求 | 啟用建議的存取權限。 |
| 資料彙集 | 如果您想要使用 s_code.js 外掛程式作為這項整合的收集模型，請選取&#x200B;**「JavaScript 外掛程式」**(請參閱)。如果您想要針對這項整合使用自動化收集模型，請選取&#x200B;**「自動化解決方案」**，然後指定用於這項整合的唯一識別碼。如果您選取此選項，請指定用於這項整合的唯一識別碼：<ul><li>訊息 ID 查詢字串參數：此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的訊息 ID。</li><li>收件者 ID 查詢字串參數：此值代表您的電子郵件合作夥伴附加至登陸頁面 URL 的收件者 ID。</li></ul> |
| 產生控制面板和書籤 | 針對整合自動產生控制面板和書籤。 |
