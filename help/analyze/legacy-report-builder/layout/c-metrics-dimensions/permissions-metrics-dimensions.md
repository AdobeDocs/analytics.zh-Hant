---
description: Adobe Report Builder 現在提供類似於 Analytics 管理工具中的權限設定。
title: 維度與量度的使用者存取權限
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
TQID: https://experienceleague.adobe.com/p-nsvA1hqNBbwXesj5cumraamq2nEk1zVHgbby-XwEA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 45%

---

# 維度與量度的使用者存取權限

{{legacy-arb}}

Adobe Report Builder的許可權設定與Analytics管理工具中的許可權設定類似。

您身為非管理員使用者，先前可能會建立請求指向您無權存取之維度和量度的活頁簿。 這些許可權現已強制執行。

例如，如果您重新整理含有您無權存取之維度或量度的請求，您將會收到「限制許可權錯誤」訊息。 錯誤訊息指出，由於管理許可權，您的使用者帳戶無法使用請求。

![熒幕擷圖顯示限制許可權錯誤訊息。](assets/arb_restrc_perm.png)

請針對您維護的&#x200B;**每一個** Report Builder 活頁簿，遵照下列指示操作：

1. 開啟活頁簿。
1. 重新整理所有請求。
1. 如果您收到使用者存取許可權錯誤的提示，請按一下&#x200B;**[!UICONTROL 開啟CSV檔案]**&#x200B;以取得許可權受限錯誤清單的存取權。
1. 建立「AllRestrictedPermissionErrors.xlsx」檔案，並將 CSV 檔案中的限制權限錯誤清單複製/貼上至此檔案。
1. 關閉 Report Builder 活頁簿。

處理完所有活頁簿後，「AllRestrictedPermissionErrors.xlsx」中應該就會出現完整的限制權限錯誤清單。 將此清單傳送給您的 Adobe Analytics 使用者存取管理員，要求他給您存取度量與維度的權限。
