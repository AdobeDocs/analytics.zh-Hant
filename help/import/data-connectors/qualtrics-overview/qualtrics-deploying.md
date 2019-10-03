---
description: 部署此整合是一個簡單的程式，需要執行下列動作。
seo-description: 部署此整合是一個簡單的程式，需要執行下列動作。
seo-title: 部署整合
solution: Analytics
subtopic: Qualtrics
title: 部署整合
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfef09
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# 部署整合{#deploying-the-integration}

部署此整合是一個簡單的程式，需要執行下列動作。

## 完成Adobe整合精靈{#completing-the-adobe-integration-wizard}

若要啟動整合，您必須在「資料連接器」介面中完成Qualtrics整合精靈

1. 導覽至資料連接器並啟動Qualtrics整合精靈。
1. 選取您要用於此整合的報表套裝，並提供名稱。

   完成整合精靈，提供下列步驟所述的資訊。 1.精 **靈步驟1**

   | Email Address | 主要聯絡人電子郵件地址。 |
   |---|---|
   | 說明 | （可選）此整合設定的說明。 |
   | Qualtrics組織ID | [尋找您的Qualtrics組織ID](../qualtrics-overview/qualtrics-org-id.md) |
   | Adobe SiteCatalyst Token | [產生您的Qualtrics Adobe Analytics Token](../qualtrics-overview/qualtrics-token.md) |

1. **精靈步驟2 —— 變數映射**| Qualtrics回應清單|從您的報表套裝中選取可用的清單變數。 （您可能需要在「報表套裝管理員」中啟用新的listVar。）||—|—|| Qualtrics回應ID|從報表套裝中選取可用的eVar或prop。 （您可能需要在「報表套裝管理員」中啟用新的listVar。）||追蹤伺服器|提供您用來追蹤Adobe Analytics資料的追蹤伺服器（網域）設定。 如果追蹤 `trackingServerSecure` 伺服器與標準追蹤伺服器設定不同，請使用它。  || Qualtrics調查提交|從報表套裝中選取可用事件（您可能需要從報表套裝管理員中啟用新事件）。  |

1. **精靈步驟3**:不需要，僅提供資訊。

   步驟結果1. **精靈步驟4 —— 匯出設定**

   | eVar | 選取最多5個eVar以供匯出至Qualtrics時公開 |
   |---|---|
   | 事件 | Select up to five of your custom events to expose for exporting to Qualtrics |
   | Prop | Select up to five of your Props to expose for exporting to Qualtrics |
   | Access Requests | Check the box for any of the standard metrics and dimensions that you wish to export to Qualtrics. The  is required to allow the export to function properly.`visitor_id` |

1. **Wizard Step 5**: Review configuration and then click **[!UICONTROL Activate Now]**.

## Enabling the Integration in Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

After completing the integration wizard, you must activate the integration for each Qualtrics survey that you want connected.

1. Log in to the Qualtrics Research Suite.
1. On the My Surveys tab, click the Edit button for the survey that you want to integrate.********
1. Click the **[!UICONTROL Advanced Options]** menu and select **[!UICONTROL Adobe Analytics]**. (if you do not see this option, ask your administrator about gaining the permissions required).

   ![](assets/advanced_options.png)

1. Select the Adobe Analytics Configuration, then click Save. **** If no configurations are available then you likely have not yet completed the Adobe Integration Wizard.
   1. 「包 **[!UICONTROL 含部分回應]** 」核取方塊可用來指示您希望在每個部分調查畫面完成後，將資料擷取至Adobe Analytics。 If not checked, then data is transferred only for fully completed surveys.
   1. 只 **** 有在與已設定為接收時間戳記資料（非常用）的報表套裝整合時，才應使用「傳送含信標的時間戳記」核取方塊。
   ![](assets/integration_config.png)

## 驗證整合{#verifying-the-integration}

完成所有部署步驟後，您可以驗證整合是否成功傳輸資料。

1. **整合活動記錄**:在「資料連接器UI」中，檢視Qualtrics整 **[!UICONTROL 合的]** 「支援」標籤。 在「整合活 **[!UICONTROL 動記錄」標題下]** ，您應看到指出成功匯入分類資料的項目。

   >[!NOTE]
   >
   >這些項目應會在成功部署後1小時內顯示。

   ![](assets/verify-1.png)

1. **報告資料**:導覽Qualtrics調查報表（在「清單變數」下），以行銷報告與分析UI檢 **[!UICONTROL 視您的Qualtrics調查報表]**。

   >[!NOTE]
   >
   >假設整合式調查正在積極接收回應，此資料應會在部署成功24-48小時內顯示。

   ![](assets/verify-2.png) ![](assets/verify-3.png)


