---
description: 說明如何透過 FTP 上傳 資料檔案的步驟。
subtopic: Classifications
title: FTP 匯入
topic: Admin tools
uuid: a914970d-ba02-4111-9dcf-06448f71b9f3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# FTP 匯入

說明如何透過 FTP 上傳 資料檔案的步驟。

## FTP 匯入 {#concept_2F965BE873254546A61FB755F25299FD}

說明如何透過 FTP 上傳 資料檔案的步驟。

**[!UICONTROL 管理員]** &gt; **[!UICONTROL 分類匯入工具]**。

以下是重要的限制建議:

* 相較於數個大檔案，大量小檔案會減緩處理速度。這是因為小型工作會產生的佇列數量以及需排定優先順序。
* 請將大檔案分割為 50 MB 的區塊。這步驟非必要，但仍建議進行，因為可為後端提供較佳的處理可見度。此外，如果我們在處理您的工作時發生錯誤，工作會重新啟動，在這種情況下大型檔案會造成大量的工作重作。

初始設定會將大量的原始資料填入分類資料庫，或者重建分類，而不是只將幾列重新分類或新增列。

報表套裝中執行初始上傳後 (對於給定的變數/報告)，Adobe 建議，後續報告中僅上傳新的和更新的列。未來上傳時，應忽略未變更的列。

每個上傳的新代碼是以當月份該變數的唯一項目為計算基準。

當超過該月份的唯一客戶數上限時，您將無法在報告中看到超過唯一客戶數值的對應分類資料。您可以在 Data Warehouse 或 Ad Hoc Analysis 中查看這些分類。

> [!NOTE] 處理分類資料檔案的所需時間視檔案的大小，以及當下 Adobe 伺服器已處理中的檔案數量而定。資料檔案的處理時間通常不會超過 72 小時。

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。For more information, see [Create an FTP account](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF).

## 透過 FTP 匯入分類 {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

說明如何使用 FTP 帳戶將分類匯入 Adobe Analytics 的步驟。

如需建立 FTP 帳戶的詳細資訊，請參閱[建立 FTP 帳戶](/help/components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. 按一下&#x200B;**[!UICONTROL 「管理員]** &gt; **[!UICONTROL 分類匯入工具」]**。
1. 依序按一下&#x200B;**[!UICONTROL 「匯入檔案」]**&#x200B;和&#x200B;**[!UICONTROL 「FTP 匯入」]**。
1. 按一下要使用的 FTP 帳戶旁的&#x200B;**[!UICONTROL 「檢視」]**。
1.  使用您選擇的 FTP 用戶端利用 FTP 存取資訊 (主機、登入、密碼) 存取FTP 伺服器。
1. 將資料檔案 ([!DNL .tab] 或 [!DNL .txt]) 上傳至 FTP 伺服器。
1.  上傳資料檔案後，上傳指出檔案已可供處理的 FIN 檔案。

   FIN 檔案是空白的檔案，其名稱與您的資料檔案相同，副檔名為 [!DNL .fin]。例如，若您的資料檔案是 [!DNL classdata1.tab]，則 檔案名稱為 [!DNL classdata1.fin].fin。

Adobe 會在正常的間隔內擷取具有相關聯 FIN 檔案的已上傳資料檔案。Adode 會將其匯入於 FTP 帳戶設定中指定的報表套裝和資料集。

## 建立 FTP 帳戶 {#task_C019268E6C934C7C95F4326F42A22CCF}

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。&gt;

<!-- 

t_create_an_ftp_account.xml

 -->

如需 Adobe FTP 伺服器的其他詳細資訊，請參閱 [FTP 和 sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/)。

1. 按一下&#x200B;**[!UICONTROL 「管理員]** &gt; **[!UICONTROL 分類匯入工具」]**。
1. 依序按一下&#x200B;**[!UICONTROL 「匯入檔案」]**&#x200B;和&#x200B;**[!UICONTROL 「FTP 匯入」]**。
1. 在&#x200B;**[!UICONTROL 匯入檔案]**&#x200B;索引標籤中按一下&#x200B;**[!UICONTROL 「新增」]**。
1. 指定 FTP 帳戶詳細資料:

   | 元素 | 說明 |
   |---|---|
   | 名稱 | FTP 帳戶名稱。 |
   | 要分類的資料集 | 從下拉式清單中選取您要分類的資料集 (行銷報告變數)。 |
   | 選取報表套裝 | 選取您要分類選取之資料集的報表套裝。若要選擇多個報表套裝，每個所選報表套裝的分類必須相同。 |
   | 覆寫衝突的資料 | 選取這個選項以覆寫重複資料。在上傳現有的分類時，這個選項非常有用。如果您要新增額外的分類，我們不建議您使用此選項。 |
   | 匯入完成之後 | 選取這個選項，自動將更新的資料集匯出到同一個 FTP 帳戶一次。指定在匯入完成後接收關於此 FTP 帳戶之通知的電子郵件地址。 |
   | 通知收件者 | 指定要接收關於這個 FTP 帳戶之通知的電子郵件地址。 |
   | 授權 | (必要) 授權 Adobe 以自動匯入傳送到新 FTP 帳戶的所有資料檔案。 |

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

建立 FTP 帳戶後，按一下所需的 FTP 帳戶旁的適當連結可編輯或刪除該帳戶。
