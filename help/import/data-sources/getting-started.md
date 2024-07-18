---
title: 資料來源快速入門
description: 將範例資料上傳至開發報表套裝。
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# 資料來源快速入門

您可以依照下列步驟，輕鬆將範例資料上傳至開發報表套裝中，以檢視運作中的工作流程。 瞭解該流程後，您就可以針對組織的實作專案加以擴展和量身打造。

>[!IMPORTANT]
>
>使用開發或測試報表套裝，依循下列步驟。 透過資料來源上傳的資料為&#x200B;**永久**。 若上傳至該處，將影響生產報表套裝資料。

1. 透過[https://experience.adobe.com](https://experience.adobe.com)登入Adobe Analytics。
1. 瀏覽至&#x200B;**[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 資料來源]**。
1. 使用右上方的下拉式清單，選取開發報表套裝。
1. 按一下左上方的&#x200B;**[!UICONTROL 建立]**&#x200B;按鈕。
1. 在[!UICONTROL 選取類別]下，選擇「[!UICONTROL 一般]」，然後在[!UICONTROL 選取型別]下，選擇「[!UICONTROL 一般資料Source （僅限摘要資料）]」。
1. 按一下&#x200B;**[!UICONTROL 啟動]**。 隨即開啟快顯視窗，顯示[!UICONTROL 資料Source啟動精靈]。
   1. 步驟1：為資料來源命名，然後按一下免責宣告核取方塊。
   1. 步驟2：此步驟在舊版Adobe Analytics中有更多用途。 按一下核取方塊，然後在其旁邊的文字欄位中輸入任何值。
   1. 步驟3：選擇要包含在資料來源範本檔案中的量度。 從下拉式清單中選取「事件1」。
   1. 步驟4：此步驟在舊版Adobe Analytics中有更多用途。 按一下核取方塊，然後在其旁邊的文字欄位中輸入任何值。
   1. 步驟5：選擇要包含在資料來源範本檔案中的維度。 從下拉式清單中選取「eVar1」。
   1. 步驟6：檢閱摘要，顯示範本檔案中所包含的維度和量度。
   1. 步驟7：按一下&#x200B;**[!UICONTROL 下載]**&#x200B;按鈕以下載資料來源範本檔案。 同時請留意FTP站台的登入認證，因為認證僅供日後使用。
1. 資料來源現在已建立；下一步是提供資料以供處理。 在想要的文字編輯器中開啟已下載的檔案。
1. 範本檔案包含三行；兩個註解行（以&quot;`#`&quot;開頭）和一個標頭列：

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. 在數列資料中輸入，以索引標籤分隔每個專案。 請勿使用空格或逗號來分隔值。
   * 第一欄是下列格式的日期： `MM/DD/YYYY/HH/mm/SS`。
   * 第二欄是您要包含在eVar1中的文字值。
   * 第三欄是您要增加事件1的金額。

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. 儲存檔案。 如有需要，您可以選擇提供其他檔案名稱。 儲存檔案後，即可關閉文字編輯器。
1. 在Windows檔案總管、尋找器或您選擇的FTP使用者端中，導覽至[ftp://ftp.omniture.com](ftp://ftp.omniture.com)。
1. 出現登入認證提示時，請使用資料來源建立精靈的最後一步驟中提供的使用者名稱和密碼。 您可以導覽至[!UICONTROL 資料來源]，然後按一下您建立的資料來源旁的&#x200B;**[!UICONTROL FTP資訊]**，以再次參考它。
1. 驗證後，將您編輯的檔案拖曳至已驗證的FTP視窗。
1. 在FTP視窗之外的任何位置建立空白文字檔。 為您提供和您上傳至FTP站台的資料來源檔案相同的檔案名稱，但有一個例外。 請指定`.fin`檔案型別，而不是`.txt`檔案型別。 請確定您的作業系統設定可讓您檢視及變更檔案型別。
1. 將空的`.fin`檔案拖曳到與資料來源檔案相同的FTP位置。 `.fin`檔案的存在會告知Adobe資料來源檔案已完全上傳，且準備內嵌。
1. 幾分鐘後，檔案會從FTP位置消失，並顯示在報表中。
1. 重新整理「資料來源」頁面，並驗證檔案是否已成功內嵌。
1. 導覽至Analysis Workspace並建立專案。
1. 將事件1作為維度拖曳至工作區畫布，並將eVar1作為量度拖曳。 請確定Workspace日期範圍包含您在資料來源中提供的日期。

   ![範例報表](assets/success-report.png)

## 後續步驟

[檔案格式](file-format.md)：瞭解建立適合您組織的資料來源檔案的相關詳細資訊。
