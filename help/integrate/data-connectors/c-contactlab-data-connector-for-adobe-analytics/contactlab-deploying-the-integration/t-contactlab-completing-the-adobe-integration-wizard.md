---
description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-title: 完成Adobe整合精靈
solution: Analytics
title: 完成Adobe整合精靈
uuid: a8135be3-fba3-436d-8959-faed40 b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Marketing Cloud中的「資料連接器」(先前稱為Genesis)區域。
1. 啓動ContactLab整合精靈。
1. 選擇所需的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯絡人的電子郵件地址 |
   | 說明 | (可選)此整合設定的說明 |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | 項目 | 說明 |
   |---|---|
   | 連結 ID | 選取即時收集連結ID的eVar。 |
   | 訊息ID | 選取即時收集訊息ID的eVar。 |
   | Recipient ID | 選取即時收集收件者ID的eVar。 |
   | 彈回數 | 選取數值事件，從ContactLab接收每日彈回數。 |
   | 已傳送 | 選取每日從ContactLab接收的數值事件。 |
   | 點按 | 選取數值事件，從ContactLab接收每日點按次數。 |
   | 已開啓 | 選取從ContactLab接收每日總開啓次數的數值事件。 |
   | 取消訂閱 | 選取數值事件，從ContactLab接收每日取消訂閱。 |

1. 啓用資料存取及設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]** 是整合中包含的標準再行銷區段。
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. 您可以在管理面板下建立其他自訂區段。
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to ContactLab in daily remarketing segments.
   1. 視需要重新命名計算量度。
   1. 透過手動更新Analytics收集程式碼或使用自動化解決方案，設定您是否要收集ID。If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
