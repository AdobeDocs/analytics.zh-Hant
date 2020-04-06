---
description: 您可以從報表中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。排除資料可排除IP位址資料，進而提高報表的準確性。 此外，您可以移除拒絕服務或其他歪曲報告資料之惡意事件的資料。 您可以設定排除，或使用防火牆。
title: 依 IP 位址排除
topic: Admin tools
uuid: 1ed6105f-e7c5-4c4f-b8f4-e5f66d0824bb
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 依 IP 位址排除

您可以從報表中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。排除資料可排除IP位址資料，進而提高報表的準確性。 此外，您可以移除拒絕服務或其他歪曲報告資料之惡意事件的資料。 您可以設定排除，或使用防火牆。

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Exclude by IP]**

>[!NOTE]依 IP 位址排除的點擊會在帳單中計為[「伺服器呼叫」](https://marketing.adobe.com/resources/help/zh_TW/reference/primary_server_calls.html)。

## 依 Cookie 排除 {#section_FB5A20AB5E514DA6BC596CC67F6A3A4C}

可讓您排除此電腦，以免在帳戶中受到追蹤。 如果您選擇排除電腦，則不會計算從電腦產生的任何資料。

此功能可讓您和您的同事瀏覽網站，但不影響流量資料的準確度。如果您沒有靜態IP位址（例如透過服務提供者的撥號網際網路連線），並想要將自己排除在帳戶資料之外，則可能會想要使用此功能。

| 元素 | 說明 |
|--- |--- |
| [!UICONTROL Add CNAME] | 產生可用來排除網域的退出連結。 如需援助，請聯絡您公司的「支援使用者」部門。<br>您可瀏覽您公司的退出頁面並選擇將您的瀏覽器從測量中排除，即可從報表套裝中排除您的流量，不予以報告。<br>如果您的實作使用第三方 Cookie，您的退出頁面位在[此處](https://democorp.112.2o7.net/optout.html?locale=zh_TW&amp;popup=true)。 |

>[!NOTE] 只有符合以下條件時才可以依電腦排除：
>
> * 從同一工作站進入網站。
> * 使用的瀏覽器啟用了 cookie。
> * 您的 cookie 未刪除。如果 cookie 已刪除，您必須再次排除本人的帳戶。


## 依 IP 位址排除 {#section_609FB6461529409D840111A32FEF5C3D}

IP位址是Internet位址。 所有網際網路使用者都會獲得數位IP位址（通常透過網際網路服務供應商），以有效做為電子識別碼。

頁面檢視會計入計數，並透過IP位址識別獨特頁面訪客。 排除IP位址後，您就無法追蹤經常造訪的訪客。 此功能可讓您和您的同事瀏覽您的網站，而不會影響流量資料的準確性。 最多可以排除 50 個不同的 IP 位址。

您可以使用萬用字元指標(*)來排除一系列位址。 舉例來說，`[!DNL 0.0.*.0]` 會排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之間的所有 IP 位址。最多可以排除 50 個不同的 IP 位址。

## 依防火牆排除 {#section_3E7BFB71ADD941D39F923DB9557AD9CD}

您也可以透過防火牆，阻止收集特定 IP 位址的資料。

請參閱 [Experience Cloud中使用的IP位址](https://marketing.adobe.com/resources/help/zh_TW/home/index.html#kb-adobe-ip-addresses) 。

## IP模糊化的影響 {#section_51B7529FFF16449CA016FDC51D87E2CA}

若啟用 IP 模糊化，系統會在將 IP 位址模糊化前即排除 IP，因此客戶在啟用 IP 模糊化至後，不必再進行任何變更。

如果最後八位數字被移除，則會在IP篩選前完成。 因此，最後八位元組會取代為0，而且應更新IP排除規則，以比對結尾為零的IP位址。 符合 * 應符合 0。
