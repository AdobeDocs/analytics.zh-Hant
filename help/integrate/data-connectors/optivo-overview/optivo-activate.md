---
description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-description: 使用Adobe Data Connectors設定精靈來設定整合。
seo-title: 啓動整合
title: 啓動整合
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d10546972c03efae1bc365b7391000a40a79b0a4

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
| 電子郵件地址 | 提供電子郵件地址以接收整合相關資訊。 |
| 帳戶ID | 這是您的電子郵件服務提供者指派給您組織的唯一識別碼。請求電子郵件促銷活動資料時(例如# Sed、# Open、# Clicked等)並傳送訪客區段給您的電子郵件服務提供者。 |
| Recipient ID | 此ID是來自Optivo® Broadmail系統電子郵件地址的編碼或數字表示。此「收件者ID」與網站上下游訪客行為(購物車放棄、購買等)關聯它會提取到optivo® Broadmail系統中，並可運用於再行銷用途。 |
| 訊息ID | (必要)儲存唯一的郵寄ID。These classification dimensions are created by the Data Connectors wizard for the Message ID: a)**Campaigns**: Campaigns associated with the message. b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". c)**Country Code**: This field contains the country code of the origin sender country. 這是常數「DE」。d) **Delivery Tool**: Method of transmission, always "Email". e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. f) **Start Date**: Timestamp of the start of this mailing. |
| 貼文點擊時間 | (必要)當收件者按一下郵件中的連結後，需要這種方式將收件者動作的相關資訊傳送至optivo® Broadmail。 |
| 貼文點擊產品 | (必要)當收件者按一下郵件中的連結後，需要這種方式將收件者動作的相關資訊傳送至optivo® Broadmail。 |
| 貼文點擊動作 | (必要)當收件者按一下郵件中的連結後，需要這種方式將收件者動作的相關資訊傳送至optivo® Broadmail。 |
| 硬碟 | (必要)指定Adobe Analytics事件，儲存從電子郵件系統匯入的硬碟資料。未傳送給收件者且被視為永久無法傳送的電子郵件訊息數。 |
| 柔和反彈 | (必要)指定Adobe Analytics事件，以儲存從電子郵件系統匯入的快捷資料。由於傳送問題而未傳送給收件者的電子郵件訊息數量。 |
| 點按 | (必要)指定儲存電子郵件的Adobe Analytics事件，並從電子郵件系統中刪除資料。點擊的事件可讓您查看點擊電子郵件訊息的訪客人數。 |
| 已開啓 | (必要)指定Adobe Analytics事件，以儲存從電子郵件系統匯入的已開啓資料。「開啓的事件」可讓您查看開啓電子郵件訊息的訪客人數。 |
| 已傳送 | (必要)指定儲存電子郵件系統所傳送資料的Adobe Analytics事件。「傳送」事件可讓您查看傳送的電子郵件訊息數目。 |
| 取消訂閱 | (必要)指定將電子郵件取消訂閱從電子郵件系統匯入的Adobe Analytics事件。「取消訂閱」事件可讓您查看開啓電子郵件訊息但按一下「取消訂閱」連結，以取消組織未來電子郵件訊息的訪客數量。 |
| 區段 | 啓用現有區段與此整合(選用)。 |
| 存取要求 | 啓用建議的存取權限。 |
| 資料彙集 | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. 如果您選取此選項，請指定用於此整合的唯一識別碼：<ul><li>訊息ID查詢字串參數：此值代表電子郵件合作夥伴附加至著陸頁面URL的訊息ID。</li><li>收件者ID查詢字串參數：此值代表電子郵件合作夥伴的「收件者ID」附加至著陸頁面URL。</li></ul> |
| 控制面板和書簽產生 | 自動產生整合的控制面板和書簽。 |