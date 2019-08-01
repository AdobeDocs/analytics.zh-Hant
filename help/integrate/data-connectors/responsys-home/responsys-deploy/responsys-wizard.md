---
description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-description: 在「資料連接器」介面中完成整合精靈的步驟。
seo-title: 完成Adobe整合精靈
solution: Analytics
title: 完成Adobe整合精靈
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Marketing Cloud中的「資料連接器」(先前稱為Genesis)區域。
1. 啓動Responsys整合精靈。
1. 選擇所需的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯絡人的電子郵件地址 |
   | 說明 | (可選)此整合設定的說明 |
   | 帳戶ID | 聯絡Responsys支援團隊，網址為support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | 項目 | 說明 |
   |---|---|
   | 訊息ID | 選取即時收集訊息ID的eVar。 |
   | Recipient ID | 選取即時收集收件者ID的eVar。 |
   | 彈回數總計 | 選取要接收Responsys每日反彈的數值事件。 |
   | 電子郵件已傳送 | 選取每日從Responsys接收的數值事件。 |
   | 點按 | 選取數值事件，以接收來自Responsys的每日點按次數。 |
   | 已開啓 | 選取要接收來自Responsys的每日總開啓次數的數值事件。 |
   | 取消訂閱 | 選取要接收來自Responsys每日取消訂閱的數值事件。 |
   | 遞送內容 | 選取由Responsys每日接收的數值事件。 |

1. 啓用資料存取及設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]** 是整合中包含的標準再行銷區段。
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. 透過手動更新Analytics收集程式碼或使用自動化解決方案，設定您是否要收集ID。If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
