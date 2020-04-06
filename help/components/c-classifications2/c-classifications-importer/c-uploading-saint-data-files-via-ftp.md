---
description: 說明如何透過 FTP 上傳 資料檔案的步驟。
subtopic: Classifications
title: FTP 匯入
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# FTP 匯入

說明如何透過 FTP 上傳 資料檔案的步驟。

## FTP 匯入 {#concept_2F965BE873254546A61FB755F25299FD}

說明如何透過 FTP 上傳 資料檔案的步驟。

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.

以下是重要的限制建議：

* 許多小檔案的處理速度會比少數大檔案慢。 這是由於小作業需要的佇列數量和優先順序。
* 請將大型檔案分割為50 MB的區塊。 這並非必要項目，但建議使用，因為它可更清楚地瞭解後端的進度。 此外，如果我們處理您的作業時發生錯誤，作業將會重新啟動；在此案例中，大型檔案會造成大量工作重做。

初始設定會以大量原始資料填入分類資料庫，或重新建構分類，而不是重新分類幾列或新增列。

在報表套裝中進行初始上傳（針對指定的變數或報表）後，Adobe建議在後續的匯入中僅上傳新和更新的列。 未變更的列應從未來的上載中忽略。

您上傳的每個新索引鍵值，都會針對該月變數的獨特值計數。

如果超過該月的唯一客戶數，您將無法在報告中看到超出唯一客戶數值的對應分類資料。 您可以在資料倉庫或臨機分析中查看這些分類。

>[!NOTE] 處理分類資料檔案的所需時間視檔案的大小，以及當下 Adobe 伺服器已處理中的檔案數量而定。資料檔案的處理時間通常不超過72小時。

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。如需詳細資訊，請參閱[建立 FTP 帳戶](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

## 透過 FTP 匯入分類 {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

說明如何使用FTP帳戶將分類匯入Adobe Analytics的步驟。

如需建立FTP帳戶的詳細資訊，請參 [閱建立FTP帳戶](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. 按一下 **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. 按一 **[!UICONTROL Import File]**&#x200B;下，然後按一 **[!UICONTROL FTP Import]**&#x200B;下。
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1. 使用您選擇的 FTP 用戶端利用 FTP 存取資訊 (主機、登入、密碼) 存取FTP 伺服器。
1. 將資料檔案 ([!DNL .tab] 或 [!DNL .txt]) 上傳至 FTP 伺服器。
1. 上傳資料檔案後，上傳指出檔案已可供處理的 FIN 檔案。

   FIN 檔案是空白的檔案，其名稱與您的資料檔案相同，副檔名為 [!DNL .fin]。例如，若您的資料檔案是 [!DNL classdata1.tab]，則 檔案名稱為 [!DNL classdata1.fin].fin。

Adobe會定期擷取具有相關聯FIN檔案的上傳資料檔案。 Adobe會將它們匯入FTP帳戶設定中指定的報表套裝和資料集。

## 建立 FTP 帳戶 {#task_C019268E6C934C7C95F4326F42A22CCF}

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。>

<!-- 

t_create_an_ftp_account.xml

 -->

如需 Adobe FTP 伺服器的其他詳細資訊，請參閱 [FTP 和 sFTP](https://marketing.adobe.com/resources/help/zh_TW/whitepapers/ftp/)。

1. 按一下 **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. 按一 **[!UICONTROL Import File]**&#x200B;下，然後按一 **[!UICONTROL FTP Import]**&#x200B;下。
1. 在標籤 **[!UICONTROL Import File]** 上，按一下 **[!UICONTROL Add New]**。
1. 指定 FTP 帳戶詳細資料：

   | 元素 | 說明 |
   |---|---|
   | 名稱 | FTP帳戶名稱。 |
   | 要分類的資料集 | 從下拉式清單中，選取您要分類的資料集（行銷報告變數）。 |
   | 選取報表套裝 | 選取您要將所選資料集分類的報表套裝。 若要選取多個報表套裝，每個選取報表套裝的分類必須相同。 |
   | 覆寫衝突時的資料 | 選取此選項可覆寫重複資料。 如果您要更新現有分類，這個選項會很有用。 如果您要新增其他分類，則不建議使用此選項。 |
   | 匯入完成後 | 選取此選項，可自動將更新的資料集匯出至相同的FTP帳戶一次。指定在匯入完成後接收此FTP帳戶相關通知的電子郵件地址。 |
   | 通知收件者 | 指定接收此FTP帳戶相關通知的電子郵件地址。 |
   | 授權 | （必要）授權Adobe自動匯入所有傳送至新FTP帳戶的資料檔案。 |

1. 按一下 **[!UICONTROL Save]**.

建立 FTP 帳戶後，按一下所需的 FTP 帳戶旁的適當連結可編輯或刪除該帳戶。
