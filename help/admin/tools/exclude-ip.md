---
title: 依 IP 位址排除
description: 防止某些 IP 位址產生的資料出現在報表中。
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 28%

---

# 依 IP 位址排除

您可以從報告中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。排除資料可排除IP位址資料，進而改善報表正確性。 此外，您也可以從拒絕服務或其他可能扭曲報表資料的惡意事件移除資料。

若要依IP位址排除資料，您可以依照下列說明設定排除專案，或是[設定防火牆](/help/technotes/ip-addresses.md)。

## 依IP位址設定排除專案

>[!NOTE]
>
>依IP位址設定排除專案時，請考量下列事項：
>
>* 依 IP 位址排除的點擊在帳單中會計為[伺服器呼叫](/help/technotes/terms.md)。
>* 私人 IP 位址不需要排除。 只有外部 IP 位址可以聯繫 Adobe 資料收集伺服器。 私人位址包括 `10.*.*.*`、`192.168.*.*`、`172.[16-31].*.*` 和 `169.254.*.*`。
>* 您可以使用萬用字元指標(&#42;)來排除某個位址範圍。 舉例來說，`[!DNL 0.0.*.0]` 會排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之間的所有 IP 位址。最多可以排除 50 個不同的 IP 位址。
>* 在設定排除後5分鐘內任何進入系統的新點選，都會排除排除的IP位址中的資料。
>* 變更IP位址前所擷取的點選資料不受影響。 IP排除僅適用於未來的資料。
>* 排除的點選仍會顯示在[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md) （標示為`exclude_hit = 4`）中。

若要依IP位址設定排除專案：

1. 在Adobe Analytics中，選取&#x200B;**[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]**。

1. 在管理頁面上，選取&#x200B;**[!UICONTROL 依IP排除]**。

## 搭配IP排除使用IP模糊化的影響

使用[IP模糊化](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)搭配IP排除的影響取決於每個報表套裝的IP模糊化設定：

* **IP模糊化（最後一個八位元）**： IP在IP排除執行前已部分模糊化。 請確定IP排除規則一律預期`0`為最後一個八位元（萬用字元有效，因為它們包含`0`）。
* **IP模糊化（移除IP）**：執行IP排除之後，IP會完全模糊化。 不需要IP排除規則調整。
