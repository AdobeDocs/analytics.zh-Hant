---
title: Adobe Analytics 的第一個管理指南
description: 瞭解如何開始使用 Adobe Analytics、一般角色類型有哪些，以及如何登入 UI。
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics 的第一個管理指南

第一位管理員是讓組織其他成員開始使用各種 Experience Cloud 解決方案的起點。簽妥合約後，Adobe 的佈建團隊就會做好供使用者建立帳戶的準備。第一位管理員會在合約開始日期之前收到含有登入憑證的電子郵件。強烈建議您務必先將第一位管理員的聯絡資訊提供給 Adobe，且確保資訊正確無誤，再簽署合約。

## 使用 Experience Cloud 的關鍵角色

如果您的組織已購買 Adobe Analytics，請考量以下幾種關鍵角色的指派:

- **Adobe Analytics 管理員**: 這類使用者可完整存取 Adobe Analytics 中的所有項目，包括報表套裝設定和使用者權限。根據組織結構而定，Analytics 管理的不同層面可能會交由不同的人員或團隊負責。例如，某人負責指定要在實施過程中使用哪些變數，另一人則可負責確認每個人都擁有正確的權限，以便讓使用者能夠正確提取報表。請至少指定一名使用者負責 Analytics 報表套裝設定和使用者權限，該人員可再從 Analytics 中邀請其他人成為管理員。
- **Adobe Experience Platform Launch 管理員**: 這類使用者可完整存取 Experience Platform Launch 的所有功能，包括發佈權限、建立容器和使用者權限。這類使用者不必非程式設計人員不可，但如果至少具備 HTML、CSS 和 JavaScript 的新手知識，則會很有幫助。他們負責與組織的網站擁有者合作，在網站上實施 Experience Platform Launch 程式碼。請至少指定一名使用者負責組織的實施工作，該人員可再從 Experience Platform Launch 中邀請其他人成為管理員。
- **網站擁有者**: 這類人員或團隊負責網站的編碼和開發。他們不需要帳戶，但是必須與 Experience Platform Launch 管理員合作取得 Experience Platform Launch 程式碼，並在網站上實作。
- **一般使用者**: 這類使用者通常只需要檢視報表，並針對業務問題尋求解答。Analytics 管理員可向這些使用者授予在產品中進行操作的權限。

身為第一位管理員，您的角色可與上述一或多個角色重疊。一旦分配好上述基本職責，您就可以授予權限，讓組織中的其他人開始運作。

## 授予 Analytics 的產品管理員存取權

系統層級管理員無法直接存取產品，但是他們可以將自己新增為產品層級管理員，讓自己取得存取權。如果您想向自己或其他人授予 Adobe Analytics 的存取權，請依照下列步驟進行。

1. 使用您的 Adobe ID 憑證登入 [Admin Console](https://adminconsole.adobe.com/)。
1. 按一下頂端的「產品」標籤。您的組織購買的所有產品都位於左側。按一下「Adobe Analytics」，然後按一下「新增設定檔」按鈕。
1. 將此設定檔命名為「Analytics 完整管理員存取權」，然後按一下「完成」。
1. 返回「產品設定檔」頁面，按一下新建立的設定檔，然後按一下「權限」標籤。
1. 按一下其中一個權限細項。如果「自動包含」可用，請啟用此項目。如果「自動包含」不可用，請按一下「全部新增」。這兩個選項都會將所有權限項目移至右欄。
1. 按一下「儲存」。對所有權限類別重複上述步驟。
1. 所有權限類別都取得設定檔後，按一下頂端的「概觀」返回「概觀」頁面。
1. 在 Adobe Analytics 圖磚下，按一下「指派使用者」。
1. 輸入您要授予 Analytics 完整存取權的電子郵件地址，並將新建的完整管理員存取設定檔指派給對方。按一下「儲存」。
1. 使用者此時就可以完整存取 Adobe Analytics 了。

## 授予 Experience Platform Launch 的產品管理員存取權

Experience Platform Launch 的產品管理員存取權與 Analytics 產品管理員存取權的授予方式幾乎相同。

1. 使用您的 Adobe ID 憑證登入 Admin Console。
1. 按一下頂端的「產品」標籤。您的組織購買的所有產品都位於左側。按一下「Experience Platform Launch by Adobe」，然後按一下「新增設定檔」按鈕。
1. 將此設定檔命名為「Experience Platform Launch 完整管理員存取權」，然後按一下「完成」。
1. 返回「產品設定檔」頁面，按一下新建立的設定檔，然後按一下「權限」標籤。
1. 按一下其中一個權限細項。如果「自動包含」可用，請啟用此項目。如果「自動包含」不可用，請按一下「全部新增」。這兩個選項都會將所有權限項目移至右欄。
1. 按一下「儲存」。對所有權限類別重複上述步驟。
1. 所有權限類別都取得設定檔後，按一下頂端的「概觀」返回「概觀」頁面。
1. 在「Experience Platform Launch by Adobe」圖磚下，按一下「指派使用者」。
1. 輸入您要授予 Analytics 完整存取權的電子郵件地址，並將新建的完整管理員存取設定檔指派給對方。按一下「儲存」。
1. 使用者此時就可以完整存取 Experience Platform Launch 了。

## 後續步驟

[建立報表套裝](create-report-suite.md): 請 Analytics 管理員登入工具並建立資料收集的報表套裝

[在 Experience Platform Launch 中建立屬性](/help/implement/implement-with-launch/create-analytics-property.md): 請 Experience Platform Launch 管理員登入工具並建立要在網站上實施的屬性
