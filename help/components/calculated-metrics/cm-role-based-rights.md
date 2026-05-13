---
description: 管理員級使用者和非管理員之間的計算量度權限不一樣。
title: 角色型權限
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 44%

---

# 角色型權限

管理員級使用者和非管理員之間的計算量度權限不一樣。

|  | 建立 | 共用 | 檢視/管理 | 核准 | 套用 |
|--- |--- |--- |--- |--- |--- |
| 管理員層級使用者 | 管理員可以在 Admin Console 中建立計算量度及產品設定檔，以限制使用者建立計算量度的權限。 | 可以與整個公司、使用者群組及個別使用者分享。 | Report Builder：可以檢視/編輯/刪除自己所擁有的計算量度以及與之共用的計算量度。 | 可核准標準計算量度。 | 可以在整個組織套用任何計算量度。 |
| 非管理員層級使用者 | 依預設，使用者可以建立計算量度。 但是，這些許可權可能會受到管理員的限制。 | 僅可與個別使用者共用 | 僅可檢視/編輯/刪除/等等自己的計算量度。 非管理員使用者必須擁有所有元件事件的存取權，才能檢視共用量度（Admin Console中的許可權仍強制執行）。  如果與非管理員使用者共用儀表板或計劃報表，但未與他們共用量度，則報表會在套用量度的情形下執行 (假設該使用者具有檢視事件的權限)。 但是，他們將無法檢視定義或編輯量度。 | 只能使用已核准的計算量度，無法標籤為已核准。 | 可以套用他們自己的計算量度以及與他們共用的區段。 |
