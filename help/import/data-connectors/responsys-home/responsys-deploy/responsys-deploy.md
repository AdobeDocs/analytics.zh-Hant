---
description: 'null'
title: 部署整合
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署此整合是一個簡單的程式，需要執行下列動作：

## 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Experience cloud中的「資料連接器」（先前稱為Genesis）區域。
1. 啟動Responsys整合精靈。
1. 選擇所要的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯繫人的電子郵件地址 |
   | 說明 | （可選）此整合設定的說明 |
   | 帳戶ID | 聯絡Responsys支援團隊，取得網址：support@responsys.com |

1. 設定下列 **[!UICONTROL 變數映射]** 項目：

   | 項目 | 說明 |
   |---|---|
   | 訊息ID | 選取要即時收集訊息ID的eVar。 |
   | Recipient ID | 選取要即時收集收件者ID的eVar。 |
   | 總彈回數 | 選取要從Responsys接收每日彈回數的數值事件。 |
   | 電子郵件已傳送 | 選擇要接收Responsys每日傳送的數值事件。 |
   | 已點按 | 選擇數值事件，以接收Responsys的每日點按總數。 |
   | 已開啟 | 選擇從Responsys接收每日開啟總數的數值事件。 |
   | 取消訂閱 | 選取要從Responsys接收每日取消訂閱的數值事件。 |
   | 交付 | 選擇數值事件，以接收Responsys的每日傳送。 |

1. 啟用資料存取和設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]** ，是整合中包含的標準再行銷區段。
   1. 在「 **[!UICONTROL 存取請求]**」下方，核取此方塊，允許將產品資訊匯出至每日再行銷區段中的Responsys。
   1. 設定您要透過手動更新Analytics收集代碼或使用自動化解決方案來收集ID。 如果您選 **[!UICONTROL 取「自動化解決方案]**」，則必須包含用於電子郵件連結的參數，才能傳遞ID。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。

## 在Responsys系統中配置{#configuring-within-the-responsys-system}

啟動整合需要聯絡Responsys支援。

完成整合精靈後，您必須在Responsys中啟動整合。

若要這麼做，請聯絡Responsys支援團隊，來信請寄至support@responsys.com。
