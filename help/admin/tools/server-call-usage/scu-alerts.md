---
description: 新增或管理伺服器所有使用量警報。 當您設定警報時，該警報會套用至結帳公司之所有登入公司中的所有報表套裝。
title: 伺服器呼叫使用量警報
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
TQID: https://experienceleague.adobe.com/aF3SxS36Y1xQN-saS6NTRJoN6H5XwgCx2iRmWPvUPm0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 5e560c5a1c241a297a7bc876978f2996e793e1ea
workflow-type: tm+mt
source-wordcount: 517
ht-degree: 53%

---

# 伺服器呼叫使用量警報

當您設定警報時，該警報會套用至結帳公司之所有登入公司中的所有報表套裝。

伺服器呼叫使用量警示是[警示](/help/components/alerts/alert-manager.md)使用者介面的一部分。

這項類別已預先填入 **1 個預設警報**，顯示在任何可存取「伺服器呼叫使用量」功能的登入公司中。 如果滿足以下其中一項條件，該警報就會觸發通知，傳送給所有登入公司的管理員：

* 您有權存取的任何伺服器呼叫型別的「任何」伺服器呼叫使用量「高於或等於」100%，或者
* 您有權使用的任何伺服器呼叫型別「任何」伺服器呼叫使用量「高於或等於」90%，或者
* 對於您有權使用的任何伺服器呼叫類型，「任何」伺服器呼叫使用量「高於或等於」75%，而且「實際使用期間」低於或等於使用期間的 75%。

![](/help/admin/tools/server-call-usage/assets/alerts.png)

您可以透過兩種方式存取伺服器呼叫使用量警報：

* 按一下「目前使用量」標籤或「報表套裝使用量」標籤右上角的&#x200B;**[!UICONTROL 「管理警報」]**，或
* 導覽至 Adobe Analytics 中的&#x200B;**[!UICONTROL 「元件]** > **[!UICONTROL 警報」]**。

## 建立伺服器呼叫使用量警報 {#create}

若要建立其他警報，

1. 請按一下&#x200B;**[!UICONTROL 「+ 新增」]**，並選取&#x200B;**[!UICONTROL 「伺服器呼叫使用量警報」]**。

   ![](/help/admin/tools/server-call-usage/assets/server_call_alert.png)

1. 定義警報。

   ![](/help/admin/tools/server-call-usage/assets/sc_alert.png)

   * **標題**：指定描述性名稱。 您無法儲存沒有名稱的警報。
   * **時間顆粒度:** 指出系統檢查警報的頻率。 *目前僅支援每週詳細程度。* 這表示會每週檢查警報，並從目前使用期間回溯資料。
   * **收件者**：指定當警報觸發指定臨界值時，組織中應該收到電子郵件的對象。
   * **過期日**：依預設，過期日是從警報建立日期開始的一年後。
   * **傳送警報的時機**：

      * 這些量度觸發器的任一項
新增伺服器呼叫型別作為量度，並藉由選取修飾詞和臨界值來指定警報臨界值：
         * 大於或等於
         * 小於或等於
      * 使用
指定「實際使用期間」的臨界值和條件（高於或等於或低於或等於）。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 管理伺服器呼叫使用量警報 {#manage}

![](/help/admin/tools/server-call-usage/assets/alert_mgmt.png)

若要管理警報：

1. 選取一或多個警報旁的核取方塊。 警示管理動作會顯示在頂端。
1. 完成以下一或多個動作：

   | 動作 | 定義 |
   |--- |--- |
   | + 新增 | 按一下[!UICONTROL 「+ 新增」]以存取[「警報產生器」](/help/admin/tools/server-call-usage/scu-alerts.md)。 |
   | 標記 | 標籤警報以組織警報以方便使用。 |
   | 刪除 | 您可以刪除預設警示以外的所有警示。 |
   | 重新命名 | 您可以重新命名預設警示以外的所有警示。 |
   | 核准 | 核准警報以使其「官方」。 |
   | 啟用/停用 | 您可以啟用或停用所有警示，甚至預設的警示。 |
   | 續訂 | 選取一或多個警報後，即可續訂警報。 如此一來，無論原始到期日為何，到期日將從按一下[!UICONTROL 續訂]之日起延長1年。 |
   | 匯出至 CSV | 檢視[下載使用量報告](/help/admin/tools/server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
