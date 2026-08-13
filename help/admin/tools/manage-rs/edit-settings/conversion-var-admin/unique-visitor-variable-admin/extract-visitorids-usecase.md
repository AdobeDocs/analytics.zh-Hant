---
description: Data Warehouse提供可讓您擷取訪客ID清單的功能。 這些ID不是Cookie ID，而是您擷取至其中一個轉換變數的ID。 雖然有其他方法可取得此資訊，但下列範例是產生Data Warehouse請求的捷徑。
title: 使用案例 - 擷取訪客 ID
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
TQID: 'https://experienceleague.adobe.com/CUpKcu-jVNn77bkWM2mJvlLxYMyvfpRt4o-maC7tUBA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f47edbe0-f963-46ff-a667-71011396f5f3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 399
ht-degree: 4%

---

# 使用案例 - 擷取訪客 ID

Data Warehouse提供可讓您擷取訪客ID清單的功能。 這些ID不是Cookie ID，而是您擷取至其中一個轉換變數的ID。 雖然有其他方法可取得此資訊，但下列範例是產生Data Warehouse請求的捷徑。

例如，假設您的企業傳送行銷電子郵件給客戶和潛在客戶。 這些電子郵件收件者在您的電子郵件系統中各有一個唯一識別碼（例如&#x200B;*`EMAIL Contact ID`*）。 您可以設定電子郵件，讓連絡人收到電子郵件並按一下其中一個連結時，訪客可以使用行銷活動ID和唯一的電子郵件連絡人ID來到您的網站。 例如，您的電子郵件連結可能會解析為：

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

在轉換變數(eVar)中設定這些變數，可讓您檢視每個電子郵件的執行方式（透過促銷活動ID），以及每個電子郵件收件者造訪網站的頻率（透過電子郵件聯絡人ID）。

假設您正在擷取這些ID。 大部分行銷人員想要劃分其網站行為，然後檢視他們是否能對符合特定條件的對象進行再行銷。 例如，您可能會想要傳送再行銷電子郵件給所有電子郵件收件者，這些電子郵件收件者都是從電子郵件來到您的網站，並檢視（或完成）網站表單。 若要這麼做，請尋找方法識別完成特定表格者的電子郵件連絡人ID。

其中一個方法是使用轉換子關聯報表，依電子郵件聯絡人ID eVar劃分「表單ID 」eVar值。 不過，預先建立的功能可使用Data Warehouse執行此操作。 此功能可讓您知道哪個eVar儲存您的不重複使用者ID （在此案例中為電子郵件聯絡人ID），並可讓您使用Data Warehouse輕鬆擷取這些ID。 透過使用此功能，您可以自動建立Data Warehouse請求，提取您感興趣的不重複訪客ID。
