---
description: 在 Analysis Workspace 中使用警報。
title: 警報產生器概觀
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 966bd9a05e6c344a62ce3f0b12df8a99ff3d7ece
workflow-type: ht
source-wordcount: '695'
ht-degree: 100%

---

# 建立警報 {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="時間詳細程度"
>abstract="時間詳細程度指的是警報的檢查頻率以及包含的內容"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>僅擁有 Adobe Analytics Prime 或 Ultimate 套件的組織才能使用具有異常偵測的警報 (也稱為 _智慧型警報_)。

Adobe Analytics 中的警報可讓您根據變更的百分比或特定資料點來接收通知。根據您的 Adobe Analytics 套件，您還可以使用根據異常臨界值觸發的警報。伺服器呼叫使用情況警報是另一種警報，僅供 Analytics 管理員使用。這些警報會通知您伺服器呼叫耗用量和承諾使用量資料有超額的風險或發生超額的情況。若需更多詳細資訊，請參閱[伺服器呼叫使用情況警報](/help/admin/admin/c-server-call-usage/scu-alerts.md)。

有關警報的更多詳細概觀資訊，請參閱[警報概述](/help/components/c-alerts/intellligent-alerts.md)。

若要建立警報：

1. 透過存取警報產生器開始建立警報。您可以透過以下任一方式存取警報產生器：

   * 在 Analysis Workspace 中開啟專案，然後選取「**[!UICONTROL 元件]**」>「**[!UICONTROL 建立警報]**」。
   * 在 Analysis Workspace 中開啟專案，然後使用以下快速鍵：***ctrl (或 cmd) + shift + a***。
   * 在 Analysis Workspace 中開啟專案，在自由格式表格中選取一個或多個條例項目，然後按一下右鍵並選取「**[!UICONTROL 從選取項目範圍建立警報]**」。此動作會立即預先填入警報產生器，以使用正確的量度和篩選器建立警報。
   * [從警報管理員](/help/components/c-alerts/alert-manager.md#create-alerts)建立警報。

   顯示警報產生器。此介面和在 Analytics 中建置區段或計算量度的介面相似：

   ![](assets/alert-builder.png)

1. 指定以下選項來設定警報：

   | 選項 | 說明 |
   |---------|----------|
   | [!UICONTROL **標題**] | 指定警報的名稱。警報名稱中可以包含報表的名稱或量度臨界值。 |
   | [!UICONTROL **說明 (可選)**] | 指定警報的說明。 |
   | [!UICONTROL **時間詳細程度**] | 選取您希望檢查量度的頻率：每小時、每日、每週或每月。<p><b>備註：</b>針對使用自訂行事曆的報告套裝，我們在警報產生器中不支援每月詳細程度。<!--true?--></p> |
   | [!UICONTROL **收件者**] | 指定可傳送警報的位置。警報可以傳送給 Analytics 用戶、Analytics 群組、原始電子郵件地址或電話號碼。<p><b>重要提示：</b>電話號碼前面必須加上 `+` 和[國家/地區代碼](https://countrycode.org/)。</p><p>一旦觸發警報，使用者收到的電子郵件顯示如下：</p><p>![](assets/alerts-email.PNG)</p> |
   | [!UICONTROL **過期日**] | 設定警報過期的日期和時間。 |
   | [!UICONTROL **傳送警報的時機**] | [!UICONTROL **這些量度中的任何一個均會觸發**]：將量度 (包括計算量度) 拖放至此處，以建立警報觸發程式。<p>如果並非所有警報中的量度、維度或區段均與目前選取資料檢視相容，系統會顯示&#x200B;**「不相容的元件」**&#x200B;訊息。</p><p>確定觸發警報前必須超過的量度臨界值。您可以將此值設為臨界值以及下列其中一個條件：</p><ul><li>存在異常</li><li>異常超出預期</li><li>異常低於預期</li><li>高於或等於</li><li>低於或等於</li><li>變更者</li><li>您可以設定 90%、95%、99%、99.75% 或 99.9% 的臨界值。</li></ul><p>[!UICONTROL **使用所有這些篩選器**]：拖放區段或維度以新增篩選器。例如，新增「僅限行動裝置」區段可以代表規則僅會針對行動裝置而觸發。您可以透過使用 AND 陳述式新增其他篩選器。您可按一下齒輪圖示，新增 AND 或 OR 規則。</p><p>例如，請參閱 [警報 - 使用案例](/help/components/c-alerts/alerts-use-cases.md)。</p> |
   | [!UICONTROL **預覽**] | 互動式警報預覽會根據過去經驗，顯示觸發警報的大約頻率。<p>例如，如果您將時間詳細程度設為每日，則預覽可告訴您在過去 30 或 31 天裡，針對特定量度觸發 x 次警報。預覽約略間範圍根據警報頻率設定建立。針對每日警報頻率，預覽時間範圍約為前 30 天。針對每週警報頻率，預覽時間範圍約為過去 12 週。針對每月警報頻率，預覽時間範圍約為前 12 個月。</p><p>如果您發現觸發警報次數過多，可在「[警報管理員](/help/components/c-alerts/alert-manager.md)」中調整臨界值。</p><p>![](assets/alert_preview.png)</p> |

1. 請選取「[!UICONTROL **儲存**]」。
