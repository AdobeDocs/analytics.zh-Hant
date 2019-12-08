---
description: 'null'
title: 部署整合
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署此整合程式很簡單，包括完成Adobe整合精靈並驗證整合。

## 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

在「資料連接器」介面中完成整合精靈的步驟。

1. 導覽至Adobe Experience cloud中的「資料連接器」（先前稱為Genesis）區域。
1. 啟動「動態信號」整合精靈。
1. 選擇所要的報表套裝，並提供整合的名稱。
1. 設定下列項目：

   | 項目 | 說明 |
   |---|---|
   | 電子郵件地址 | 主要聯繫人的電子郵件地址。 |
   | 說明 | （可選）此整合設定的說明。 |
   | 社群ID | 您可以從動態信號代表取得此ID。 |

1. 設定下列 **[!UICONTROL 變數映射]** 項目：

   | 項目 | 說明 |
   |---|---|
   | 追蹤代碼 | 從報表套裝中選取可用的eVar變數。 |

1. 檢視將針對此整合建立的分類。
1. 核取此方塊以建立動態訊號整合控制面板（選用，但強烈建議使用）。
1. 檢閱所有設定項目，然後按一 **[!UICONTROL 下立即啟動]**。
1. **重要**:完成嚮導後，您必須通知動態信號代表，以便他們能夠激活VoiceStorm平台上的整合。

## 驗證整合{#verifying-the-integration}

在Adobe Experience cloud中檢視動態訊號VoiceStorm整合設定的步驟

1. 在整合活動記錄中檢視您的動態訊號整合設定。
   1. 在Adobe Experience cloud中，導覽至「支援 **[!UICONTROL &gt;整]** 合活動記錄」 **** 。

      ![](assets/integration_activity_log.png)

   1. 尋找成功匯入 **[!UICONTROL 分類資料等項目]**。 這些項目應會在成功部署後的24小時內顯示。
1. 使用「儀表板」在Adobe Analytics中檢視動態訊號報表，儀表板是使用Adobe Integration精靈自動為您建立的（步驟7）。 或者，您也可以導覽至Adobe Analytics功能表結構內的「動態訊號」報表——請參閱下列螢幕擷取畫面。

   **注意**:在成功部署後的24-48小時內應會顯示此資料。

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
