---
title: 依 IP 位址排除
description: 防止某些 IP 位址產生的資料出現在報表中。
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 94%

---

# 依 IP 位址排除

您可以從報表中排除特定 IP 位址的資料，例如內部網站活動、網站測試和員工使用情形。透過排除 IP 位址資料，可以排除資料以改進報告準確度。此外，您可以移除來自拒絕服務攻擊或其他歪曲報告資料之惡意事件的資料。您可以設定排除規則，或使用防火牆來進行設定。

**[!UICONTROL Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 所有管理員]** > **[!UICONTROL 依 IP 位址排除]**

>[!NOTE]
>
>依 IP 位址排除的點擊在帳單中會計為[伺服器呼叫](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html)。

您可以使用萬用字元指標(&#42;)以排除某個位址範圍。 舉例來說，`[!DNL 0.0.*.0]` 會排除 `[!DNL 0.0.0.0]` 和 `[!DNL 0.0.255.0]` 之間的所有 IP 位址。最多可以排除 50 個不同的 IP 位址。

>[!TIP]
>
>私人 IP 位址不需要排除。 只有外部 IP 位址可以聯繫 Adobe 資料收集伺服器。 私人位址包括 `10.*.*.*`、`192.168.*.*`、`172.[16-31].*.*` 和 `169.254.*.*`。

## IP 模糊化的影響 {#section_51B7529FFF16449CA016FDC51D87E2CA}

若啟用 IP 模糊化，系統會在將 IP 位址模糊化前即排除 IP，因此客戶在啟用 IP 模糊化至後，不必再進行任何變更。

如果最後的八位數字己移除，則會在 IP 篩選前進行這項作業。因此，最後八位數字被 0 取代，而 IP 排除規則應更新為符合最後為零的 IP 位址。符合 &#42; 應符合 0。
