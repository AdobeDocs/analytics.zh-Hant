---
description: 關於資料來源 .txt 範本的資訊。
subtopic: Data sources
title: 匯入檔案參考
topic: Developer and implementation
uuid: cc58f8d8-cb6e-4908-846f-0a41c6da805d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 匯入檔案參考

關於資料來源 .txt 範本的資訊。

使用「資料來源精靈」產生匯入範本。資料來源匯入檔案包含下列資料:

* 井字號 (#) 將該列識別為備註。
* 您可視需要在檔案中新增其他備註。
* 備註，列出範本檔案標題。
* 備註，列出在「[!UICONTROL 資料來源啟動精靈]」中指定之外部量度和資料維度名稱。

欄標題是用於識別「資料來源」檔案中各欄的資料。有三種欄標題:

**日期**: (必要) 檔案中每一列資料的時間戳記。

**變數**:映射到資料來源資料維度的報表變數名稱。

**事件**:映射至資料來源量度的事件名稱。

使用資料來源範本建立資料來源檔案，用以包含您要上傳的資料。建立資料來源檔案時，記住下列原則:

* 實際上，資料來源檔案中的每一列包含一個資料記錄，而每一個記錄是由一連串以定位點分格的欄位所組成。「資料來源」範本中的欄標題定義這些欄位的順序。例如:

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* 若您上傳多個資料欄位，資料來源會以字母順序載入它們。若檔案需以時間順序處理，則必須加以指定，它們的字母順序才會對應到其時間順序。例如:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* 若要加速資料來源檔案的處理，Adobe 建議按日期將事件 (量度) 資料集中到單一列。

   例如，若您的資料來源檔案是將廣告印象資料映射至事件 6，請建立包含每天廣告印象總數的單一資料列，而不是替特定一天發生的廣告印象建立單獨一列。
* 如果您需要上傳報表套裝建立日期以前的資料，請連絡您的帳戶管理員以變更您可執行報表的最早日期。

**.FIN 檔案**

當您填寫完「資料來源」檔案後，可將它FTP傳入Analytics。 但是，還需要其他檔案，系統才能處理您的資料。You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
