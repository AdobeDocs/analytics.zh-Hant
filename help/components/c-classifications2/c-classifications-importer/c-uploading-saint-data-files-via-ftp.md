---
description: 說明如何透過 FTP 上傳 資料檔案的步驟。
seo-description: 說明如何透過 FTP 上傳 資料檔案的步驟。
seo-title: FTP匯入
solution: Analytics
subtopic: '分類   '
title: FTP匯入
topic: 管理工具
uuid: a914970d-ba02-4111-9dcf-06448f71 b9 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# FTP匯入

說明如何透過 FTP 上傳 資料檔案的步驟。

## FTP import {#concept_2F965BE873254546A61FB755F25299FD}

說明如何透過 FTP 上傳 資料檔案的步驟。

**[!UICONTROL 管理員]** &gt; **[!UICONTROL 分類匯入工具]**。

以下是重要的限制建議:

* 相較於數個大檔案，大量小檔案會減緩處理速度。這是因為小型工作會產生的佇列數量以及需排定優先順序。
* 請將大檔案分割為 50 MB 的區塊。這步驟非必要，但仍建議進行，因為可為後端提供較佳的處理可見度。此外，如果我們在處理您的工作時發生錯誤，工作會重新啟動，在這種情況下大型檔案會造成大量的工作重作。

初始設定會將大量的原始資料填入分類資料庫，或者重建分類，而不是只將幾列重新分類或新增列。

報表套裝中執行初始上傳後 (對於給定的變數/報告)，Adobe 建議，後續報告中僅上傳新的和更新的列。未來上傳時，應忽略未變更的列。

每個上傳的新代碼是以當月份該變數的唯一項目為計算基準。

當超過該月份的唯一客戶數上限時，您將無法在報告中看到超過唯一客戶數值的對應分類資料。您可以在 Data Warehouse 或 Ad Hoc Analysis 中查看這些分類。

>[!NOTE]
>
>處理分類資料檔案所需的時間視檔案大小和目前Adobe伺服器已處理的檔案數量而定。資料檔案的處理時間通常不會超過 72 小時。

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。有關詳細資訊，請參閱[建立 FTP 帳戶](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

## 透過 FTP 匯入分類 {#task_132C36830B69418B8C929E39838EF01D}

<!-- 

t_upload_a_saint_data_file_via_ftp.xml

 -->

說明如何使用 FTP 帳戶將分類匯入 Adobe Analytics 的步驟。

如需建立 FTP 帳戶的詳細資訊，請參閱[建立 FTP 帳戶](../../../components/c-classifications2/c-classifications-importer/c-uploading-saint-data-files-via-ftp.md#task_C019268E6C934C7C95F4326F42A22CCF)。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. Next to the FTP account that you want to use, click **[!UICONTROL View]**.
1.  使用您選擇的 FTP 用戶端利用 FTP 存取資訊 (主機、登入、密碼) 存取FTP 伺服器。
1. Upload the data file ( [!DNL .tab] or [!DNL .txt]) to the FTP server.
1.  上傳資料檔案後，上傳指出檔案已可供處理的 FIN 檔案。

   The FIN file is an empty file that has the same name as your data file, with a [!DNL .fin] filename extension. For example, if your data file is [!DNL classdata1.tab], the FIN filename is [!DNL classdata1.fin].

Adobe 會在正常的間隔內擷取具有相關聯 FIN 檔案的已上傳資料檔案。Adode 會將其匯入於 FTP 帳戶設定中指定的報表套裝和資料集。

## 建立 FTP 帳戶 {#task_C019268E6C934C7C95F4326F42A22CCF}

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。&gt;

<!-- 

t_create_an_ftp_account.xml

 -->

如需 Adobe FTP 伺服器的其他詳細資訊，請參閱 [FTP 和 sFTP](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/)。

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**, then click **[!UICONTROL FTP Import]**.
1. On the **[!UICONTROL Import File]** tab, click **[!UICONTROL Add New]**.
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

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

建立 FTP 帳戶後，按一下所需的 FTP 帳戶旁的適當連結可編輯或刪除該帳戶。
