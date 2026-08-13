---
title: 將虛擬報告套裝限制在特定日期
description: 瞭解如何限制虛擬報表套裝日期範圍，以僅限著重銜接的資料。
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 41%

---

# 將虛擬報告套裝限制在特定日期

{{available-existing-customers}}

當我們開啟銜接功能時，系統會在特定日期開始銜接。 假設該日期是 6 月 1 日。 CDA虛擬報告套裝將包含6月1日之前未銜接的資料。 您可能想要在6月1日之前隱藏虛擬報表套裝中的任何資料，以便分析著重在銜接開始後的日期範圍。

您可以執行下列動作，將虛擬報表套裝資料限製為特定日期：

## 步驟1：建立具有「每日滾動」日期範圍的虛擬報表套裝

當您設定虛擬報表套裝時，在「元件」下方，新增開始日期為固定的日期範圍，並具有「每日滾動」日期範圍。 固定開始日期應該是銜接開始的當日。

![](assets/rolling-daily.png)

## 步驟 2：建立「排除-排除」區段

接著，建立點擊區段，將日期範圍放在另一個排除容器內的排除容器中。 這就是「排除 — 排除」。

「排除 — 排除」的原因是日期範圍旨在覆寫報告的日期範圍。 因此，如果您只納入 6 月 1 日轉送，這會使報告日期範圍 6 月 1 日一律轉送。 這將導致不想要的結果。 當您「排除 — 排除」時，這會覆寫此行為，並只限制您可從中擷取的資料至適當的日期範圍。

![](assets/exclude-exclude.png)

## 步驟3：將此區段套用至您的跨裝置分析虛擬報表套裝

![](assets/apply-segment.png)

## 步驟4：檢視報告結果

請注意，現在報告是從所要的日期開始，也就是第一次實施銜接的當天：

![](assets/report-limited-dates.png)
