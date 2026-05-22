---
description: 「網站服務 API」可程式化地存取行銷報告和其他「套裝」服務，讓您透過 Analytics 介面複製並增強可用功能。
title: 網站服務
feature: Company Settings
exl-id: d003d40e-b0b6-44f3-b9ef-ce6af61f5eb5
role: Admin
TQID: https://experienceleague.adobe.com/q0Ji-KYZJS486CKtHaDttXs3coS5hSYQd-cArPK1mCU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 42%

---

# 網站服務

「網站服務 API」可程式化地存取行銷報告和其他「套裝」服務，讓您透過 Analytics 介面複製並增強可用功能。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 公司設定]** > **[!UICONTROL 網站服務]**&#x200B;或&#x200B;**[!UICONTROL API存取]**


## Analytics 2.0 API

若要存取Analytics 2.0 API，您需要Analytics公司的全域公司ID。 您可以在[!UICONTROL API存取]區段頂端的&#x200B;**bold**&#x200B;中找到全域公司識別碼。 以下是範例：「您目前登入之Analytics公司的全域公司ID為&#x200B;**adobe1234**。」

## 管理舊版網站服務 (已過時)

在 [Adobe Admin Console](https://helpx.adobe.com/tw/enterprise/using/admin-console.html) 中，您可以更新權限，以納入那些需要存取網頁服務 API 的使用者。

## WSDL：下載網站服務開發商的網站服務 API WSDL

請前往 [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/)，存取與網站服務 API 相關的文件、範例程式碼和論壇。 如需詳細資訊，請按一下網站服務API概述。

## 篩選選項

使用SOAP時，如果您的XML剖析器在回應網站服務API呼叫時遇到非法或無效的字元問題，請選取下列其中一個或兩個選項，讓Analytics自動篩選回應輸出。 通常只有雙位元組語言（日文、中文、韓文）會發生此問題。

## API 存取資訊

依使用者檢視網站服務存取資訊。 此表格包含「網站服務使用者名稱」和「共用機密」，當進行「網站服務」呼叫時，使用者必須使用這些資訊作為驗證程式的一部分。

## Token使用方式

檢視貴公司在目前行事曆月份所使用之Web服務Token數目的相關資訊。
