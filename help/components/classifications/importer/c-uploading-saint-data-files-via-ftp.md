---
description: 如何透過 FTP 上傳資料檔案。
title: FTP 匯入
feature: Classifications
exl-id: 3e93b35c-6f65-4a93-887d-d94e4d359bdc
TQID: https://experienceleague.adobe.com/CMHQpWtGl14Z7kHaZ7ufp6-tDIfQ-pCEzSI47XMi-pA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 727
ht-degree: 75%

---

# FTP匯入（舊版）

{{classification-importer-deprecation}}

>[!IMPORTANT]
>
>Adobe不再建議使用FTP進行匯入，如本頁所述。
>
>不建議使用FTP，因為這是共用檔案的未加密方法，這表示任何人都可以攔截檔案內容以及帳戶使用的使用者名稱和密碼。
>
>請依照[設定雲端匯入和匯出帳戶](/help/components/locations/configure-import-accounts.md)中的說明來設定雲端帳戶。

說明如何透過 FTP 上傳 資料檔案的步驟。

## FTP 匯入 {#concept_2F965BE873254546A61FB755F25299FD}

透過 FTP 上傳資料檔案：

1. **[!UICONTROL 管理員]** > **[!UICONTROL 分類匯入工具]**。

以下是重要的限制建議。

>[!IMPORTANT]
>
>過多小檔案或單一大檔案會在處理伺服器上產生不必要的處理負載。 Adobe 建議將大檔案拆分為 50 MB 的小檔，或將小檔案合併。

初始設定會使用大型原始資料集填入分類資料庫，或重新建構分類，而不是重新分類少數列或新增列。

報表套裝中執行初始上傳後 (對於給定的變數/報告)，Adobe 建議，後續報告中僅上傳新的和更新的列。 未來上傳時應忽略未變更的列。

您上傳的每個新索引鍵值，都會計入當月該變數的唯一值。

如果您超過該月的不重複值，您將不會在報表中看到不重複值超過值的對應分類資料。 您可以在 Data Warehouse 中看到這些分類。

>[!NOTE]
>
>處理分類資料檔案的所需時間視檔案的大小，以及當下 Adobe 伺服器已處理中的檔案數量而定。 資料檔案的處理時間通常不會超過 72 小時。

## 建立 FTP 帳戶

在透過 FTP 上傳資料之前，請先建立 FTP 帳戶。 >

如需 Adobe FTP 伺服器的其他詳細資訊，請參閱 [FTP 和 sFTP](/help/export/ftp-and-sftp/ftp-overview.md)。

1. 按一下&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 分類匯入工具」]**。
1. 依序按一下&#x200B;**[!UICONTROL 「匯入檔案」]**&#x200B;和&#x200B;**[!UICONTROL 「FTP 匯入」]**。
1. 在&#x200B;**[!UICONTROL 匯入檔案]**&#x200B;索引標籤中按一下&#x200B;**[!UICONTROL 「新增」]**。
1. 指定 FTP 帳戶詳細資料：

   | 元素 | 說明 |
   |---|---|
   | **名稱** | FTP 帳戶名稱。 |
   | **要分類的資料集** | 從下拉式清單中選取您要分類的資料集 (行銷報告變數)。 |
   | **選取報表套裝** | 選取您要分類選取之資料集的報表套裝。 若要選擇多個報表套裝，每個所選報表套裝的分類必須相同。 |
   | **覆寫衝突的資料** | 選取此選項可覆寫重複資料。 如果您更新現有的分類，此選項會很有用。 如果使用[最新分類架構](../sets/overview.md)，會一律啟用此設定。 |
   | **匯入完成之後** | 選取這個選項，自動將更新的資料集匯出到同一個 FTP 帳戶一次。指定在匯入完成後接收關於此 FTP 帳戶之通知的電子郵件地址。 如果使用[最新分類架構](../sets/overview.md)，會無法使用此選項。 |
   | **通知收件者** | 指定要接收關於這個 FTP 帳戶之通知的電子郵件地址。 |
   | **授權** | (必要) 授權 Adobe 以自動匯入傳送到新 FTP 帳戶的所有資料檔案。 |

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

建立 FTP 帳戶後，按一下所需的 FTP 帳戶旁的適當連結可編輯或刪除該帳戶。

>[!NOTE]
>
>如果匯入未對分類造成任何變更，則不會發送通知。 只有在成功並導致分類變更時，才會發送電子郵件。

## 透過 FTP 匯入分類

您可以使用 FTP 帳戶將分類匯入 Adobe Analytics。

若要透過 FTP 匯入分類：

1. 按一下&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 分類匯入工具」]**。
1. 依序按一下&#x200B;**[!UICONTROL 「匯入檔案」]**&#x200B;和&#x200B;**[!UICONTROL 「FTP 匯入」]**。
1. 按一下要使用的 FTP 帳戶旁的&#x200B;**[!UICONTROL 「檢視」]**。
1. 使用您選擇的 FTP 用戶端利用 FTP 存取資訊 (主機、登入、密碼) 存取FTP 伺服器。
1. 將資料檔案 (`.tab` 或 `.txt`) 上傳至 FTP 伺服器。
1. 上傳資料檔案後，上傳指出檔案已可供處理的 FIN 檔案。

   FIN 檔案是空白的檔案，其名稱與您的資料檔案相同，副檔名為 `.fin`。 例如，若您的資料檔案是 `classdata1.tab`，則 檔案名稱為 `classdata1.fin`.fin。

Adobe會定期擷取上傳的具有關聯FIN檔案的資料檔案。 Adode 會將其匯入於 FTP 帳戶設定中指定的報表套裝和資料集。

一旦 Adobe Analytics 讀取並處理了上傳到 FTP 資料夾中的檔案，這些檔案就會自動從 FTP 網站上移除。
