---
description: 列出受使用者移轉影響的 API
title: 受使用者移轉影響的 API
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 54%

---

# 受使用者移轉影響的 API{#apis-affected-by-the-migration}

Adobe 正在移轉所有透過 Analytics 登入的企業，使其從 [!DNL my.omniture.com] 登入，改成透過 Adobe Experience Cloud 驗證。 一旦開始移轉作業，原本的 Analytics 專用權限，以及 Analytics Admin API 1.3 和 1.4 等版本所提供的 `GetLoginKey` 方法都將停用，屆時系統將不支援以這些方法建立及管理程式使用者。 Experience Cloud 中的所有此類動作，現在都將透過 [!DNL adobe.io] 啟用。

## 受影響的 API 方法 {#methods}

一旦開始移轉使用者，系統將不再支援 Admin API 1.3 和 1.4 版的以下 API 方法：

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authinate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## 您可以採取的動作 {#actions}

如果貴公司目前使用這些方法，請尋找2018年3月31日起開始的移轉前通知。 我們會在貴公司開始移轉至Experience Cloud驗證至少30天前傳送通知，屆時系統將停止支援這些方法。

如果貴公司未使用這些方法，則除了確保您不會開始使用這些方法外，不需要採取任何動作。

如需其他資訊，請參閱以下資源：

* [一般使用者管理資訊](https://helpx.adobe.com/tw/enterprise/help/users.html)
* [User Management API論壇](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Analytics使用者存取權和管理權移轉至Experience Cloud](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
