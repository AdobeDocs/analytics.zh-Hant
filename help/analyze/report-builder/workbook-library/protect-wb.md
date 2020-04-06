---
description: 您可以鎖定活頁簿，以保護活頁簿中的所有請求，避免新增和編輯請求。 如此可暫停所有報表要求，以便更有效率地編輯活頁簿，讓活頁簿離線編輯。
title: 鎖定/解除鎖定活頁簿
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 鎖定/解除鎖定活頁簿

您可以鎖定活頁簿，以保護活頁簿中的所有請求，避免新增和編輯請求。 如此可暫停所有報表要求，以便更有效率地編輯活頁簿，讓活頁簿離線編輯。

身為分析師，鎖定活頁簿可讓您保護活頁簿請求，避免組織內其他使用者竄改。 同時，這些使用者仍可重新整理活頁簿中的請求。

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

)。

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

)。

若要將已鎖定的活頁簿解鎖，您必須具備下列其中一項權限：

* 您是管理員，或
* 您是最初鎖定活頁簿的人。 在這種情況下，您不必是管理員。

>[!NOTE] 您必須具備解除活頁簿鎖定的權限，才能將請求新增至受保護的活頁簿。

當活頁簿因請求編輯而鎖定時，

* 使用者無法建立／新增請求。
* 使用者無法透過「請求精靈」編輯請求。
* 使用者無法透過「編輯多個請求」功能來編輯請求。
* 使用者無法剪下、複製或貼上請求。 不過，使用者仍可使用原生的Excel剪下／複製／貼上內容功能表來剪下／複製／貼上請求的內容。
* 使用者可以個別重新整理請求，或以群組的一部分重新整理請求。
* 如果請求使用儲存格（日期範圍、區段、篩選）的輸入值，使用者可變更儲存格中的這些值，然後透過重新整理請求間接編輯請求。

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* 如果您沒有解除鎖定請求的權限，畫面會顯示以下提示：

   ![](assets/locked_workbook_error.png)

* 如果您擁有必要的權限，則不會顯示任何提示，而且您可以編輯請求。

## 工作流程 {#section_260D05FF632B41DB97DB43E2ADBE2E75}

假設活頁簿 A 有一個處於鎖定狀態的請求，而該請求是由使用者 A 建立。

**範例 1：管理員使用者 (或使用者 A)**

1. 使用者登入 Report Builder，並開啟活頁簿。
1. 活頁簿 A 目前已鎖定，因此工具列中的「建立請求」按鈕為停用狀態，其他按鈕的功能也因遭到鎖定而停用。
1. 如果使用者嘗試使用其中一個已停用的按鈕，會顯示訊息，指出活頁簿目前已鎖定。
1. 使用者可解除鎖定活頁簿，以啟用完整編輯功能。
1. 解除鎖定後，活頁簿會保持解除鎖定狀態，直到明確重新鎖定為止。

**範例 2：非管理員使用者 (使用者 B)**

1. 使用者登入 Report Builder，並開啟活頁簿。
1. 使用者無法新增／編輯請求。
1. 使用者無法解除鎖定活頁簿。

