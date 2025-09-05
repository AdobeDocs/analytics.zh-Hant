---
description: Data Warehouse 提供可讓您擷取訪客 ID 清單的功能。這些 ID 並不是 Cookie ID，而是您在其中一個轉換變數中擷取的 ID。雖然您有其他方式可取得這項資訊，但下列範例會是您產生 Data Warehouse 請求要求的捷徑。
title: 使用案例 - 擷取訪客 ID
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 96%

---

# 使用案例 - 擷取訪客 ID

Data Warehouse 提供可讓您擷取訪客 ID 清單的功能。這些 ID 並不是 Cookie ID，而是您在其中一個轉換變數中擷取的 ID。雖然您有其他方式可取得這項資訊，但下列範例會是您產生 Data Warehouse 請求要求的捷徑。

例如，假設您的公司傳送行銷電子郵件給客戶與潛在客戶。這些電子郵件收件者在您的電子郵件系統中各有一個唯一識別碼（例如&#x200B;*`EMAIL Contact ID`*）。 您可以設定電子郵件，讓聯絡人在收到電子郵件並點按其中一個連結時，即可透過促銷活動 ID 與唯一的電子郵件聯絡人 ID 造訪您的網站。例如，您的電子郵件連結可能會解析為：

```js
https://www.example.com/?cid=springmailblast&mid=1363660158
```

在轉換變數 (eVar) 中設定這些項目，可讓您瞭解每則電子郵件的執行情形 (透過促銷活動 ID)，以及每個電子郵件收件者瀏覽網站 (透過電子郵件聯絡人 ID) 的頻率。

假設您要擷取這些 ID。大部分的行銷人員都會想區分出其網站的行為，然後瞭解他們是否能對符合特定條件的訪客進行二次銷售。例如，您可能會想將二次銷售電子郵件傳送給所有透過電子郵件進入您的網站，並檢視 (或完成) 了網站表單的電子郵件收件者。若要這麼做，請找出適當方式，識別出完成特定表單之訪客的電子郵件聯絡人 ID。

其中一個方式是使用「轉換子關聯」報告，依據電子郵件聯絡人 ID eVar 來劃分表單 ID eVar 值。不過，有一項預先建置的功能，可讓您使用「Data Warehouse」完成此作業。這項功能可讓您告知您的唯一使用者 ID (在此案例中為電子郵件聯絡人 ID) 儲存在哪個 eVar 中，並讓您透過 Data Warehouse 輕鬆擷取這些 ID。使用這項功能可讓您自動建立資料倉庫請求，以提取您想要知道的唯一訪客 ID。
