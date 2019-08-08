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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Marketing Cloud中的「資料連接器」(先前稱為Genesis)區域。
1. 啓動ContactLab整合精靈。
1. 選擇所需的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯絡人的電子郵件地址 |
   | 說明 | (可選)此整合設定的說明 |

1. 設定下列 **[!UICONTROL 變數映射]** 項目：

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
   1. 在「 **[!UICONTROL 您的區段]**」下方，選取您要納入此整合的任何自訂區段。您可以在管理面板下建立其他自訂區段。
   1. 在 **[!UICONTROL 「存取請求]**」下，核取方塊以允許在每日再行銷區段中匯出產品資訊至ContactLab。
   1. 視需要重新命名計算量度。
   1. 透過手動更新Analytics收集程式碼或使用自動化解決方案，設定您是否要收集ID。如果您選取 **[!UICONTROL 「自動化解決方案]**」，則必須包含電子郵件連結中使用的參數，以傳遞ID。
1. 檢閱所有組態項目，然後按一下 **[!UICONTROL 「立即啓動]**」。
