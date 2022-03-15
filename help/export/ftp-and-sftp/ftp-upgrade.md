---
description: 升級至 Adobe FTP 伺服器可引進會影響自動化指令碼 (通常用於定期下載或上傳資料) 的新設定，這通常需依賴某些伺服器設定。
keywords: ftp;sftp
title: 升級 Adobe FTP 伺服器
feature: FTP Export
exl-id: 442b2d5d-735c-4ece-a456-3a0ac5909c8c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# 升級 Adobe FTP 伺服器

升級至 Adobe FTP 伺服器可引進會影響自動化指令碼 (通常用於定期下載或上傳資料) 的新設定，這通常需依賴某些伺服器設定。

例如，引進一個新的成功狀態，會影響到使用成功狀態來觸發某些動作的指令碼。Adobe 會主動通知使用者此類設定變更。如果 Adobe 通知您即將進行 FTP 伺服器升級，請查看您的自動化指令碼，確認是否仍可正確運作。
