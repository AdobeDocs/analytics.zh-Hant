---
description: 三種 Report Builder 登入方法的相關資訊。
title: 登入 Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 70%

---


# 登入 Report Builder

>[!IMPORTANT]
>
>報告建立工具5.6.47版及更新版本僅支援Experience Cloud登入，不支援舊版登入，例如Site Catalyst單一登入或標準登入。 到2021年4月30日，所有Report Builder使用者都必須將Report Builder增益集更新至5.6.47版或更新版本，其中包含登入程式的重要更新。

若要登入報告建立工具，請使用您的Experience Cloud登入帳戶。

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

Experience Cloud 登入可讓您使用 Enterprise ID (電子郵件與密碼) 來登入 Adobe Experience Cloud。按一下&#x200B;**[!UICONTROL 「登入]** > **[!UICONTROL 使用 Enterprise ID 登入」]**，系統會將您重新導向至貴公司的單一登入頁面。如需 Enterprise ID 的詳細資訊，請按一下[這裡](https://helpx.adobe.com/tw/enterprise/kb/enterprise-id-faq.html#whatis)。

![](assets/adobe_id_login.png)

>[!NOTE]
>
> Experience Cloud 登入是以工作階段為準，代號會在 30 天後過期。

## 登入 Report Builder

若要登入報告建立工具

1. 在 Excel 中按一下&#x200B;**[!UICONTROL 「增益集」]**。
1. 按一下&#x200B;**[!UICONTROL 登入]**。其他讓您登入的動作包括：

   * 按一下 **[!UICONTROL 建立]**。
   * [在「請求管理員」中選取請求](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md)，然後按一下「 **** 新增 **[!UICONTROL 管理」]**。
   * 在Excel中按兩下請求。

1. 填寫[!UICONTROL 「登入」]頁面中的欄位，然後按一下&#x200B;**[!UICONTROL 「確定」]**。

## 舊版登入類型

>[!IMPORTANT]
>
>到2021年4月30日，舊版登入類型將無法運作。 所有Report Builder使用者都必須將Report Builder增益集更新至5.6.47版或更新版本，其中包含登入程式的重要更新。 **報告建立工具5.6.47版及更新版本僅支援Experience Cloud登入，不支援舊版登入，例如標準登入或Site Catalyst單一登入。**

<!-- ![](assets/login_screen.png) -->

* [標準](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Site Catalyst單一登入](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## 標準 {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

如果您想使用 Adobe Analytics 憑證登入 Report Builder，請使用這個登入選項。

**Report Builder 登入 – 欄位定義**

| 欄位 | 定義 |
|--- |--- |
| 公司 | 用於 Adobe Analytics 的公司登入憑證。 |
| 使用者名稱 | 用於 Adobe Analytics 的使用者名稱登入。使用者的排程任務會與使用者名稱連結。如果您以相同的登入憑證登入 Report Builder，將可從任何電腦檢視排程任務。 |
| 密碼 | 您的 Analytics 密碼。 |
| 記住我 | 登入資訊會經過加密，並儲存在安裝 Report Builder 的機器上的使用者設定檔內。由於登入資訊會儲存在電腦中，因此使用同一台電腦的報表建立者在開啟含報表的試算表時，都能重新整理和編輯資料。如果您與其他使用者共用電腦且想要維持試算表資料的隱私，請勿啟用此選項。若要停用自動登入設定，請按一下工具列中的&#x200B;**[!UICONTROL 「請使用其他憑證登入」]**，並停用&#x200B;**[!UICONTROL 「記住我」]**。 |
| 使用代理伺服器 | 如果您透過代理伺服器存取網際網路且必須提供代理使用者名稱和密碼，請啟用此選項。 |

## 單一登入 {#section_6970A5F926774976B85FFE576610E85F}

此 (舊版) 單一登入只能讓您登入 Adobe Analytics，無法登入整個 Experience Cloud。

您也可以輸入網域，系統會辨別網域並將您重新導向至貴公司的單一登入頁面，以讓您登入 Adobe Analytics。
