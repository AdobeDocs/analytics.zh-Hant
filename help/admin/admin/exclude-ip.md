---
description: 您可以從報表中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。透過排除 IP 位址資料，可以排除資料以改進報告準確度。此外，您可以移除來自拒絕服務攻擊或其他歪曲報告資料之惡意事件的資料。您可以設定排除規則，或使用防火牆來進行設定。
solution: Analytics
title: 依 IP 位址排除
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 依 IP 位址排除

您可以從報表中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。透過排除 IP 位址資料，可以排除資料以改進報告準確度。此外，您可以移除來自拒絕服務攻擊或其他歪曲報告資料之惡意事件的資料。您可以設定排除規則，或使用防火牆來進行設定。

**[!UICONTROL Analytics]** &gt;管 **[!UICONTROL 理]** &gt;依IP **[!UICONTROL 排除]**

> [!NOTE] IP位址排除的點擊會計為伺服 [器呼叫](https://marketing.adobe.com/resources/help/en_US/reference/primary_server_calls.html)。

## 依 Cookie 排除 {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

可讓您在帳戶中排除此電腦不予以追蹤。如果您選擇排除電腦，將不會統計電腦產生的任何資料。

此功能可讓您和您的同事拜訪您的網站，但不影響流量資料的準確性。如果您沒有靜態 IP 位址 (例如使用服務提供者提供的撥號 Internet 連線)，但希望從您的帳戶資料中排除自己，則可使用此功能。

| 元素 | 說明 |
|--- |--- |
| [!UICONTROL 新增 CNAME] | 產生退出連結，讓您用來排除您的網域。如需援助，請聯絡您公司的「受支援使用者」部門。<br>您可瀏覽您公司的退出頁面並選擇將您的瀏覽器從測量中排除，即可從報表套裝中排除您的流量，不予以報告。<br>如果您的實施使用第三方 Cookie，您的退出頁面位在[此處](https://democorp.112.2o7.net/optout.html?locale=en_US&popup=true)。 |

> [!NOTE] 除非符合下列條件，否則電腦排除才有效：
>
> * 從同一工作站進入網站。
> * 使用的瀏覽器啟用了 cookie。
> * 您的 cookie 未刪除。如果 cookie 已刪除，您必須再次排除本人的帳戶。


## 依 IP 位址排除 {#section_609FB6461529409D840111A32FEF5C3D}

IP 位址就是 Internet 位址。所有 Internet 使用者都擁有數位 IP 位址 (通常由 Internet 服務提供者提供)，作為有效的電子識別碼。

系統會計算頁面檢視，並透過 IP 位址辨識唯一頁面訪客。將 IP 位址排除不予計算，即可避免 Adobe 追蹤經常存取的訪客。此功能可讓您和您的同事拜訪您的網站，但不影響流量資料的準確性。最多可以排除 50 個不同的 IP 位址。

您可使用萬用字元 (*) 排除某個位址範圍。For example, `[!DNL 0.0.*.0]` would exclude all IP addresses between `[!DNL 0.0.0.0]` and `[!DNL 0.0.255.0]`. 您最多可以排除50個不同的IP位址。

## 依防火牆排除 {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

您也可以透過防火牆，阻止收集特定 IP 位址的資料。

請參閱 [Experience Cloud 使用的 IP 位址](https://marketing.adobe.com/resources/help/en_US/home/index.html#kb-adobe-ip-addresses)一文。

## IP 模糊化的影響 {#section_51B7529FFF16449CA016FDC51D87E2CA}

如果啟用IP模糊化，則會在IP位址被模糊化之前排除IP，因此客戶在啟用IP模糊化時不需要變更任何項目。

如果最後的八位數字己移除，則會在 IP 篩選前進行這項作業。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 * 應符合 0。
