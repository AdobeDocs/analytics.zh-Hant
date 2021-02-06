---
source-git-commit: 03b1195225b97f3ea151eb5b4f39fbed746b3654
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '646'
ht-degree: 67%

---
# Adobe Analytics的產品設定檔

產品設定檔是產品管理員可指派給組織內使用者的權限預設集。 如果您建立產品設定檔，並將將 Experience Cloud 使用者指派到該產品設定檔，對方會繼承產品設定檔中包含的權限項目。

如需瞭解產品設定檔的一般資訊 ，請參閱企業使用者指南中的[管理產品和設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-products-and-profiles.html)。

## 產品設定檔管理員

產品設定檔管理員是一個選用群組，可對該產品設定檔新增或移除使用者。請注意，產品設定檔管理員與產品管理員並不相同：

* 產品設定檔管理員無法完整存取 Adobe Analytics。Adobe Analytics 的完整存取權會保留給產品管理員。
* 產品設定檔管理員可以調整其產品設定檔中的權限項目。
* 產品設定檔管理員可以指派或移除產品設定檔給使用者群組。
* 產品設定檔管理員最適合需要授與及管理其團隊Adobe Analytics存取權的團隊主管或經理。 且不需經由系統管理員或產品管理員即可執行這項操作。

## Adobe Analytics 權限項目

產品設定檔要存取 Adobe Analytics 所需的最低權限如下：

* 產品設定檔必須至少擁有一個報表套裝的存取權-
* 產品設定檔必須屬於 Analytics 工具權限項目&#x200B;**「Analysis Workspace 存取」**(或&#x200B;**「Reports &amp; Analytics 存取」**)

### 報表套裝

授予 Analytics 組織中報表套裝的存取權。使用者必須至少屬於一個報表套裝，才能獲得使用 Adobe Analytics 的存取權。

### 量度

授予報表套裝中量度的存取權。量度會在 Analysis Workspace 中各自列為元件；如果量度可在「Reports &amp; Analytics」中使用，則會列為「網站量度」下的功能表項目。

自訂量度會以編號 1 到 1000 標記為「自訂事件」，以便在報表套裝中各自獨立。如果「自訂事件 1」是啟用的權限項目，則該使用者可存取產品設定檔中所有報表套裝的 event1。

### 維度

授予報表套裝中維度的存取權。維度會在 Analysis Workspace 中各自列為元件；如果維度可在「Reports &amp; Analytics」中使用，則會列為「網站維度」下的功能表項目。

自訂維度 (例如 eVar) 會以編號 1 到 250 標記為「自訂轉換」，以便在報表套裝中各自獨立。如果「自訂轉換 1」是啟用的權限項目，則該使用者可存取產品設定檔中所有報表套裝的 eVar1。

### 報表套裝工具

報表套裝工具權限項目所授予的權限是使用者在報表套裝中有權存取的特定功能。如需權限項目完整清單和說明，請參閱[報表套裝工具](report-suite-tools.md)。

### Analytics 工具

Analytics 工具權限項目所授予的權限是不受報表套裝設定影響的功能。如需權限項目和說明的完整清單，請參閱[Analytics工具的產品設定檔權限](analytics-tools.md)。

## 產品設定檔開發人員

開發人員與使用者類似，但是他們可以在 Adobe I/O 上使用 Experience Cloud API。如需詳細資訊，請參閱企業版使用手冊中的[管理開發人員](https://helpx.adobe.com/tw/enterprise/using/manage-developers.html)。如果使用者獲得任何設定檔的「開發人員存取權」，則可存取「開發控制台」(console.adobe.io)並編輯Adobe Analytics整合。 為使用者授權的Analytics API呼叫和回應將視該使用者擁有「開發人員存取權」之所有設定檔的淨權限而定。

例如，若設定檔權限包含所有量度、所有維度和一個報表套裝，則設定檔的「開發人員存取權」成員可能會進行與相關套裝內任何元件相關的API呼叫。 新增異常偵測後，報表可能會包含更完整的回應，並新增異常資料。 根據經驗，如果描述檔授與Adobe Analytics介面中藍本的存取權，則類似定義描述檔的「開發人員存取權」將啟用對應的API呼叫和回應。
