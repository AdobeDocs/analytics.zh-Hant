---
description: 重要範本檔案是用來讓您開始匯入。
subtopic: Data sources
title: 產生匯入檔案範本
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 產生匯入檔案範本

重要範本檔案是用來讓您開始匯入。

不限使用範本中定義的欄。您可以視需要新增任何其他欄，只要選取的資料處理類型支援量度或定義。您可以在下列各節查閱各類型支援的量度和維度: Web [Traffic 、](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)Traffic [、](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md)Conversion [](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)Log事務處理 [](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)ID完整、訪客身份證處理（ID處理）。 For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

建立後，可下載範本，將您的資料輸入範本，然後上傳資料到資料來源 FTP 站台。Data Sources伺服器處理後，匯入的資料便可用於Analytics報表。

「資料來源」範本是 .txt 檔案，可以用任何文字編輯器開啟。不過，使用範本最簡單的方法是使用 Microsoft Excel 或其他試算表應用程式。範本的內容依您在「資料來源啟動精靈」中的選擇而異。

如需詳細資訊，請參閱[匯入檔案參考](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md)。

1. 登入 Analytics.
1. In the Suite header, select **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Review the Activation Instructions/Information, then click **[!UICONTROL Activate]**.

   步驟結果 1。 在「資料來源啟動精靈」中選取範本產生選項。

   | 精靈頁面 | 欄位 | 說明 |
   |--- |--- |--- |
   | 1 | 名稱 | Analytics在Data Sources管理員中顯示的範本名稱。 |
   | 1 | 電子郵件 | 接收所有與使用此「資料來源」範本相關之通知的電子郵件地址。 |
   | 1 | 相關費用核取方塊 | 選中此複選框表示您接受與此「資料源」模板相關的費用。 |
   | 2 | 選擇量度 | 選取以「資料來源」匯入的量度。Analytics會根據步驟3中選取的「資料來源類別」和「類型」，建議某些量度。  若要指定其他量度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用量度。 |
   | 3 | 量度映射 | 選取Analytics事件，以接收在精靈第2頁中選取的每個匯入量度。  應該是新的、未指派的事件，且先前已指派名稱 (名稱對應到事件將透過資料來源接收的匯入量度資料)。若 eVar、產品或追蹤代碼變數是目標變數，且上傳的值符合現存的已擷取值，上傳的事件實際上會新增量度到現存值。例如，您可以建立「離線訂購」量度，其中「產品」資料維度已有「產品檢視」、「結帳」和「訂購」等現有量度。 |
   | 4 | 選擇資料維度 | 選擇資料維度，用來劃分由此「資料來源」匯入的量度。Analytics建議根據步驟3中選取的「資料來源類型」來建立特定的資料維度。  若要指定其他資料維度，在空白欄位中輸入其名稱，然後選取核取方塊以啟用資料維度。 |
   | 5 | 資料維度映射 | 選取標準報表或 eVar，用以接收在精靈第 4 頁中選取的每一個已匯入資料維度。 |

1.  產生範本後，將資料複製到「資料來源」範本中適當的欄，務必遵守該資料欄要求的資料格式。

   步驟結果 1。 使用您愛用的命名規則儲存資料來源檔案。Adobe 建議對所有資料來源檔案使用一致的命名規則。使用常用的副檔名，例如。txt或。tsv（或不使用副檔名）。

