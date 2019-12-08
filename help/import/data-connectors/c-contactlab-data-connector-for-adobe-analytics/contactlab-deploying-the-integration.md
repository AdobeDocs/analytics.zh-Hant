---
description: 'null'
title: 部署整合
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署此整合是一個簡單的程式，需要執行下列動作：

## 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Experience cloud中的「資料連接器」（先前稱為Genesis）區域。
1. 啟動ContactLab整合嚮導。
1. 選擇所要的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯繫人的電子郵件地址 |
   | 說明 | （可選）此整合設定的說明 |

1. 設定下列 **[!UICONTROL 變數映射]** 項目：

   | 項目 | 說明 |
   |---|---|
   | 連結 ID | 選取要即時收集連結ID的eVar。 |
   | 訊息ID | 選取要即時收集訊息ID的eVar。 |
   | Recipient ID | 選取要即時收集收件者ID的eVar。 |
   | 彈回數 | 選擇數值事件，從ContactLab接收每日彈回數。 |
   | 已傳送 | 選擇要接收ContactLab每日發送的數值事件。 |
   | 已點按 | 選擇數值事件，以接收ContactLab的每日點按總數。 |
   | 已開啟 | 從ContactLab選取要接收每日開機總數的數值事件。 |
   | 取消訂閱 | 選擇一個數值事件，從ContactLab接收每日取消訂閱。 |

1. 啟用資料存取和設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]** ，是整合中包含的標準再行銷區段。
   1. 在「 **[!UICONTROL 您的區段]**」下方，選取您要納入此整合的任何自訂區段。 您可以在管理面板下建立其他自訂區段。
   1. 在「 **[!UICONTROL 存取請求]**」下方，核取此方塊，允許將產品資訊匯出至每日再行銷區段中的ContactLab。
   1. 視需要重新命名計算量度。
   1. 設定您要透過手動更新Analytics收集代碼或使用自動化解決方案來收集ID。 如果您選 **[!UICONTROL 取「自動化解決方案]**」，則必須包含用於電子郵件連結的參數，才能傳遞ID。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。

## 驗證整合{#verifying-the-integration}

在Adobe Experience cloud中檢視您的ContactLab整合設定

1. 檢視整合活動記錄。
   1. 在Adobe Experience cloud中，導覽至「支援 **[!UICONTROL &gt;整]** 合活動記錄」 ****。

      ![](assets/integration_activity_log.png)

   1. 尋找成功匯入 **[!UICONTROL 分類資料、成功匯入]**&#x200B;量度資料 **[!UICONTROL 、成功匯]**&#x200B;出量度資料等項目 ****。 這些項目應會在成功部署的1天內顯示。
1. 在Adobe Analytics中檢視您的報告資料。
   1. 導覽至「 **[!UICONTROL 自訂轉換]** &gt;自 **[!UICONTROL 訂轉換1-10]** &gt;訊息 **[!UICONTROL ID報表」]**。

      ![](assets/reporting.png)

   1. 尋找ContactLab報告。 在成功部署後的24-48小時內應會顯示此資料。
