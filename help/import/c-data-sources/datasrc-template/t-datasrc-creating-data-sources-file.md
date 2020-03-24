---
description: 重要範本檔案是用來讓您開始匯入。
subtopic: Data sources
title: 產生匯入檔案範本
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 產生匯入檔案範本

重要範本檔案是用來讓您開始匯入。

不限使用範本中定義的欄。您可以視需要新增任何其他欄，只要選取的資料處理類型支援量度或定義。您可以在下列各節查閱各類型支援的量度和維度: [網站記錄檔](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)、[流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)、[轉換](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)、[交易 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)、[訪客 ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)、[完整處理](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md))。例如，針對流量資料類型，可以替列在[流量](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)中的任何量度或維度新增欄。

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。「資料來源」伺服器處理後，您的 Analytics 報表就可以使用匯入的資料。

「資料來源」範本是 .txt 檔案，可以用任何文字編輯器開啟。不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「資料來源啟動精靈」中的選擇而異。

如需詳細資訊，請參閱[匯入檔案參考](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)。

1. 登入 Analytics。
1. 在套裝標題中，按一下&#x200B;**[!UICONTROL 「管理]** > **[!UICONTROL Data Sources」]**。
1. 在&#x200B;**[!UICONTROL 「資料來源建立」]** 標籤中，選取範本類別和類型。
1.  閱讀「啟動指示/資訊」，然後按一下&#x200B;**[!UICONTROL 「啟動」]**。

   步驟結果 1。在「資料來源啟動精靈」中選取範本產生選項。

   | 精靈頁面 | 欄位 | 說明 |
   |--- |--- |--- |
   | 1 | 名稱 | Analytics 顯示在「資料來源管理器」中的範本名稱。 |
   | 1 | 電子郵件 | 接收所有與使用此「資料來源」範本相關之通知的電子郵件地址。 |
   | 1 | 相關費用核取方塊 | 選取此核取方塊表示您接受使用此「資料來源」範本的相關費用。 |
   | 2 | 選擇量度 | 選取以「資料來源」匯入的量度。Analytics 建議根據步驟 3 中的資料來源類別和類型，選擇特定量度。若要指定其他量度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用量度。 |
   | 3 | 量度映射 | 選取 Analytics 事件，用於接收在精靈第 2 頁中選取的每一個已匯入量度。應該是新的、未指派的事件，且先前已指派名稱 (名稱對應到事件將透過資料來源接收的匯入量度資料)。若 eVar、產品或追蹤代碼變數是目標變數，且上傳的值符合現存的已擷取值，上傳的事件實際上會新增量度到現存值。例如，您可以用已有現存量度「產品檢視」、「結帳」、「訂購」的產品維度來建立離線訂購量度。 |
   | 4 | 選擇資料維度 | 選擇資料維度，用來劃分由此「資料來源」匯入的量度。Analytics 建議根據步驟 3 中的資料來源類型，選擇特定資料維度。若要指定其他資料維度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用資料維度。 |
   | 5 | 資料維度映射 | 選取標準報表或 eVar，用以接收在精靈第 4 頁中選取的每一個已匯入資料維度。 |

1.  產生範本後，將資料複製到「資料來源」範本中適當的欄，務必遵守該資料欄要求的資料格式。

   步驟結果 1。使用您愛用的命名規則儲存資料來源檔案。Adobe 建議對所有資料來源檔案使用一致的命名規則。使用常見的副檔名，如 .txt 或 .tsv (或不使用副檔名)。

