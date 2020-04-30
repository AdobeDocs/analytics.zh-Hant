---
description: 新增或管理伺服器所有使用量警報。當您設定警報時，該警報會套用至結帳公司之所有登入公司中的所有報表套裝。
title: 伺服器呼叫使用量警報
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 伺服器呼叫使用量警報

當您設定警報時，該警報會套用至結帳公司之所有登入公司中的所有報表套裝。

## 概觀

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the existing [Alert Management](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html) user interface.

這項類別已預先填入 **1 個預設警報**，顯示在任何可存取「伺服器呼叫使用量」功能的登入公司中。如果滿足以下其中一項條件，該警報就會觸發通知，傳送給所有登入公司的管理員：

* 對於您有權使用的任何伺服器呼叫類型，「任何」伺服器呼叫使用量「高於或等於」100%，或者
* 對於您有權使用的任何伺服器呼叫類型，「任何」伺服器呼叫使用量「高於或等於」90%，或者
* 對於您有權使用的任何伺服器呼叫類型，「任何」伺服器呼叫使用量「高於或等於」75%，而且「實際使用期間」低於或等於使用期間的 75%。

![](assets/alerts.png)

您可以透過兩種方式存取伺服器呼叫使用量警報：

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or
* 導覽至 **[!UICONTROL Components]** Adobe Analytics **[!UICONTROL Alerts]** 中的>。

## 建立伺服器呼叫使用量警報 {#section_2A2882C6D48D47C1944D52FB7C766BEC}

若要建立其他警報，

1. 按一 **[!UICONTROL + Add]** 下並選取 **[!UICONTROL Server Call Usage Alert]**。

   ![](assets/server_call_alert.png)

1. 定義警報。

   ![](assets/sc_alert.png)

   * **標題**：指定描述性名稱。您無法儲存沒有名稱的警報。
   * **時間粒度**：指出系統檢查警報的頻率。*目前僅支援每週粒度。*&#x200B;這表示將每週檢查警報，並回顧目前使用期間的資料。
   * **收件者**：指定當警報觸發指定臨界值時，組織中應該收到電子郵件的對象。
   * **到期日**：依預設，到期日是從警報建立日期開始的一年後。
   * **傳送警報的時機**：

      * 以上任何量度觸發時
將伺服器呼叫類型新增為量度，並藉由選取修飾詞和臨界值來指定警報臨界值：
         * 高於或等於
         * 低於或等於
      * 採用
指定「實際使用期間」的臨界值和條件 (高於或等於或低於或等於)。

1. 按一下 **[!UICONTROL Save]**.

## 管理伺服器呼叫使用量警報 {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

若要管理警報：

1. 選取一或多個警報旁的核取方塊。警報管理動作會顯示在頂端。
1. 完成以下一或多個動作：

   | 動作 | 定義 |
   |--- |--- |
   | + 新增 | Access the [Alert Builder](/help/admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | 標記 | 標記警報可讓您組織警報以方便使用。 |
   | 刪除 | 您可以刪除預設警報以外的所有警報。 |
   | 重新命名 | 您可以重新命名預設警報以外的所有警報。 |
   | 核准 | 核准警報即可使其成為「正式」警報。 |
   | 啟用/停用 | 您可以啟用或停用所有警報，甚至是預設警報。 |
   | 續訂 | 選取一或多個警報後，可續訂這些警報。This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | 匯出至 CSV | 請參閱[下載使用情況報表](/help/admin/c-server-call-usage/report-suite-usage.md) |

