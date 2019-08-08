---
description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-title: 啓動整合
title: 啓動整合
uuid: 0a5d2d45-5133-4259-96ce-c992 a1 e314 ee
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 啓動整合 {#activate-the-integration}

使用Adobe Data Connectors設定精靈來設定整合。

1. 啓動 [「資料連接器](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) 」並按一下 **[!UICONTROL 「新增」]** 以 [新增整合](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)。
1. 在 **[!UICONTROL 「顯示]** 」清單中，選取 **[!UICONTROL 「依名稱」]** 並將 [!DNL ~合作夥伴~] 整合拖曳至空白外掛程式槽。
1. 使用下表中的資訊完成整合精靈：

| 欄位 | 說明 |
|--- |--- |
| 報表套裝 | 接收此整合資料的報表套裝。 |
| 整合名稱 | 指定資料連接器在報表套裝的作用中整合清單中顯示的整合名稱。 |
| 帳戶ID | 指定您的Aprimo帳戶ID。 |
| Recipient ID | 此ID是由Aprimo系統的電子郵件地址編碼或數值表示。此「收件者ID」與網站收件者ID(購物車放棄、購買等)上下游訪客行為相關聯。它會被提取到Aprimo系統中，並可用來進行再行銷。 |
| 點按 | (必要)指定Adobe Analytics事件，以儲存從電子郵件系統匯入的點按資料。點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 |
| 訊息ID | (必要)儲存唯一的郵寄ID。 |
| 已開啓 | (必要)指定Adobe Analytics事件，該事件儲存從電子郵件系統匯入的已開啓資料。「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 |
| Recipient ID | (必要)儲存唯一訪客ID。 |
| 已傳送 | (必要)指定Adobe Analytics事件，該事件儲存從電子郵件系統匯入的傳送資料。「傳送」事件可讓您查看傳送的電子郵件訊息數目。 |
| 彈回數 | (必要)指定Adobe Analytics事件，儲存從電子郵件系統匯入的電子郵件總彈回數。「總計」事件可讓您查看由於傳送問題而未傳送給收件者的電子郵件訊息數量。 |
| 取消訂閱 | (必要)指定儲存從電子郵件系統匯入的「取消訂閱」資料電子郵件的Adobe Analytics事件。「取消訂閱」事件可讓您查看開啓電子郵件訊息但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 |
| 區段 | 此整合會建立合作夥伴定義區段中顯示的合作夥伴定義區段。此外，您還可以選取要納入整合的現有報表套裝層級區段。 |
| 存取要求 | 啓用建議的存取權限。 |
| 資料彙集 | 如果您想要使用s_ code. js外掛程式做為此整合的系列模型，請選取 **JavaScript外掛程式** 。 |
如果您想要針對此整合使用自動化收集模型，請選取 **「自動化解決方案** 」，然後指定用於此整合的唯一識別碼。如果您選取此選項，請指定用於此整合的唯一識別碼：
<ul><li>訊息ID查詢字串參數：此值代表電子郵件合作夥伴附加給著陸頁面URL的訊息ID。</li>
<li>收件者ID查詢字串參數：此值代表電子郵件合作夥伴的「收件者ID」附加至著陸頁面URL。</li></ul>|
|儀表板書簽產生|自動產生整合的控制面板和書簽。|
