---
title: 雜湊碰撞
description: 描述雜湊碰撞為何及其出現方式。
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/yjYX-h-8jJA7k-jzRMOJ0l2BxN5-no2kCfySkGYss8w'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 539
ht-degree: 5%

---

# 雜湊碰撞

Adobe Analytics中的維度會收集字串值。 有時這些字串長達數百個字元，有時則較短。 為改善效能，這些字串值不會直接用於報表時間處理。 相反地，每個值都會計算雜湊，產生大小一致的識別碼。 對於大多數欄位，值在雜湊前會轉換為小寫，以減少唯一值的總數。 所有報表都在這些雜湊值上執行，這會大幅提升其效能。

Adobe Analytics會為各個變數維護個別的雜湊表，每個月都會重新建置每個表格。 在這些資料表的任一資料表中，兩個不同的來源值偶爾會產生相同的雜湊，稱為&#x200B;*雜湊衝突*。

雜湊碰撞可於以下情形出現於報表：

* 如果您檢視一段時間的報表並看到非預期的尖峰，該變數的多個不重複值可能會使用相同的雜湊。
* 如果您使用區段並看到非預期的值，則非預期的維度專案可能會使用與符合您區段的另一個維度專案相同的雜湊。

## 雜湊碰撞的機率

Adobe Analytics對大部分的維度使用32位元雜湊，這表示有2<sup>32</sup>個可能的雜湊組合（約43億）。 根據唯一值數目，發生雜湊碰撞的大致機率如下。 這些賠率是根據單一維度的單一月計算。

| 唯一值 | 賠率 |
| --- | --- |
| 1,000 | 0.01% |
| 10,000 | 1% |
| 50,000 | 26% |
| 100,000 | 71% |

與[生日悖論](https://en.wikipedia.org/wiki/Birthday_problem)類似，雜湊碰撞的可能性會隨著唯一值數目的增加而大幅增加。 該維度至少會有100萬個不重複值，且可能至少有100個雜湊碰撞。

## 緩解雜湊碰撞

雜湊碰撞無法完全消除，但可減輕其對報表的影響。 大部分的雜湊碰撞都會發生於兩個不常見的值，而這些值對報表沒有實質影響。 即使雜湊與通用和不常用的值發生衝突，結果也微不足道。 但是，在少數情況下，當兩個常用的值遇到雜湊碰撞時，可以清楚看到其影響。 Adobe建議採取下列措施來減少其在報表中的影響：

* **變更日期範圍**：雜湊表格每個月都會變更。 將日期範圍變更為跨越另一個月，可能會為每個值提供互不抵觸的不同雜湊。 這通常是清除特定報表中可見異常的最快方式。
* **減少唯一值的數量**：您可以調整實作或使用[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)，協助減少維度所收集的唯一值的數量。 例如，如果您的維度收集URL，您可以移除查詢字串或通訊協定。
* **使用[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)或[資料摘要](/help/export/analytics-data-feed/data-feed-overview.md)**：這些工具不依賴雜湊表。
* **移至[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hant)**： Customer Journey Analytics沒有雜湊層，且[維度沒有基數限制](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html)。 如果雜湊碰撞或[[!UICONTROL 低流量]](/help/technotes/low-traffic.md)經常影響您的報表，請考慮移至此產品。

>[!MORELIKETHIS]
>
>* Adobe Analytics中的[[!UICONTROL 低流量]值](/help/technotes/low-traffic.md)
>* [處理規則總覽](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
