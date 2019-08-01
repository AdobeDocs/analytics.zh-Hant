---
description: 說明在精靈完成後，在Lyris中設定要設定甚麼項目的步驟。
seo-description: 說明在精靈完成後，在Lyris中設定要設定甚麼項目的步驟。
seo-title: Lynris EmailLabs中的設定
solution: Analytics
title: Lynris EmailLabs中的設定
uuid: 1276176d-e5 e9-451a-9a7 b-9f29 a340 a25 b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configuration within the Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

說明在精靈完成後，在Lyris中設定要設定甚麼項目的步驟。

1. 完成整合精靈後，您必須與Lyris Professional團隊合作完成您的Lyris HQ帳戶整合，並協助測試。
1. 新增URL查詢字串參數：驗證URL附加字串是否正確輸入至使用者介面的組織設定區域中。這應該包含促銷活動層級ID(hq_ m)和收件者層級ID(hq_ v)。

   字串ID的範例為：

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >If you are applying Lyris’s native analytics tool, *Click Tracks* tags all of the required variables that are added.

