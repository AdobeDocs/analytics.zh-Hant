---
title: Adobe Analytics 產品設定檔
description: 瞭解如何將產品設定檔當做權限預設集使用，讓產品管理員可指派給組織內的使用者。
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 97%

---

# Adobe Analytics 產品設定檔

產品設定檔是產品管理員指派組織內各使用者的權限預設集。如果您建立產品設定檔，並將將 Experience Cloud 使用者指派到該產品設定檔，對方會繼承產品設定檔中包含的權限項目。

如需瞭解產品設定檔的一般資訊 ，請參閱企業使用者指南中的[管理產品和設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-products-and-profiles.html)。

## 產品設定檔管理員

產品設定檔管理員是一個選用群組，可對該產品設定檔新增或移除使用者。請注意，產品設定檔管理員與產品管理員並不相同：

* 產品設定檔管理員無法完整存取 Adobe Analytics。Adobe Analytics 的完整存取權會保留給產品管理員。
* 產品設定檔管理員可以調整產品設定檔中的權限項目。
* 產品設定檔管理員可以對使用者群組，指派或移除其得使用的產品設定檔。
* 需要為團隊授予和管理 Adobe Analytics 存取權限的團隊領導者或經理，都非常適合出任產品資料管理員。且不需經由系統管理員或產品管理員即可執行這項操作。

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

Analytics 工具權限項目所授予的權限是不受報表套裝設定影響的功能。請參閱 [Analytics 工具的產品設定檔權限](analytics-tools.md)，有關權限項目和說明的完整清單。

## 產品設定檔開發人員

開發人員與使用者類似，但是他們可以在 Adobe I/O 上使用 Experience Cloud API。如需詳細資訊，請參閱企業版使用手冊中的[管理開發人員](https://helpx.adobe.com/tw/enterprise/using/manage-developers.html)。獲有任何設定檔之「開發人員存取權」的使用者，可進出「開發控制台」(console.adobe.io) 並編輯 Adobe Analytics 的整合。該使用者獲授權的 Analytics API 呼叫和回應，會視該使用者的所有設定檔之「開發人員存取權」的權限淨效而定。

例如，若某設定檔的權限涵蓋所有量度、所有維度和一個報表套裝，則具有該設定檔之「開發人員存取權」的人員，可叫用該套裝內任何元件的 API。加入「異常偵測」功能後，報表中可提供更完整的回應，並加入相關的異常資料。就經驗而言，如果某設定檔授予存取 Adobe Analytics 介面中某個藍本的權限，則與其類似定義的設定檔的「開發人員存取權」可啟用相應的 API 呼叫和回應。
