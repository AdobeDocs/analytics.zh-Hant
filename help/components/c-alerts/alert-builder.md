---
description: 'null'
title: 警報產生器
uuid: 86d00a33-dc99-4dc3-a732-0b895ba487bc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 警報產生器

>[!IMPORTANT]
>
>智慧型警報僅供 Adobe [!DNL Analytics] Prime 與 Adobe [!DNL Analytics] Ultimate 的客戶使用。

存取警報產生器有四種方法：

* 在 Analysis Workspace 中使用下列快速鍵：

   `ctrl (or cmd) + shift + a`
* 前往 **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**。
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* 從報表 [!UICONTROL Reports & Analytics] 內，前往 **[!UICONTROL More]** > **[!UICONTROL Add Alert]**。

警報產生器的介面與在 [!DNL Analytics] 中建立區段或計算量度時所用的介面類似：

![](assets/alert_builder.png)

**警報名稱**

指定警報的名稱。 警報名稱中可以包含報表的名稱或量度臨界值。

**時間粒度**

指定您希望檢查量度的時間：每小時、每日、每週或每月。

>[!NOTE] 對於使用自訂日曆的報表套裝，警報產生器不支援每月粒度。

**收件者**

指定可傳送警報的位置。警報可以傳送給 [!DNL Analytics] 使用者、[!DNL Analytics] 群組、原始電子郵件地址或電話號碼。

>[!IMPORTANT]
>
>電話號碼前面必須加上「+」符號和[國家/地區代碼](https://countrycode.org/)。

**到期日**

設定警報的到期日。

**傳送警報的時機...**

*... 任何這些量度觸發*

* 拖放量度到畫布以新增觸發。

   請注意，如果警報中並非所有元件 (量度/維度/區段) 都與目前所選報表套裝相容，則會出現&#x200B;**「不相容的元件清單」**&#x200B;訊息。

* 確定度量在設定警報前必須超過的臨界值。 您可以將此值設為臨界值以及下列其中一個條件：

   * 存在有異常狀況
   * 異常狀況高於預期
   * 異常狀況低於預期
   * 異常超過
   * 高於或等於
   * 低於或等於
   * 變更依據

* 「異常超過」是超出現有（靜態）臨界值的新條件。 它會提取動態定義觸發器的異常偵測演算法。 您可以設定 90%、95%、99%、99.75% 或 99.9% 的臨界值。
* 每小時粒度設定為99.75%臨界值，每日粒度設定為99%。
* 請注意您也可以使用計算量度。

*... 包含這些篩選*

拖放區段或維度以新增篩選。 例如，新增「僅限行動裝置」區段表示規則只會觸發行動裝置。

將使用AND語句添加其他篩選器。

**新增規則**

您可按一下齒輪圖示，新增 AND 或 OR 規則。

## 警報預覽 {#section_10D75BA7B77E4C5FAF58A719C082E070}

互動式警報預覽會根據過去的經驗，顯示警報的觸發頻率。

例如，如果您將時間詳細程度設為每日，預覽會告知您，在過去30或31天內，某個量度x次會觸發警報。

如果您發現觸發的警報過多，可以在警報管理器中調整 [閾值](/help/components/c-alerts/alert-manager.md)。

![](assets/alert_preview.png)
