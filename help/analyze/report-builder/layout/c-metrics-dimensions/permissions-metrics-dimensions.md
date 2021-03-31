---
description: Adobe Report Builder 現在提供類似於 Analytics 管理工具中的權限設定。
title: 維度與度量的使用者存取權限
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: 業務從業人員、管理員
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 98%

---


# 維度與度量的使用者存取權限

Adobe Report Builder 現在提供類似於 Analytics 管理工具中的權限設定。

身為非管理員的使用者，您先前建立的活頁簿中可能含有指向您無權存取之維度與量度的請求。現在，這些權限會強制執行。

例如，如果您重新整理含有您無權存取之維度或度量的請求，您將會收到「限制權限錯誤」訊息：

![](assets/arb_restrc_perm.png)

請針對您維護的&#x200B;**每一個** Report Builder 活頁簿，遵照下列指示操作：

1. 開啟活頁簿。
1. 重新整理所有請求。
1. 如果出現「使用者存取權限」錯誤提示，請按一下「**[!UICONTROL 開啟 CSV 檔案]**」，以存取限制權限錯誤清單。
1. 建立「AllRestrictedPermissionErrors.xlsx」檔案，並將 CSV 檔案中的限制權限錯誤清單複製/貼上至此檔案。
1. 關閉 Report Builder 活頁簿。

處理完所有活頁簿後，「AllRestrictedPermissionErrors.xlsx」中應該就會出現完整的限制權限錯誤清單。將此清單傳送給您的 Adobe Analytics 使用者存取管理員，要求他給您存取度量與維度的權限。
