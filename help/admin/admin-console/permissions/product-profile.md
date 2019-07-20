---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Adobe Analytics中的產品描述檔

產品設定檔是一個權限預設集，可供產品管理員指派給組織內的使用者。如果您建立產品描述檔並指派Experience Cloud使用者至該產品描述檔，則會繼承產品描述檔中包含的權限項目。

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## 產品設定檔管理員

產品設定檔管理員是可選群組，可新增或移除使用者至該產品描述檔。請注意，產品設定檔管理員與產品管理員不同：

* 產品設定檔管理員僅負責產品設定檔的使用者清單。
* 產品設定檔管理員無法完整存取Adobe Analytics。Adobe Analytics的完整存取權僅適用於產品管理員。
* 產品設定檔管理員無法調整其產品設定檔中的權限項目；產品管理員必須進行權限項目調整。
* 產品設定檔管理員最適合需要為團隊授與Adobe Analytics存取權的團隊潛在客戶或經理人。個人不需要健全的系統管理員或產品管理員來授與Adobe Analytics的存取權。

## Adobe Analytics權限項目

存取Adobe Analytics的產品設定檔中所需的權限上限如下：

* 產品描述檔必須至少存取一個報表套裝
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### 報表套裝

授予屬於您Analytics組織之報告套裝的存取權。使用者必須屬於至少一個報表套裝，才能獲得使用Adobe Analytics的存取權。

### 量度

授予報表套裝中度量的存取權。度量會在分析工作區中列為其各自的元件，也會在「報告與分析」中提供，作為「網站度量」下的功能表項目。

自訂度量會標示為「自訂事件1-1000」，使它們獨立於報表套裝。如果「自訂事件1」是已啓用的權限項目，則該使用者可在產品設定檔中的所有報表套裝中存取event1。

### 維度

授予報表套裝維度的存取權。維度會在分析工作區中列為其各自的元件，或如果維度可用於「報告與分析」，則可作為功能表項目。

自訂變數(例如eVar)會標示為「自訂轉換1-250」，使它們獨立於報表套裝。如果「自訂轉換1」是已啓用的權限項目，則該使用者可在產品設定檔中的所有報表套裝中存取eVar1。

### 報表套裝工具

報表套裝工具權限項目授予存取使用者有權存取之報告套裝的功能。See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Analytics 工具

Analytics工具權限項目授予存取獨立於報表套裝設定的功能。See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## 產品設定檔開發人員

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
