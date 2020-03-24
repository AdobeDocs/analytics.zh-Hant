---
description: 'null'
title: 部署整合
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署這項整合是一項簡單的程序，需要執行下列動作：

## 完成 Adobe 整合精靈{#completing-the-adobe-integration-wizard}

在 Data Connectors 介面中完成整合精靈的步驟。

1. 導覽至 Adobe Experience Cloud 中的 Data Connectors (前身為 Genesis) 區域。
1. 啟動 ContactLab 整合精靈。
1. 選擇所需的報表套裝，並替整合提供名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要連絡人的電子郵件地址 |
   | 說明 | (選用) 這項整合設定的說明 |

1. 設定下列&#x200B;**[!UICONTROL 變數對應]**&#x200B;項目：

   | 項目 | 說明 |
   |---|---|
   | 連結 ID | 選取要即時收集連結 ID 的 eVar。 |
   | 訊息 ID | 選取要即時收集訊息 ID 的 eVar。 |
   | 收件者 ID | 選取要即時收集收件者 ID 的 eVar。 |
   | 彈回數 | 選取數值事件，以從 ContactLab 接收每日跳出數。 |
   | 已傳送 | 選取數值事件，以從 ContactLab 接收每日傳送次數。 |
   | 已點按 | 選取數值事件，以從 ContactLab 接收每日點按總次數。 |
   | 已開啟 | 選取數值事件，以從 ContactLab 接收每日開啟總次數。 |
   | 已取消訂閱 | 選取數值事件，以從 ContactLab 接收每日取消訂閱次數。 |

1. 啟用資料存取並設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]**&#x200B;是您整合中包含的標準再行銷區段。
   1. 在&#x200B;**[!UICONTROL 「您的區段」]**&#x200B;下方，選取您要納入這項整合的任何自訂區段。您可以在管理面板下建立其他自訂區段。
   1. 在&#x200B;**[!UICONTROL 「存取要求」]**&#x200B;下方勾選方塊，以允許將產品資訊匯出至每日再行銷區段中的 ContactLab。
   1. 視需要重新命名計算量度。
   1. 設定您要透過手動更新 Analytics 收集代碼或使用自動化解決方案來收集 ID。如果您選取&#x200B;**[!UICONTROL 「自動化解決方案」]**，則您必須包含用於電子郵件連結的參數，才能傳遞 ID。
1. 檢閱所有設定項目，然後按一下&#x200B;**[!UICONTROL 「立即啟用」]**。

## 驗證整合{#verifying-the-integration}

在 Adobe Experience Cloud 中檢視您的 ContactLab 整合設定

1. 檢視整合活動記錄。
   1. 在 Adobe Experience Cloud中，導覽至&#x200B;**[!UICONTROL 「支援]** > **[!UICONTROL 整合活動記錄」]**。

      ![](assets/integration_activity_log.png)

   1. 尋找&#x200B;**[!UICONTROL 「成功匯入分類資料」]**、**[!UICONTROL 「成功匯入量度資料」]**、**[!UICONTROL 「成功匯出量度資料」]**&#x200B;等項目。這些項目應會在成功部署後 1 天內顯示。
1. 在 Adobe Analytics 中檢視您的報表資料。
   1. 導覽至&#x200B;**[!UICONTROL 「自訂轉換]** > **[!UICONTROL 自訂轉換 1-10]** > **[!UICONTROL 訊息 ID 報表」]**。

      ![](assets/reporting.png)

   1. 尋找 ContactLab 報表。這項資料應會在成功部署後 24 到 48 小時內顯示。
