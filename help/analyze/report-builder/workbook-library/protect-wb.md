---
description: 您可以鎖定活頁簿，保護活頁簿中的所有請求，不讓他人新增及編輯。這樣可暫停所有報表請求，啟用活頁簿的離線編輯功能，進行更有效率的編輯。
title: 鎖定/解除鎖定活頁簿
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 鎖定/解除鎖定活頁簿

您可以鎖定活頁簿，保護活頁簿中的所有請求，不讓他人新增及編輯。這樣可暫停所有報表請求，啟用活頁簿的離線編輯功能，進行更有效率的編輯。

身為分析師，您可以鎖定活頁簿，讓組織內的其他使用者無法竄改，以保護您的活頁簿請求。同時，這些使用者仍然可以重新整理活頁簿中的請求。

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

)。

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

)。

若要將已鎖定的活頁簿解鎖，您必須具備下列其中一項權限:

* 您是管理員，或者
* 您是一開始鎖定活頁簿的人。在這種情況下，您就不需要是管理員。

> [!NOTE] 除非您擁有解除鎖定活頁簿的權限，否則無法將請求新增至受保護的活頁簿。

當活頁簿已鎖定而無法編輯請求時，

* 使用者無法建立/新增請求。
* 使用者無法透過「請求精靈」編輯請求。
* 使用者無法透過「編輯多項請求」功能編輯請求。
* 使用者無法剪下、複製或貼上請求。不過，使用者仍可使用原生的「Excel 剪下/複製/貼上」內容功能表，剪下/複製/貼上請求的內容。
* 使用者可以重新整理單一請求，或群組中的部分請求。
* 如果請求使用的是儲存格的輸入值 (日期範圍、區段、篩選條件)，使用者可以變更這些儲存格的值，然後經由重新整理來間接編輯請求。

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* 如果您沒有解除鎖定請求的權限，會出現此提示:

   ![](assets/locked_workbook_error.png)

* 如果您具備必要權限，則不會出現任何提示，您可直接編輯請求。

## 工作流程 {#section_260D05FF632B41DB97DB43E2ADBE2E75}

假設活頁簿 A 有一個處於鎖定狀態的請求，而該請求是由使用者 A 建立。

**範例1:管理員使用者（或使用者A）**

1. 使用者登入 Report Builder，並開啟活頁簿 
1. 活頁簿A目前已鎖定，因此工具列中的「建立請求」按鈕會停用，而其他所有按鈕的功能則會因鎖定而停用。
1. 如果使用者嘗試使用其中一個已停用的按鈕，則會出現訊息說明此活頁簿目前已遭鎖定。
1. 使用者可解除鎖定活頁簿，如此便可啟用所有編輯功能。
1. 解除鎖定之後，活頁簿會保持在已解鎖狀態，直到重新鎖定為止。

**範例2:非管理員使用者（使用者B）**

1. 使用者登入 Report Builder，並開啟活頁簿 
1. 使用者無法新增/編輯請求。
1. 使用者無法解除鎖定活頁簿。

