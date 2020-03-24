---
description: 部署這項整合是一項簡單的程序，需要執行下列動作。
subtopic: Qualtrics
title: 部署整合
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 部署整合{#deploying-the-integration}

部署這項整合是一項簡單的程序，需要執行下列動作。

## 完成 Adobe 整合精靈{#completing-the-adobe-integration-wizard}

若要啟用整合，您必須在 Data Connectors 介面中完成 Qualtrics 整合精靈

1. 導覽至 Data Connectors 並啟動 Qualtrics 整合精靈。
1. 選取您要用於此整合的報表套裝，並提供名稱。

   完成整合精靈，提供下列步驟所述的資訊。1. **精靈步驟 1**

   | 電子郵件地址 | 主要連絡人電子郵件地址。 |
   |---|---|
   | 說明 | (選用) 此整合設定的說明。 |
   | Qualtrics 組織 ID | [查詢您的 Qualtrics 組織 ID](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst 代號 | [產生您的 Qualtrics Adobe Analytics 代號](../qualtrics-overview/qualtrics-token.md) |

1. **精靈步驟2 - 變數對應**
|  Qualtrics 回應清單  | 從報表套裝中選取可用的清單變數。(您可能需要在報表套裝管理器中啟用新的 listVar。)|
|---|---|
|  Qualtrics 回應 ID  | 從報表套裝中選取可用的 eVar 或 Prop。(您可能需要在報表套裝管理器中啟用新的 listVar。)|
|  追蹤伺服器  | 提供您用來追蹤 Adobe Analytics 資料的追蹤伺服器 (網域) 設定。如果 `trackingServerSecure` 追蹤伺服器與標準追蹤伺服器設定不同，請使用該追蹤伺服器。|
|  Qualtrics 調查提交  | 從報表套裝中選取可用事件 (您可能需要從報表套裝管理器中啟用新事件)。  |

1. **精靈步驟 3**：不需要任何操作，僅提供資訊。

   步驟結果 1。**精靈步驟 4 - 匯出設定**

   | eVar | 選取最多 5 個要開放匯出至 Qualtrics 的 eVar |
   |---|---|
   | 事件 | 選取最多 5 個要開放匯出至 Qualtrics 的自訂事件 |
   | Prop | 選取最多 5 個要開放匯出至 Qualtrics 的 Prop |
   | 存取要求 | 勾選方塊，選取您要匯出至 Qualtrics 的任何標準量度和維度。須有 `visitor_id` 匯出功能才能正常運行。 |

1. **精靈步驟 5**：檢閱設定，然後按一下&#x200B;**[!UICONTROL 「立即啟用」]**。

## 啟用 Qualtrics Research Suite 中的整合{#enabling-the-integration-in-qualtrics-research-suite}

完成整合精靈後，您必須為每個要連接的 Qualtrics 調查啟用整合。

1. 登入 Qualtrics Research Suite。
1. 在&#x200B;**[!UICONTROL 「我的調查」]**&#x200B;標籤上，按一下您要整合之調查的&#x200B;**[!UICONTROL 「編輯」]**&#x200B;按鈕。
1. 按一下&#x200B;**[!UICONTROL 「進階選項」]**&#x200B;功能表，然後選取&#x200B;**[!UICONTROL 「Adobe Analytics」]**。(如果沒有看到此選項，請詢問您的管理員如何取得所需權限)。

   ![](assets/advanced_options.png)

1. 選取「Adobe Analytics 設定」，然後按一下&#x200B;**[!UICONTROL 「儲存」]**。如果沒有可用的設定，表示您可能尚未完成 Adobe 整合精靈。
   1. **[!UICONTROL 包含部分回應]**&#x200B;核取方塊可用來指定您希望在每個部分調查畫面完成後，將資料擷取至 Adobe Analytics 中。如果沒有勾選此方塊，則只會為全部完成的調查傳送資料。
   1. 只有在與已設為接收時間戳記資料的報表套裝 (不常見) 整合時，才應使用&#x200B;**[!UICONTROL 傳送含信標的時間戳記]**&#x200B;核取方塊。
   ![](assets/integration_config.png)

## 驗證整合{#verifying-the-integration}

完成所有部署步驟後，可以驗證整合是否能成功傳輸資料。

1. **整合活動記錄**：在 Data Connectors UI 中，檢視 Qualtrics 整合上的&#x200B;**[!UICONTROL 支援]**&#x200B;標籤。在&#x200B;**[!UICONTROL 整合活動記錄]**&#x200B;標題下，應該會看到指出已匯入成功分類資料的項目。

   >[!NOTE]
   >
   >這些項目應會在成功部署後 1 小時內顯示。

   ![](assets/verify-1.png)

1. **報表資料**：導覽 Qualtrics 調查報表 (在&#x200B;**[!UICONTROL 清單變數]**&#x200B;底下)，使用 Marketing Reports &amp; Analytics UI 檢視您的 Qualtrics 調查報表。

   >[!NOTE]
   >
   >假設整合式調查正在主動接收回應，此資料應會在部署成功後 24-48 小時內顯示。

   ![](assets/verify-2.png) ![](assets/verify-3.png)


