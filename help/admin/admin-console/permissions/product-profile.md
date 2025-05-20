---
title: Adobe Analytics 產品設定檔
description: 了解如何使用產品設定檔來進行權限預設，讓產品管理員可以指定權限給組織內的使用者。
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: 8f1a17d2b07d5b37ef6d3d3f426234b29be61319
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 65%

---

# Adobe Analytics 產品設定檔

產品設定檔是產品管理員指派組織內各使用者的權限預設集。如果您建立產品設定檔，並將將 Experience Cloud 使用者指派到該產品設定檔，對方會繼承產品設定檔中包含的權限項目。

如需有關產品設定檔的一般資訊，包括建立產品設定檔和指派使用者，請參閱企業使用者指南中的[管理企業使用者的產品設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)。

## 產品設定檔管理員

產品設定檔管理員是一個選用群組，可對該產品設定檔新增或移除使用者。請注意，產品設定檔管理員與產品管理員並不相同：

* 產品設定檔管理員無法完整存取 Adobe Analytics。Adobe Analytics 的完整存取權會保留給產品管理員。
* 產品設定檔管理員無法調整產品設定檔中的許可權專案。
* 產品設定檔管理員可以對使用者群組，指派或移除其得使用的產品設定檔。
* 需要為團隊授予和管理 Adobe Analytics 存取權限的團隊領導者或經理，都非常適合出任產品資料管理員。且不需經由系統管理員或產品管理員即可執行這項操作。

有關如何指派產品設定檔管理員的一般資訊，請參閱企業使用手册內[管理企業使用者的產品設定檔](https://helpx.adobe.com/tw/enterprise/using/manage-product-profiles.html)文章中的「管理產品設定檔管理員」部份。

## Adobe Analytics 權限項目

單一產品設定檔要存取Adobe Analytics所需的最低許可權如下：

* 產品設定檔必須至少擁有一個報告套裝的存取權-
* 產品設定檔必須屬於Analytics工具許可權專案&#x200B;**Workspace專案存取權**。

### 報告套裝

授予 Analytics 組織中報告套裝的存取權。使用者必須至少屬於一個報告套裝，才能獲得使用 Adobe Analytics 的存取權。

### 量度

授予報告套裝中量度的存取權。量度會在Analysis Workspace中各自列為元件。

自訂量度會以編號 1 到 1000 標籤為「自訂事件」，以便在報告套裝中各自獨立。如果「自訂事件 1」是啟用的權限項目，則該使用者可存取產品設定檔中所有報告套裝的 event1。

### 維度

授予報告套裝中維度的存取權。維度會在Analysis Workspace中各自列為元件。

自訂維度 (例如 eVar) 會以編號 1 到 250 標籤為「自訂轉換」，以便在報告套裝中各自獨立。如果「自訂轉換 1」是啟用的權限項目，則該使用者可存取產品設定檔中所有報告套裝的 eVar1。

### 報告套裝工具

報告套裝工具權限項目所授予的權限是使用者在報告套裝中有權存取的特定功能。如需權限項目完整清單和說明，請參閱[報告套裝工具](report-suite-tools.md)。

### Analytics 工具

Analytics 工具權限項目所授予的權限是不受報告套裝設定影響的功能。請參閱 [Analytics 工具的產品設定檔權限](analytics-tools.md)，有關權限項目和說明的完整清單。

## 產品設定檔開發人員

開發人員與使用者類似，但是他們可以在Adobe Developer上使用Experience Cloud API。 如需詳細資訊 ，請參閱企業使用手冊中的[管理開發商](https://helpx.adobe.com/tw/enterprise/using/manage-developers.html)。 如果使用者被授予任何設定檔的開發人員存取權，他們可以存取開發控制檯(console.adobe.io)並編輯Adobe Analytics整合。 使用者獲授權的Analytics API呼叫和回應，會視使用者具有開發人員存取權之所有設定檔的淨許可權而定。

例如，若某設定檔許可權涵蓋所有量度、所有維度和一個報表套裝，開發人員即可以叫用該報表套裝內任何元件的API。 如果新增「異常偵測」許可權專案，API回應可包含異常資料。 根據經驗，如果設定檔授予對Adobe Analytics介面中案例的存取權，則開發人員對類似定義設定檔的存取權將啟用對應的API呼叫和回應。
