---
description: 重要範本檔案是用來讓您開始匯入。
seo-description: 重要範本檔案是用來讓您開始匯入。
seo-title: 產生匯入檔案範本
solution: Analytics
subtopic: 資料來源
title: 產生匯入檔案範本
topic: 開發人員和實施
uuid: bcd90e34-42e6-4cd1-b67 e-87586dea25 d8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# 產生匯入檔案範本

重要範本檔案是用來讓您開始匯入。

不限使用範本中定義的欄。您可以視需要新增任何其他欄，只要選取的資料處理類型支援量度或定義。您可以在下列各節查閱各類型支援的量度和維度:[網站記錄檔](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)、 [流量](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC)、 [轉換](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)、 [交易ID](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)、 [訪客ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)、 [完全處理](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED))。For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC).

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。Data Sources伺服器處理後，即可在您的Analytics報表中使用匯入的資料。

「資料來源」範本是 .txt 檔案，可以用任何文字編輯器開啟。不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「資料來源啟動精靈」中的選擇而異。

如需詳細資訊，請參閱[匯入檔案參考](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD)。

1. 登入 Analytics.
1. In the Suite header, select **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   步驟結果1. 在「資料來源啟動精靈」中選取範本產生選項。

   | 精靈頁面 | 欄位 | 說明 |
   |--- |--- |--- |
   | 1 | 名稱 | Analytics在「資料來源管理員」中顯示的範本名稱。 |
   | 1 | 電子郵件 | 接收所有與使用此「資料來源」範本相關之通知的電子郵件地址。 |
   | 1 | 相關費用核取方塊 | 選取核取方塊，表示您接受使用此「資料來源」範本的相關費用。 |
   | 2 | 選擇量度 | 選取以「資料來源」匯入的量度。Analytics建議根據步驟中的「資料來源類別」和「類型」，建議特定度量。若要指定其他量度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用量度。 |
   | 3 | 量度映射 | 選取Analytics事件，以接收在精靈第頁中選取的每個已匯入量度。應該是新的、未指派的事件，且先前已指派名稱 (名稱對應到事件將透過資料來源接收的匯入量度資料)。若 eVar、產品或追蹤代碼變數是目標變數，且上傳的值符合現存的已擷取值，上傳的事件實際上會新增量度到現存值。例如，您可以用已有現存量度「產品檢視」、「結帳」、「訂購」的產品維度來建立離線訂購量度。 |
   | 4 | 選擇資料維度 | 選擇資料維度，用來劃分由此「資料來源」匯入的量度。Analytics建議根據步驟中選取的「資料來源類型」來指定特定資料維度。若要指定其他資料維度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用資料維度。 |
   | 5 | 資料維度映射 | 選取標準報表或 eVar，用以接收在精靈第 4 頁中選取的每一個已匯入資料維度。 |

1.  產生範本後，將資料複製到「資料來源」範本中適當的欄，務必遵守該資料欄要求的資料格式。

   步驟結果1. 使用您愛用的命名規則儲存資料來源檔案。Adobe 建議對所有資料來源檔案使用一致的命名規則。使用常用的副檔名，如 .txt 或 .tsv (或不要使用副檔名)。

