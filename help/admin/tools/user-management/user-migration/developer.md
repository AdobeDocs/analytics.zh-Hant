---
description: 列出受使用者移轉影響的 API
title: 受使用者移轉影響的 API
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 42%

---

# 受使用者移轉影響的 API{#apis-affected-by-the-migration}

Adobe正在將所有Analytics登入公司從[!DNL my.omniture.com]移轉到透過Adobe CX Enterprise的驗證。 一旦開始移轉作業，原本的 Analytics 專用權限，以及 Analytics Admin API 1.3 和 1.4 等版本所提供的 `GetLoginKey` 方法都將停用，屆時系統將不支援以這些方法建立及管理程式使用者。 此類動作將透過`adobe.io`在CX Enterprise啟用。

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

如果貴公司目前使用這些方法，請尋找2018年3月31日起開始的移轉前通知。 通知至少會在貴公司開始移轉至CX Enterprise驗證的30天前傳送，屆時系統將停止支援這些方法。

如果貴公司未使用這些方法，則除了確保您不會開始使用這些方法外，不需要採取任何動作。

如需其他資訊，請參閱以下資源：

* [一般使用者管理資訊](https://helpx.adobe.com/tw/enterprise/help/users.html)
* [User Management API論壇](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Analytics使用者存取及管理移轉至CX Enterprise](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
