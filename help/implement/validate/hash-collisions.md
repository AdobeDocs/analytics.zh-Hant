---
title: 雜湊碰撞
description: 描述雜湊碰撞為何及其出現方式。
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: e6dd38fe34d7e0ab69bdf1c68716427905caa356
workflow-type: tm+mt
source-wordcount: '539'
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

雜湊碰撞無法完全消除，但可減輕其對報表的影響。 大部分的雜湊碰撞都會發生於兩個不常見的值，而這些值對報表沒有實質影響。 即使雜湊與通用和不常用的值發生衝突，結果也微不足道。 However, in rare cases where two popular values experience a hash collision, it is possible to see its effect clearly. Adobe recommends the following to reduce its effect in reports:

* **Change the date range**: Hash tables change each month. Changing the date range to span another month can give each value different hashes that don&#39;t collide. It is usually the fastest way to clear a visible anomaly from a specific report.
* **Reduce the number of unique values**: You can adjust your implementation or use [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) to help reduce the number of unique values that a dimension collects. For example, if your dimension collects a URL, you can strip query strings or protocol.
* **Use [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) or [Data Feeds](/help/export/analytics-data-feed/data-feed-overview.md)**: These tools do not rely on hash tables.
* **Move to [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=zh-Hant)**: Customer Journey Analytics has no hashing layer and [no cardinality limits on dimensions](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html). Consider moving to this product if hash collisions or [[!UICONTROL Low-Traffic]](/help/technotes/low-traffic.md) frequently affect your reports.

>[!MORELIKETHIS]
>
>* [[!UICONTROL Low-Traffic] value in Adobe Analytics](/help/technotes/low-traffic.md)
>* [Processing rules overview](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
