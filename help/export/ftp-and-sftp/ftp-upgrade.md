---
description: 升級至 Adobe FTP 伺服器可引進會影響自動化指令碼 (通常用於定期下載或上傳資料) 的新設定，這通常需依賴某些伺服器設定。
keywords: ftp;sftp
title: 升級Adobe FTP和SFTP伺服器
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
TQID: https://experienceleague.adobe.com/z19S-G-h4IHJkt4PNp-ajBapP3EYlo0TUtPSYqbhWJ8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
ht-degree: 25%

---

# 升級Adobe FTP和SFTP伺服器

升級至Adobe FTP和SFTP伺服器可引進會影響自動化指令碼（通常用於定期下載或上傳資料）的新設定，這通常需依賴某些伺服器設定。

例如，系統引入新的成功狀態，這會影響使用成功狀態來觸發特定動作的指令碼。 Adobe會主動通知使用者此類設定變更。 如果Adobe通知您即將FTP伺服器升級，請檢查您的自動化指令碼，確保它們仍正常運作。
