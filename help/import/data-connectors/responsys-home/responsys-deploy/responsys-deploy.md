---
description: 'null'
title: 部署整合
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署這項整合是一項簡單的程序，需要執行下列動作：

## 完成 Adobe 整合精靈{#completing-the-adobe-integration-wizard}

在 Data Connectors 介面中完成整合精靈的步驟。

1. 導覽至 Adobe Experience Cloud 中的 Data Connectors (前身為 Genesis) 區域。
1. 啟動 Responsys 整合精靈。
1. 選擇所需的報表套裝，並替整合提供名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要連絡人的電子郵件地址 |
   | 說明 | (選用) 這項整合設定的說明 |
   | 帳戶 ID | 透過 support@responsys.com 聯絡 Responsys 支援團隊以取得 |

1. 設定下列&#x200B;**[!UICONTROL 變數對應]**&#x200B;項目：

   | 項目 | 說明 |
   |---|---|
   | 訊息 ID | 選取要即時收集訊息 ID 的 eVar。 |
   | 收件者 ID | 選取要即時收集收件者 ID 的 eVar。 |
   | 總跳出數 | 選取一個數值事件，用於接收來自 Responsys 的每日跳出數。 |
   | 已傳送電子郵件 | 選取一個數值事件，用於接收來自 Responsys 的每日傳送數。 |
   | 已點按 | 選取一個數值事件，用於接收來自 Responsys 的每日總點按次數。 |
   | 已開啟 | 選取一個數值事件，用於接收來自 Responsys 的每日總開啟次數。 |
   | 已取消訂閱 | 選取一個數值事件，用於接收來自 Responsys 的每日取消訂閱數。 |
   | 已傳遞 | 選取一個數值事件，用於接收來自 Responsys 的每日交付數。 |

1. 啟用資料存取並設定資料收集。
   1. 視需要重新命名分類。
   1. **[!UICONTROL 合作夥伴區段]**&#x200B;是您整合中包含的標準再行銷區段。
   1. 在&#x200B;**[!UICONTROL 存取要求]**&#x200B;下方核取方塊，允許將產品資訊匯出至 Responsys 的每日再行銷區段。
   1. 設定您要透過手動更新 Analytics 收集代碼或使用自動化解決方案來收集 ID。如果您選取&#x200B;**[!UICONTROL 「自動化解決方案」]**，則您必須包含用於電子郵件連結的參數，才能傳遞 ID。
1. 檢閱所有設定項目，然後按一下&#x200B;**[!UICONTROL 「立即啟用」]**。

## 在 Responsys 系統中進行設定{#configuring-within-the-responsys-system}

若要啟動整合，需聯絡 Responsys 支援。

完成整合精靈後，您必須在 Responsys 中啟用整合。

若要啟動整合，請透過 support@responsys.com 聯絡 Responsys 支援團隊。
