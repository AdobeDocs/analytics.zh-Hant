---
title: Adobe Analytics 的第一個管理指南
description: 瞭解如何開始使用Adobe Analytics、一般角色類型和登入UI。
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Adobe Analytics 的第一個管理指南

第一個管理員是啟用組織其他成員使用每個Experience cloud解決方案的起點。 簽署合約後，Adobe的布建團隊會準備建立帳戶。 第一個管理員在合約的開始日期之前，會收到含登入認證的電子郵件。 強烈建議您確保第一位管理員的聯絡資訊已提供給Adobe，而且在簽署合約前必須正確無誤。

## 使用Experience cloud的關鍵角色

如果您的組織已購買Adobe Analytics，則需考慮幾個關鍵角色：

- **** Adobe Analytics管理員：這些使用者可完整存取Adobe Analytics中的一切，包括報表套裝設定和使用者權限。 根據組織的結構，Analytics管理的不同層面可由不同的人員或團隊負責。 例如，一人負責指定要在實施中使用的變數。 另一人可負責確保每個人擁有正確的權限，讓使用者能夠正確提取報表。 請至少識別一位可負責Analytics報表套裝設定和使用者權限的使用者，而且他們可以從那裡邀請其他Analytics管理員。
- **** Adobe Experience Platform Launch管理員：這些使用者可完整存取Experience Platform Launch的所有功能，包括發佈權限、建立容器和使用者權限。 這些使用者不一定是程式設計人員，但至少擁有HTML、CSS和JavaScript新手的知識是有益的。 他們負責與您組織的網站擁有者合作，讓您的網站上實作Experience Platform Launch代碼。 請至少識別一位可負責貴組織實作的使用者，而且他們可以從那裡邀請其他Experience Platform Launch管理員。
- **** 網站擁有者：這些個人或團隊負責網站的編碼和開發。 他們不需要帳戶，但是想要與Experience Platform Launch管理員合作，以取得Experience Platform Launch程式碼並在您的網站上實作。
- **** 使用者：這些使用者通常會檢視報表並尋找業務問題的解答。 Analytics管理員會授與這些使用者在產品中工作的權限。

身為第一個管理員，您的角色可以在一個或多個這些角色中重疊。 只要涵蓋這些基本責任，您就可以授與權限，讓組織中的其他人也能開始運作。

## 授與Analytics的產品管理員存取權

系統層級管理員無法直接存取產品，但是他們可以新增自己為產品層級管理員，讓自己擁有存取權。 如果您想要讓自己或其他人存取Adobe Analytics，請依照下列步驟進行。

1. 使用您的Adobe ID認 [證登入Admin Console](https://adminconsole.adobe.com/) 。
1. 按一下頂端的「產品」標籤。 您的組織購買的所有產品都位於左側。 按一下「Adobe Analytics」，然後按一下「新增設定檔」按鈕。
1. 將此描述檔命名為「Analytics完整管理員存取」，然後按一下「完成」。
1. 返回「產品描述檔」頁面，按一下新建立的描述檔，然後按一下「權限」標籤。
1. 按一下其中一個權限行項目。 如果「自動包含」可用，請啟用它。 如果「自動包含」不可用，請按一下「全部新增」。 這兩個選項都會將所有權限項目移至右側欄。
1. 按一下「儲存」。 對所有權限類別重複上述步驟。
1. 將所有權限類別授予描述檔後，按一下頂端的「概述」，返回「概述」頁面。
1. 在Adobe Analytics方塊下，按一下「指派使用者」。
1. 輸入您要授予Analytics完整存取權的電子郵件地址，並指派新建立的完整管理員存取設定檔。 按一下「儲存」。
1. 使用者現在可以完整存取Adobe Analytics。

## 授予Experience Platform Launch的產品管理員存取權

Experience Platform Launch的產品管理員存取權與授予Analytics的產品管理員存取權幾乎相同。

1. 使用您的Adobe ID認證登入Admin Console。
1. 按一下頂端的「產品」標籤。 您的組織購買的所有產品都位於左側。 按一下「Experience Platform Launch by Adobe」，然後按一下「New Profile」（新增設定檔）按鈕。
1. 將此描述檔命名為「Experience Platform Launch完整的管理員存取」，然後按一下「完成」。
1. 返回「產品描述檔」頁面，按一下新建立的描述檔，然後按一下「權限」標籤。
1. 按一下其中一個權限行項目。 如果「自動包含」可用，請啟用它。 如果「自動包含」不可用，請按一下「全部新增」。 這兩個選項都會將所有權限項目移至右側欄。
1. 按一下「儲存」。 對所有權限類別重複上述步驟。
1. 將所有權限類別授予描述檔後，按一下頂端的「概述」，返回「概述」頁面。
1. 在「Experience Platform Launch by Adobe」方塊下，按一下「指派使用者」。
1. 輸入您要授予Analytics完整存取權的電子郵件地址，並指派新建立的完整管理員存取設定檔。 按一下「儲存」。
1. 使用者現在可完整存取Experience Platform Launch。

## 後續步驟

[建立報表套裝](create-report-suite.md):讓您的Analytics管理員登入工具並建立資料收集的報表套裝

[在Experience Platform Launch中建立屬性](/help/implement/implement-with-launch/create-analytics-property.md):讓您的Experience Platform Launch管理員登入工具並建立要在網站上實施的屬性
