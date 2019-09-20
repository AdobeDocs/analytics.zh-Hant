---
description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-title: 完成Adobe整合精靈
solution: Analytics
title: 完成Adobe整合精靈
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

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
   | 連結 ID | 選取eVar以即時收集連結ID。 |
   | 訊息ID | 選取eVar以即時收集訊息ID。 |
   | Recipient ID | 選取eVar，即時收集收件者ID。 |
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
   1. 設定您要透過手動更新Analytics收集代碼或使用自動化解決方案來收集ID。 如果您選取「 **[!UICONTROL 自動化解決方案]**」，則必須包含用於電子郵件連結中的參數，才能傳遞ID。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。
