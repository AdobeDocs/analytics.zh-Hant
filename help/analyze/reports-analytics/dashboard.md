---
description: 控制面板是稱為小報表的縮圖報表集合。 控制面板若包含相關小報表，可提供您網站特定方面的完整概觀，例如尋找方法、訪客資料等，則最有用。
subtopic: Dashboards
title: 控制面板和報表
topic: Reports and analytics
uuid: 7a7b3bc9-0a3c-49b0-9168-e2878ae67b97
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 控制面板和報表

控制面板是稱為小報表的縮圖報表集合。 控制面板若包含相關小報表，可提供您網站特定方面的完整概觀，例如尋找方法、訪客資料等，則最有用。

## 控制面板和報表 {#concept_8CD3ACA2830A4994A68A31D8773B57E0}

控制面板是報告縮圖的集合，稱為&#x200B;*`reportlets`*。控制面板若包含相關小報表，可提供您網站特定方面的完整概觀，例如尋找方法、訪客資料等，則最有用。

您可以將大部分的行銷報告新增至控制面板，包括圖形密集型報 [!UICONTROL Fallout Report]告， [!UICONTROL Conversion Funnel Report]例如、和 [!UICONTROL Pathfinder Report]。

您也可以將控制面板設為著陸頁面、與其他使用者共用控制面板，並排程控制面板的傳送。 如果您未將控制面板（或書籤）設為著陸頁面，則會顯示控 [!UICONTROL My Recommended Reports] 制面板。 **[!UICONTROL My Recommended Reports]** 顯示報 **[!UICONTROL Key Metrics]** 表，加上您最常檢視的5個報表。 這是根據您最常檢視的實際報表而動態顯示。

請注意，有些經常檢視的報表無法設定控制面板，因此不會顯示。 這些類別包括：

* 異常偵測報表
* 貢獻分析報表
* 流失報表
* Pathfinder報表
* 即時報表
* 其他控制面板

>[!NOTE] 「報 **[!UICONTROL Site Overview]** 告與分析」中不再列出控制面板。 不過，您仍有幾種情況可看到其部分或全部小報表。

* If you have, say, only three frequently viewed reports, Reports &amp; Analytics will take two reports from the Site Overview dashboard to complete the **[!UICONTROL My Recommended Reports]** dashboard.
* 全新的報表套裝一開始仍會包含網站綜覽報表，直到您經常檢視的報表取代它們為止。 即使如此，控制面板現在也會被呼叫 **[!UICONTROL My Recommended Reports]**。

除了您建立的控制面板外，使用者也可使用下列預先封裝的控制面板︰

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Local Sites]**

此可自訂的控制面板可讓您將小報表拖放至所提供的範本中。

**[!UICONTROL Components]>[!UICONTROL Dashboards]>[!UICONTROL Shared Dashboards]>[!UICONTROL Site Operations Dashboard]**

此控制面板提供與網站作業相關之關鍵量度的概述。 此控制面板上的報表包括：

* 退出頁面
* 最受歡迎頁面
* 最受歡迎網站區域
* KPI/量規報表
* 文字報表
* 公司摘要報表

使用可 [!UICONTROL Dashboard Manager] 編輯和管理控制面板，並啟用它們以進行DirectAccess。

See [Managing Dashboards](/help/analyze/reports-analytics/dashboard-manage.md).

## 建立控制面板 {#task_54EFBED59BDC4418A919E6EF84AB9CFF}

說明如何建立控制面板的步驟。

<!-- 

t_dashboard_add.xml

 -->

在新增報表（作為小報表）至控制面板之前，請先定義控制面板的配置。

1. Go to **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Manage Dashboards]**.
1. 按一下 **[!UICONTROL Add Dashboard]**.
1. 鍵入控制面板的名稱。
1. 按一下 **[!UICONTROL 3 x 2]** 或 **[!UICONTROL 2 x 2]**，指定您想在控制面板頁面上顯示幾個小報告。
1. 設定控制面板頁面配置：

   * **[!UICONTROL Add Page]**:新增空白頁面至控制面板，您可在控制面板上拖曳內容以建立小報表。
   * **[!UICONTROL Paper]**:可讓您指定紙張大小，例如橫向、縱向和A4。
   * **[!UICONTROL Find Content]**:可讓您搜尋和功能表中 [!UICONTROL Add Content] 的內 [!UICONTROL Dashboard Contents] 容。

1. 拖曳項目至小報告畫布，即可新增可用內容至控制面板。

   請參閱[建立小報告](/help/analyze/reports-analytics/dashboard.md#task_EC3AFBBAA51C45CEBAF632F841C305B3)和[編輯控制面板設定](/help/analyze/reports-analytics/dashboard.md#task_90D7FAC1CC3E4DB786B4C87CC33B5459)。
1. 按一下 **[!UICONTROL Save.]**

   Saving a dashboard makes it available in the **[!UICONTROL Dashboard]** menu. The new dashboard is also available in the [!UICONTROL Dashboard Manager] ( **[!UICONTROL Favorites]** > **[!UICONTROL Dashboards]** > **[!UICONTROL Manager]**), where you can edit, organize, share, schedule, archive dashboards, and more. (請參閱[管理控制面板](/help/analyze/reports-analytics/dashboard-manage.md))。

1. （可選）若要將控制面板設定為著陸頁面，請按一下 **[!UICONTROL More Options]** > **[!UICONTROL Set as Landing Page]**。

## 建立小報告 {#task_EC3AFBBAA51C45CEBAF632F841C305B3}

說明如何建立小報表的步驟。 建立小報表後，它便可顯示在控制面板中。

<!-- 

t_dashboard_add_report.xml

 -->

1. 執行報告。
1. 按一下 **[!UICONTROL Dashboard.]**
1. 在頁面 [!UICONTROL Add Reportlet] 上，為報表命名，然後從中選取控制面板 **[!UICONTROL Place in Dashboard]**。
1. (可選) 設定日期範圍。

   * **[!UICONTROL Rolling]**:根據時間範圍（每日、每月等）變更時間流逝的日期。 例如，如果今天是1月17日，您可以設定1月15 - 16日的日期。 然後，如果您選 **[!UICONTROL Rolling]**&#x200B;取，則在1月27日，小報表會顯示1月25 - 26日的資料。
   * **[!UICONTROL Fixed]**:防止日期隨著時間流逝而向前移動。

1. (可選) 覆蓋發佈分送清單。

   **[!UICONTROL Publishing List Override]**:如果您啟用此選項，則在分發至發佈清單時，一律會使用此小報告中參考的報表套裝。 如果您停用此選項，則發佈清單中識別的報表套裝會取代此小報表中的報表套裝。

1. 按一下 **[!UICONTROL Create New]**.

   The reportlet is added to the **[!UICONTROL Dashboard Contents]** menu in the dashboard editor.

## 將內容新增到控制面板 {#task_90D7FAC1CC3E4DB786B4C87CC33B5459}

說明如何從其他控制面板和共用控制面板新增內容的步驟。 您也可以從自訂和外部來源（例如文字和影像）新增內容。

<!-- 

t_dashboard_content.xml

 -->

1. Open a dashboard, then click **[!UICONTROL Layout]**.
1. Click **[!UICONTROL Add Content]**, then drag items to the dashboard.

   The [!UICONTROL Add Content] menu displays reportlet content from other dashboards, legacy dashboards, and shared dashboards.

   >[!NOTE]
   >
   >控制面板中目前的頁數限制為 30。

   **自訂小報表**

   *資料內容：*

   * 公司摘要：顯示您選取的多個報告套裝和度量的頁面檢視。
   * 量規：顯示一個量規，告訴您度量圖與所指定臨界值的關聯位置。

      您可以選取度量、圖表類型、顏色範圍以及臨界值。如果度量的計數超過大於臨界值，量規會使用大於欄位上方的顏色，在小報告中指出這點。如果度量的計數小於臨界值，量規會使用小於欄位上方的顏色，在小報告中指出這點。您在這些欄位中指定的值是度量的可計算值，例如頁面檢視次數、金額、購物車檢視等等（請勿使用特殊字元。）
   * 報告套裝摘要：顯示報告套裝的選定度量及其總計或高和低值。
   * 使用摘要：依據您公司的人員顯示有關介面存取的資料。這個小報告可依使用者名稱存取、報告存取或報告套裝存取來顯示資料。您可以提供 URL 以便建立以下使用者內容小報告。如果影像或其他資源 URL 不是以 https:// 開始，則 Internet Explorer 使用者可能會看到有關混合內容的警告。您可以在瀏覽器的安全設定中停用混合內容的警告。
   *使用者內容：*

   * 外部報告：讓您以 .xml 和 .csv 格式新增外部報告。
   * HTML：讓您新增自訂 HTML 小報告。URL 必須使用 HTTP 或 HTTPS。否則，您將會看到 `Specified URL could not be retrieved` 錯誤。在文件的內容中，會移除所有含有使用 data: 和 javascript: 通訊協定之屬性的標記。同時移除指令、框架、Applet、事件處理程式、Flash 及其他內嵌對象。如果使用非 HTTPS 指定資源，IE 使用者會收到有關混合內容的警告。
   * 影像：讓您從影像 URL 中建立控制面板。如果 URL 使用 HTTP 通訊協定，Internet Explorer 會發出混合內容警告。請使用帶 HTTPS 的 URL 移除警告。其他所有通訊協定都會發出 `Specified URL could not be retrieved` 錯誤。
   * RSS：讓您新增 RSS 網頁摘要。必須是 HTTP 或 HTTPS。否則，您將會看到 `Specified URL could not be retrieved` 錯誤。
   * 文字：讓您使用 XHTML 代碼建立自己的資料。URL 請使用 HTTP 或 HTTPS。用於文字小報告內容中的影像 (具備 HTTP 通訊協定) 將導致 IE 使用者接收有關混合內容的警告。使用其他通訊協定所包含的影像不會顯示在小報告中。
   **我的控制面板**

   列出您升級的控制面板，您可從中將內容移至新控制面板。

   **舊式控制面板**

   列出您可移動內容至新控制面板的共用控制面板。

   **共用控制面板**

   列出您可將內容移至新控制面板的舊式控制面板。 如果您想要保留舊版控制面板格式，舊式控制面板會很實用。

   **控制面板內容**

   顯示您已新增至控制面板的項目。

1. 按一下 **[!UICONTROL Save.]**

## 編輯控制面板和小報告資料 {#task_B460CCD70D9F40FCAC6BBC1C044CC460}

您可以變更控制面板或小報表層級的資料設定。 例如，您可以變更報表套裝、鎖定報表套裝、變更日期、套用區段等。 您也可以插入公司的機密陳述式，將HTML、XML、Web API和CSV資料加入自訂小報告中，以個人化控制面板。

<!-- 

t_dashboard_edit.xml

 -->

**若要編輯控制面板和小報告資料**

1. Click **[!UICONTROL Components]** > **[!UICONTROL Dashboards]** > *dashboard name* to open a dashboard.
1. 按一下 **[!UICONTROL Layout]**.

| 結束日期 | 執行此動作 |
|--- |--- |
| 變更控制面板的報表套裝 | 按一下Experience Cloud標題中的功能表，然後選取報表套裝。 |
| 變更小報告的報告套裝 | In the reportlet, click the report suite name, then select a report suite from the [!UICONTROL Report Suite] menu. |
| 將區段套用至控制面板 | 在Experience Cloud標題中，按一下 [!UICONTROL Show Segments]，然後選取區段。 |
| 將區段套用至小報告 | 在控制面板中，按一下配置來編輯控制面板。在小報告中，按一下報表套裝名稱，然後從「區段」欄位選取值，再按一下「更新」。 |
| 鎖定報表套裝（防止變更小報表中的報表套裝） | In the reportlet, click the report suite name, then enable [!UICONTROL Lock Report Suite]. 按一下「更新」。 |
| 變更報告日期 | 若是控制面板，按一下日曆(該控制面板中的所有小報告都會反映這項變更)。<br>若是小報告，按一下日期連結，然後設定日曆。 |
| 命名控制面板 | Open a dashboard, then click  [!UICONTROL More] >  [!UICONTROL Rename]. |
| 檢視控制面板封存檔 | 按一下  [!UICONTROL More] >  [!UICONTROL View Archive]. |
| 將控制面板設為著陸頁面 | 在控制面板中，按一下 [!UICONTROL More] > [!UICONTROL Set As Landing Page]。 |
| 下載控制面板 | In a dashboard, click  [!UICONTROL More] >  Download. |
| 列印控制面板 | In a dashboard, click  [!UICONTROL More] >  Print. |
| 儲存控制面板 | 在控制面板中，按一下另存新檔，然後指定名稱。 |

## 品牌結合控制面板 {#task_603BDE7700B945699AF5514C2DEB81F7}

說明如何上傳影像以在控制面板中顯示的步驟。

<!-- 

t_dashboard_branding.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]**.
1. 在頁面上 [!UICONTROL Company Settings] ，按一下 **[!UICONTROL Co-Brand the Adobe Experience Cloud]**。
1. 按一下 **[!UICONTROL Enable Co-Branding]**.
1. Browse to upload the image, then click **[!UICONTROL Save.]**

   為在瀏覽器中檢視影像時獲得最佳效果，請上傳100像素寬的30像素影像。 為獲得最佳的PDF輸出效果，請上傳417像素高、125像素高(300 dpi)的影像。 過大的影像會縮小為大小，同時保留長寬比。

## 搭配控制面板使用區段 {#concept_ED030C3713D54D03971FB7B209285750}

像Adobe Analytics中的大部分報表一樣，控制面板可以利用區段來擷取所需的資料。

<!-- 

segments_dashboards.xml

 -->

區段可以套用至兩個層級：套用至整個控制面板或特定報告。

* **小報告層級**:按一 **[!UICONTROL Layout]**&#x200B;下，然後是您要分段之小報表的報表套裝。 此時會出現一個模式視窗，可讓您新增或變更小報表使用的區段。
* **控制面板層級**：按一下左側導覽的「區段」圖示，勾選您要使用的區段，然後按一下「套用」。選取的區段會覆寫和取代任何小報表層級的區段。
