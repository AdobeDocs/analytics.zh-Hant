---
title: Adobe Analytics中的管理員角色
description: 瞭解如何開始使用 Adobe Analytics、一般角色類型有哪些，以及如何登入 UI。
feature: Admin Tools
source-git-commit: 7cde90a15dc97468a70f8120bec46915eab7c1bb
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 58%

---

# Adobe Analytics中的管理員角色

Adobe Analytics支援各種類型的管理員。 完整的Adobe Analytics管理員可存取Adobe Analytics中的所有功能，而其他管理員和使用者則可執行更專業的工作。

>[!NOTE]
>
>在Adobe Analytics中，必須先將使用者指派為Experience Cloud中的第一個管理員，才能為任何使用者指派角色。 然後，第一個管理員就可以將組織中的使用者布建為其他關鍵角色，如本文所述。 如需第一個管理員的詳細資訊，請參閱 [Adobe Analytics第一份管理指南](/help/admin/admin-console/first-admin-guide.md).


## Experience Cloud和Adobe Analytics中的關鍵角色

使用Adobe Analytics時，請考量下列關鍵角色：

* **完整的Adobe Analytics管理員：** 這些使用者可完整存取Adobe Analytics中的所有項目，包括報表套裝設定和使用者權限。 根據組織結構而定，Analytics 管理的不同層面可能會交由不同的人員或團隊負責。例如，某人負責指定要在實施作業過程中使用哪些變數，另一人則可負責確認每個人都擁有正確的權限，以便讓使用者能夠正確提取報表。請至少指定一名使用者負責 Analytics 報表套裝設定和使用者權限，該人員可再從 Analytics 中邀請其他人成為管理員。
* **資料收集管理員：** 這些使用者可完整存取Adobe Experience Platform資料收集中的所有項目，包括發佈權限、建立容器和使用者權限。 這類使用者不必非程式設計人員不可，但如果至少具備 HTML、CSS 和 JavaScript 的新手知識，則會很有幫助。 他們負責與貴組織的網站擁有者合作，在您的網站上實作標籤。 請至少確定一個使用者來負責貴組織的實作，該使用者可以從這裡邀請其他資料收集管理員。
* **產品設定檔管理員：** 這些使用者可以新增或移除使用者至產品設定檔、調整其產品設定檔中的權限項目，以及指派或移除產品設定檔至使用者群組。 產品設定檔管理員無法完整存取Adobe Analytics。 不過，對於需要授予及管理其團隊存取權的團隊領導或經理而言，這些權限是理想的選擇。 如需產品設定檔的詳細資訊，請參閱 [Adobe Analytics的產品設定檔](/help/admin/admin-console/permissions/product-profile.md).
* **支援委派**：也稱為受支援使用者，他們在 Analytics 介面中沒有額外的權限。而是當他們與 Adobe 客戶服務溝通時，會獲得額外的權限。這些使用者幾乎永遠都是 Analytics 管理員，因為可協助客戶服務疑難排解他們的問題。請至少找出一位負責協助使用者與 Adobe 客戶服務互動的 Analytics 管理員。
* **網站負責人**：這類人員或團隊需負責網站的編碼和開發。 他們不需要帳戶，但他們會想要與資料收集管理員合作，以取得標記程式碼，並在您的網站上實作這些程式碼。
* **一般使用者**：這類使用者通常只需要檢視報表，並針對業務問題尋求解答。Analytics 管理員可向這些使用者授與在產品中進行操作的權限。

## 授予Analytics的完整產品管理員存取權

系統層級管理員無法直接存取產品；但是，他們可以將自己新增為產品層級管理員，以提供存取權。

為Adobe Analytics提供您自己或他人的存取權：

1. 使用您的 Adobe ID 認證登入 [Admin Console](https://adminconsole.adobe.com/)。
1. 按一下上方的「**[!UICONTROL 產品]**」索引標籤。 貴組織購買的所有產品都位於左側。 按一下 **[!UICONTROL Adobe Analytics]**，然後按一下 **[!UICONTROL 新設定檔]** 按鈕。
1. 將此設定檔命名為「Analytics完整管理員存取權」，然後按一下 **[!UICONTROL 下一個]** > **[!UICONTROL 儲存]**.
1. 返回「產品描述檔」頁面，按一下新建的描述檔，然後按一下「**[!UICONTROL 權限]**」索引標籤。
1. 按一下其中一個權限細項。 如果可使用「**[!UICONTROL 自動加入]**」，則啟用它。 若 **[!UICONTROL 自動包含]** 無法使用，請按一下 **[!UICONTROL 全部新增]**. 這兩個選項都會將所有權限項目移至右欄。
1. 按一下「**[!UICONTROL 儲存]**」。對所有權限類別重複上述步驟。
1. 將所有權限類別授予設定檔後，按一下以返回「產品」頁面 **[!UICONTROL 產品]** 頂端。
1. 在「Adobe Analytics」圖磚下，按一下 **[!UICONTROL 指派使用者]**.
1. 輸入您要授與 Analytics 完整存取權的電子郵件地址，並將新建的完整管理員存取設定檔指派給對方。 按一下「**[!UICONTROL 儲存]**」。

使用者此時就可以完整存取 Adobe Analytics 了。

## 授予產品管理員在Experience Platform中資料收集的存取權

產品管理員對 Experience Platform 中資料收集的存取權幾乎與授與產品管理員對 Analytics 的存取權相同。

1. 使用 Adobe ID 認證登入 [Adobe Admin Console](https://adminconsole.adobe.com)。
1. 按一下上方的「**[!UICONTROL 產品]**」索引標籤。 貴組織購買的所有產品都位於左側。 按一下 **[!UICONTROL Experience Platform Launch]**，然後按一下「**[!UICONTROL 新描述檔]**」。
1. 將此描述檔命名為「Data Collection full admin access」，然後按一下「**[!UICONTROL 完成]**」。
1. 返回「**[!UICONTROL 產品描述檔]**」頁面，按一下新建的描述檔，然後按一下「**[!UICONTROL 權限]**」索引標籤。
1. 按一下其中一個權限細項。 如果可使用「**[!UICONTROL 自動加入]**」，則啟用它。 如果無法使用自動加入，請按一下「**[!UICONTROL 全部新增]**」。 這兩個選項都會將所有權限項目移至右欄。
1. 按一下「**[!UICONTROL 儲存]**」。 對所有權限類別重複上述步驟。
1. 當所有權限類別都授與描述檔之後，請按一下最上方的「**[!UICONTROL 總覽]**」返回總覽頁面。
1. 在 [!UICONTROL Experience Platform Launch] 動態磚底下，按一下「**[!UICONTROL 指派使用者]**」。
1. 輸入您要授與 Analytics 完整存取權的電子郵件地址，並將新建的完整管理員存取設定檔指派給對方。 按一下「**[!UICONTROL 儲存]**」。
1. 該使用者現在便擁有 Experience Platform 資料收集的完整存取權。

## 授予產品設定檔的產品管理員存取權

如需將使用者指派為產品設定檔管理員的相關資訊，請參閱文章中的「管理產品設定檔管理員」一節 [管理企業使用者的產品設定檔](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) （在企業使用手冊中）。

## 後續步驟

[建立報表套裝](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md):請您的Analytics管理員登入工具並建立資料收集的報表套裝

[建立 Analytics 標記屬性](/help/implement/launch/create-analytics-property.md)：請您的資料收集管理員登入此工具，並建立在您的網站上實作的屬性

在Adobe Analytics中，必須先將使用者指派為Experience Cloud中的第一個管理員，才能為任何使用者指派角色。 然後，第一個管理員就可以將組織中的使用者布建為其他關鍵角色，如本文所述。

第一位管理員是讓組織其他成員開始使用各種 Experience Cloud 解決方案的起點。

簽合同後

1. Adobe的布建團隊準備建立帳戶。

1. 第一位管理員會在合約開始日期之前收到含有登入憑證的電子郵件。

>[!IMPORTANT]
>
>   強烈建議您務必先將第一位管理員的聯絡資訊提供給 Adobe，且確保資訊正確無誤，再簽署合約。