---
description: Workspace 中的專案共用和專案角色
keywords: Analysis Workspace 共用
title: 共用專案
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 58abc4a8410441a3c76c6737ace8e2c5ab5c1374
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 49%

---

# 共用專案

您可以與組織中現有的Adobe Analytics使用者或群組共用專案。 如本節所述，當您共用專案時，您與共用的使用者必須已有Adobe Analytics帳戶。

您可以與使用者或群組共用特定角色，也可以共用連結。

* [共用特定專案角色](#share-a-specific-project-role)

* [共用專案的連結](#share-a-link-to-a-project)

## 共用特定專案角色

與組織中的使用者和群組共用特定專案角色時，請考慮下列事項：

* 專案角色(**[!UICONTROL 可編輯]**, **[!UICONTROL 可複製]**，和 **[!UICONTROL 可檢視]**)會系結至使用者和特定專案ID。 專案角色不受 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中管理的使用者權限影響。

* 在 Adobe Analytics 中，群組由 [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 中的產品設定檔所定義。管理員可以共用給任何群組，包括「全部」。 非管理員可以與其所屬的任何群組共用，但「全部」除外。

* 被安排多個角色的使用者一律會獲得最高的體驗。 如果將使用者新增為個人和群組的一部分，就可能會發生此情況。 例如，如果使用者獲得 **[!UICONTROL 可編輯]** 角色 **[!UICONTROL 可檢視]** 作為群組成員的角色，他們將獲得 **[!UICONTROL 可編輯]** 專案體驗。

* 管理員 **[!UICONTROL 可複製]** 或 **[!UICONTROL 可檢視]** 角色在開啟專案時會獲得這些有限的體驗。 如有需要，管理員可隨時透過&#x200B;**[!UICONTROL 元件] > [!UICONTROL 專案]**&#x200B;將其角色增加到&#x200B;**[!UICONTROL 可編輯]**&#x200B;中。

若要與組織中的使用者或群組共用特定專案角色：

1. 前往您要共用的專案，然後按一下 **[!UICONTROL 共用]** > **[!UICONTROL 共用專案]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
如果有未儲存的變更，系統會提示您先儲存專案。

   ![](assets/share-proj-modal.png)

   如需如何同時共用多個專案的詳細資訊，請參閱 [在專案管理員中共用專案](#share-projects-in-the-project-manager).

1. 在提供的角色欄位之一中新增收件者或收件者群組：

   **可以編輯：** 收件者可以 **[!UICONTROL 儲存]** 專案的變更，並以共同擁有者的身分運作。 如果您想要與其他同事共同管理專案，此角色將有其效用；包括編輯、刪除和修改共用專案的收件者清單。<br>注意：Analysis Workspace 目前不支援即時共同作業，因此我們建議不要有多名使用者同時編輯一個專案。如果同時儲存專案，將會保留最後一個版本。

   **可複製：** 收件者可以 **[!UICONTROL 另存新檔]** 並可存取左側邊欄。 此角色的專案互動不受限制。如果您想要與了解組織資料以及如何使用Analysis Workspace的使用者共用專案，但您不想讓專案遭到變更，這個角色就十分實用。

   **可檢視：** 收件者不能 **[!UICONTROL 儲存]** 或 **[!UICONTROL 另存新檔]** 且無法存取左側邊欄。 專案互動也有所限制。如果您想要與整體上較不熟悉您組織資料結構(Analysis Workspace或Adobe Analytics)的使用者共用專案，此角色就十分實用。 但您仍希望他們能在安全的環境中使用資料和深入分析。深入瞭解[可檢視專案體驗](/help/analyze/analysis-workspace/curate-share/view-only-projects.md)。

1. 選擇是否在共用專案時啟用下列選項：

   * **共用內嵌的專案元件：** 與所有收件者共用區段、計算量度和日期範圍。 共用後，這些元件會出現在收件者 Workspace 的「元件」下拉式清單中。此設定不會持續存在 — 這是共用時的一次性動作。

   * **設為收件者的登陸頁面：** 將此頁面設為收件者的登陸頁面。 此設定不會持續存在 — 這是共用時的一次性動作。

1. 按一下 **[!UICONTROL 共用]**。您也可以按一下&#x200B;**[!UICONTROL 監管與共用]**&#x200B;自動套用專案組織。如果專案已共用，這些按鈕將會顯示&#x200B;**[!UICONTROL 更新]**&#x200B;和&#x200B;**[!UICONTROL 監管與更新]**。深入瞭解[專案組織](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=zh-Hant)。

## 共用專案的連結

依照本節所述來共用連結時，請考量下列事項：

* 使用連結的收件者必須先登入Adobe Analytics，才能取得專案的存取權。

* 如果收件者未獲指派角色，且收到 [連結](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=zh-Hant) 至專案(**[!UICONTROL 共用] > [!UICONTROL 取得專案連結]**)，則預設會獲得角色。 管理員會獲得&#x200B;**[!UICONTROL 可編輯]**&#x200B;角色，非管理員會獲得&#x200B;**[!UICONTROL 可複製]**&#x200B;角色。

若要與組織中的使用者共用專案連結：

1. 按一下&#x200B;**[!UICONTROL 共用]** > **[!UICONTROL 共用專案]**。
<!-- recommned changing "Share project" to "Share project internally" or something like that -->
如果有未儲存的變更，系統會提示您先儲存專案。

   ![](assets/share-proj-modal.png)

1. 按一下 **[!UICONTROL 複製連結]** 旁邊 **[!UICONTROL 共用URL欄位]**.

1. 與組織中的使用者共用連結。 例如，您可以將其貼入電子郵件、貼到內部網站等。

## 在 Project Manager 中共用專案 {#Manager}

您也可以從&#x200B;**[!UICONTROL 元件] > [!UICONTROL 專案]**&#x200B;來共用專案。依照上述步驟操作，可共用單一專案。如果選取了多個要共用的專案，收件者將會新增至每個專案的現有收件者清單。

例如：

* 專案 A 會與收件者 1、2、3 共用
* 專案 B 會與收件者 4、5、6 共用

在選取專案 A 和 B 後，收件者 4 和 7 會新增至共用清單。此時，每個專案新的共用清單分別為：

* 專案 A：1、2、3、4、7
* 專案 B：4、5、6、7

![](assets/mult-proj-sharing.png)

## 共用內嵌元件

以下是有關該主題的影片：

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## 常見問答 {#FAQs}

| 問題 | 回答 |
| --- | --- |
| 如果兩個編輯者同時儲存專案，會發生什麼情況？ | 不會合併變更，而會保留最後儲存的專案版本。Analysis Workspace 目前不支援即時共同作業。 |
| 身為管理員，我會有何種專案體驗？ | 設為&#x200B;**[!UICONTROL 可複製]**&#x200B;或&#x200B;**[!UICONTROL 可檢視]**&#x200B;角色的管理員，在開啟專案時將獲得這些有限的體驗。如有需要，管理員可隨時透過&#x200B;**[!UICONTROL 元件] > [!UICONTROL 專案]**&#x200B;將其角色增加到&#x200B;**[!UICONTROL 可編輯]**&#x200B;中。 |
| 如果某個收件者以個人身分設定於某個角色，又以群組成員身分設定於另一個角色，會發生什麼情況？ | 如果收件者獲得多個角色，將一律會有較高的體驗。例如，如果收件者以個人身分獲得&#x200B;**[!UICONTROL 可編輯]**&#x200B;角色，並且以群組成員身分獲得&#x200B;**[!UICONTROL 可檢視]**&#x200B;角色，則將獲得&#x200B;**[!UICONTROL 可編輯]**&#x200B;專案體驗。 |
| 如果收件者開啟了專案連結，將有何體驗？ | 收件者會獲得您在分享模式中為其設定的角色。收件者若未被指派任何角色，且收到專案的連結 (**[!UICONTROL 共用] > [!UICONTROL 取得專案連結]**)，將會獲得預設角色。管理員會獲得&#x200B;**[!UICONTROL 可編輯]**&#x200B;角色，非管理員會獲得&#x200B;**[!UICONTROL 可複製]**&#x200B;角色。 |
