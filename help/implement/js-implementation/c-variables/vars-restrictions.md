---
description: 在 JavaScript 變數中一律不允許使用的字元和字串。
keywords: Analytics Implementation
subtopic: Variables
title: 非法 JavaScript 字元
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 非法 JavaScript 字元

在 JavaScript 變數中一律不允許使用的字元和字串。

* 定位字元 (0x09)
* 歸位字元 (0x0D)
* 新行字元 (0x0A)
* ASCII 碼超過 127 的 ASCII 字元 (除非已啟用多位元組字元，並適當填入  *`charSet`*)
* HTML 標籤 (例如 <b></b> 或 &amp;#153)

許多變數 (特別是產品、階層和事件) 會有其他限制或語法需求。如需個別變數的限制和語法需求，請參閱  *`s_account`* 變數參數的對應章節。
