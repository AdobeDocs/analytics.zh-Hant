---
title: 記錄檔
description: 取得記錄檔以進行疑難排解。
translation-type: tm+mt
source-git-commit: aea3b4448b61e8b1b217b4f74b0b80c9fbedd070
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# 記錄檔

疑難排解臨機分析問題時，有時需要取得其記錄檔。 Adobe可使用記錄檔找出問題的根本原因並提供解決方法。 檔案 `discover.log` 包含所有作業階段的所有使用者互動、報表載入資訊和Java錯誤訊息。 它會雜湊任何受保護的資訊，例如使用者的密碼。 大型記錄檔會分割為10 MB的增量。 向Adobe提供記錄檔時，請確定已選取所有檔案。

## Windows

獲取 `discover.log` Windows檔案：

1. 按一下開始功能表，然後選 **取「執行**」，或 `[Win]` 按+ `[R]`。
2. 將下列內容貼入文字欄位，然後按一下「 **確定**」:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. 反白標示資料夾中的所有檔案，然後按一下滑鼠右鍵，然後選 **擇「傳送至」>「壓縮（壓縮）資料夾」**。
4. 將。zip檔案提供給Adobe代表。

## Mac

若要取得 `discover.log` Mac OS的檔案，請執行下列動作：

1. 開啟Finder並導覽至 `/Users/your-user/.adobe/Discover/log`
2. 反白標示資料夾中的所有檔案，然後按一下滑鼠右鍵，然後選擇「壓縮 **」**。
3. 將。zip檔案提供給Adobe代表。

如果壓縮檔案的總大小超過10 MB,Adobe代表可提供暫時的FTP位置。
