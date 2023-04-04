---
title: 資料來源快速入門
description: 將範例資料上傳至開發報表套裝。
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# 資料來源快速入門

您可以依照下列步驟輕鬆將範例資料上傳至開發報表套裝，以查看實際運作中的工作流程。 了解程式後，您就可以展開，並量身打造符合組織實作的程式。

>[!IMPORTANT]
>
>使用開發或測試報表套裝，請依照下列步驟操作。 透過資料來源上傳的資料 **永久**. 如果上傳到生產報表套裝，則會影響資料。

1. 透過登入Adobe Analytics [https://experience.adobe.com](https://experience.adobe.com).
1. 導覽至 **[!UICONTROL 管理]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 資料來源]**.
1. 使用右上角的下拉式清單，選取開發報表套裝。
1. 按一下 **[!UICONTROL 建立]** 按鈕。
1. 在 [!UICONTROL 選擇類別]，選擇&quot;[!UICONTROL 一般]「 」和「 」下 [!UICONTROL 選擇類型]，選擇&quot;[!UICONTROL 一般資料來源（僅摘要資料）]」。
1. 按一下&#x200B;**[!UICONTROL 啟用]**。隨即開啟彈出式視窗，顯示 [!UICONTROL 資料源激活嚮導].
   1. 步驟1:為資料來源命名，然後按一下免責聲明核取方塊。
   1. 步驟2:此步驟在舊版Adobe Analytics中有更多使用。 按一下核取方塊，然後在旁邊的文字欄位中輸入任何值。
   1. 步驟3:選擇要包含在資料來源範本檔案中的量度。 從下拉式清單中選取「事件1」。
   1. 步驟4:此步驟在舊版Adobe Analytics中有更多使用。 按一下核取方塊，然後在旁邊的文字欄位中輸入任何值。
   1. 步驟5:選擇要包含在資料來源範本檔案中的維度。 從下拉式清單中選取「eVar1」。
   1. 步驟6:檢閱摘要，顯示範本檔案中包含的維度和量度。
   1. 步驟7:按一下 **[!UICONTROL 下載]** 按鈕下載資料源模板檔案。 另請注意FTP站台的登入認證，因為這些認證很快就會使用。
1. 資料來源現在已建立；下一步是將資料提供給處理。 在所需的文字編輯器中開啟下載的檔案。
1. 範本檔案包含三行；兩個注釋行(以「`#`&quot;)和標題行：

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #	eVar1	event1
   Date	Evar 1	Event 1
   ```

1. 在數列資料中輸入，並依索引標籤分隔每個項目。 請勿使用空格或逗號來分隔值。
   * 第一欄是以下格式的日期： `MM/DD/YYYY/HH/mm/SS`.
   * 第二欄是您要納入eVar1的文字值。
   * 第三欄是您要增加事件1的金額。

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #	eVar1	event1
   Date	Evar 1	Event 1
   09/07/YYYY/11/23/00	Data source example value	3
   09/07/YYYY/15/59/00	Another data source value	18
   ```

1. 儲存檔案。您可以視需要為其指定不同的檔案名稱。 儲存檔案後，您可以關閉文字編輯器。
1. 在Windows Explorer、Finder或您選擇的FTP用戶端中，導覽至 [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. 提示輸入登錄憑據時，請使用資料源建立嚮導的最後一個步驟中提供的用戶名和密碼。 您可以導覽至 [!UICONTROL 資料來源] 按一下 **[!UICONTROL FTP資訊]** 旁邊。
1. 驗證後，將您編輯的檔案拖曳至已驗證的FTP視窗。
1. 在FTP視窗以外的任何位置建立空白文字檔案。 指定與您上傳至FTP站台的資料來源檔案相同的檔案名稱，但有一個例外。 而非 `.txt` 檔案類型 `.fin` 檔案類型。 請確定您的作業系統設定可讓您查看和變更檔案類型。
1. 拖曳空白 `.fin` 檔案移至與資料來源檔案相同的FTP位置。 存在 `.fin` 檔案會告訴Adobe資料來源檔案已完全上傳，且已準備好內嵌。
1. 幾分鐘後，檔案會從FTP位置消失，並顯示在報表中。
1. 重新整理「資料來源」頁面，並驗證檔案是否已成功擷取。
1. 導覽至Analysis Workspace並建立專案。
1. 將eVar1拖曳至工作區畫布，並將事件1拖曳至量度。 請確定工作區日期範圍包含您在資料來源中提供的日期。

   ![報表範例](assets/success-report.png)

## 後續步驟

[檔案格式](file-format.md):了解有關建立為您的組織量身打造的資料來源檔案的詳細資訊。