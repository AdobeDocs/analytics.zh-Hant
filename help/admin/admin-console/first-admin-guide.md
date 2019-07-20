---
title: Adobe Analytics第一個管理指南
seo-title: Adobe Analytics第一個管理指南
description: 瞭解如何開始使用Adobe Analytics、一般角色類型以及登入UI。
seo-description: 瞭解如何開始使用Adobe Analytics、一般角色類型以及登入UI。
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Adobe Analytics第一個管理指南

第一個管理員是讓組織其餘人員使用每個Experience Cloud解決方案的起點。簽署合約後，Adobe的布建團隊就會準備好建立帳戶。第一個管理員會在合約開始日期之前收到登入憑證的電子郵件。強烈建議先向Adobe提供第一個管理員的聯絡資訊，然後強烈建議簽署合約。

## 使用Experience Cloud中的主要角色

如果您的組織已購買Adobe Analytics，則有幾個主要角色可供考慮：

- **Adobe Analytics管理員：** 這些使用者可以完整存取Adobe Analytics中的所有內容，包括報表套裝設定和使用者權限。視組織結構而定，不同的人員或團隊可以對Analytics管理的不同Facet負責。例如，一個人負責指定要在實施中使用哪些變數。另一個人負責讓使用者確保每個人擁有正確權限，以正確提取報告。識別至少一位負責Analytics報表套裝設定和使用者權限的使用者，並且他們可以從該處邀請其他Analytics管理員。
- **Adobe Experience Platform Launch管理員：** 這些使用者可完整存取Experience Platform Launch中的所有功能，包括發佈權限、建立容器和使用者權限。這些使用者不一定是程式設計人員，但是至少新手對HTML、CSS和JavaScript的知識很有益處。他們負責與您組織的網站擁有者合作，以取得在您網站上實施的Experience Platform Launch程式碼。識別至少有一位使用者負責您的組織實施，並且他們可以從該處邀請其他Experience Platform Launch管理員。
- **網站擁有者：** 這些個人或團隊負責編寫和開發您的網站。他們不需要帳戶，但想要使用Experience Platform Launch管理員來取得Experience Platform Launch程式碼並在您的網站上實施。
- **使用者：** 這些使用者通常會檢視報告，並尋找商業問題的答案。Analytics管理員會授與這些使用者在產品中工作的權限。

身為第一個管理員，您的角色會在其中一個或多個角色中重疊。只要涵蓋這些基本責任，您就可以授予權限給組織中的其他人。

## 授予Analytics的產品管理員存取權

系統層級管理員無法直接存取產品，但是他們可以將自己新增為產品層級管理員來自行存取。如果您想要讓自己或其他人存取Adobe Analytics，您可以遵循這些步驟。

1. Log in to the [Admin Console](https://adminconsole.adobe.com/) with your Adobe ID credentials.
1. 按一下頂端的「產品」索引標籤。您的組織購買的所有產品都位於左側。按一下Adobe Analytics，然後按一下「新描述檔」按鈕。
1. 將此描述檔的「Analytics完整管理員存取權」命名，然後按一下「完成」。
1. 在「產品描述檔」頁面上，按一下新建立的描述檔，然後按一下「權限」標籤。
1. 按一下其中一個權限行項目。如果「自動包含」已提供，請啓用它。如果自動包含無法使用，請按一下「新增所有」。這兩個選項都會將所有權限項目移至右側欄。
1. 按一下儲存。針對所有權限類別重復上述步驟。
1. 將所有權限類別授與描述檔後，請按一下頂端的「概述」，返回「概述」頁面。
1. 在Adobe Analytics圖標下，按一下「指派使用者」。
1. 輸入您要提供完整Analytics存取權的電子郵件地址，並指派新建立的完整管理員存取設定檔。按一下「儲存」。
1. 使用者現在可以完整存取Adobe Analytics。

## 授予Experience Platform Launch的產品管理員存取權

Experience Platform Launch的產品管理存取權與授與Analytics產品管理員存取權幾乎相同。

1. 使用您的Adobe ID認證登入Admin Console。
1. 按一下頂端的「產品」索引標籤。您的組織購買的所有產品都位於左側。按一下「Experience Platform Launch by Adobe」，然後按一下「New Profile」(新描述檔)按鈕。
1. 將此描述檔命名為「Experience Platform Launch完整admin access」，然後按一下「完成」。
1. 在「產品描述檔」頁面上，按一下新建立的描述檔，然後按一下「權限」標籤。
1. 按一下其中一個權限行項目。如果「自動包含」已提供，請啓用它。如果自動包含無法使用，請按一下「新增所有」。這兩個選項都會將所有權限項目移至右側欄。
1. 按一下儲存。針對所有權限類別重復上述步驟。
1. 將所有權限類別授與描述檔後，請按一下頂端的「概述」，返回「概述」頁面。
1. 在Experience Platform Launch by Adobe圖標下，按一下「指派使用者」。
1. 輸入您要提供完整Analytics存取權的電子郵件地址，並指派新建立的完整管理員存取設定檔。按一下「儲存」。
1. 使用者現在可以完整存取Experience Platform Launch。

## 後續步驟

[建立報表套裝](create-report-suite.md)：讓您的Analytics管理員登入工具登入，並建立資料收集的報表套裝

[在Experience Platform Launch中建立屬性](../../implement/implement-with-launch/create-analytics-property.md)：讓您的Experience Platform啓動管理員登入，並建立要在網站上實施的屬性
