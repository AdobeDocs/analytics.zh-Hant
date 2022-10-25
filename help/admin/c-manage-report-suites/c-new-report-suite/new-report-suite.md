---
description: 您可以選取預先定義的範本，或使用其中一個現有的報表套裝作為模型，來建立新的報表套裝。
title: 新的報表套裝 - 設定
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 4f51233fa7373481c0e001f86398a09fbbb35fb3
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 91%

---

# 新的報表套裝 - 設定

您可以選取預先定義的範本，或使用其中一個現有的報表套裝作為模型，來建立新的報表套裝。

建立報表套裝時[所使用元素的說明](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)。

>[!NOTE]
>
>[虛擬報表套裝文件](/help/components/vrs/c-workflow-vrs/vrs-create.md)會示範如何建立虛擬報表套裝。

| 元素 | 說明 |
| --- | --- |
| 報表套裝 ID | 指定僅能含英數字元的不重複 ID。此 ID 在建立後即無法變更。由 Adobe 設定必要的 ID 首碼，此值無法變更。在建立多個報表套裝時，請確定您所使用的命名慣例可確保唯一報表套裝 ID。 |
| 網站標題 | 在「管理工具」中識別報表套裝。此標題也會用於套裝標題的報表套裝下拉式清單中。 |
| 時區 | 排程事件與時間戳記資料。 |
| 基礎 URL | (可選) 定義報表套裝的基本網域。如果您未明確定義報表套裝的內部 URL 篩選器，此 URL 就會當做內部 URL 篩選器使用。 |
| 預設頁面 | (可選) 從遇到的 URL 中移除預設頁面值的發生次數。若您的人氣最高的頁面報表包含 URL 而非頁面名稱，此設定可防止同一網頁出現多個 URL。例如，URL `https://example.com` 和 `https://example.com/index.html` 通常是指同一頁面。<p> 您可移除多餘的檔案名稱，好讓上述兩個 URL 在報表中均顯示為 `https://example.com` 。若您未設定此值，Analytics會自動從URL中移除下列檔案名稱： `index.htm`, `index.html`, `index.cgi`, `index.asp`,  `default.htm`, `default.html`, `default.cgi`, `default.asp`, `home.htm`, `home.html`, `home.cgi`，和 `home.asp`. 若要停用檔案名稱移除，請指定一個 URL 中永遠不會出現的「預設頁面」值， |
| 上線日期 | 通知 Adobe 您要讓此報表套裝開始生效的日期。如果您的部署計劃變更，請使用「流量管理」下的「永久性預期流量」工具，提供更新的流量估計值。 |
| 預計的每日頁面檢視次數 | 識別您預期此報表套裝在一天內可支援的頁面檢視預估次數。大流量將需要更長的批準過程。若想避免處理延遲，此項估計請盡量準確。 |
| 基本貨幣 | 指定用來儲存所有貨幣資料的預設貨幣。Analytics 報告會使用它收到資料時的轉換率，將其他貨幣的交易換算為基本貨幣。Analytics報表使用currencyCode JavaScript變數來識別指定交易的貨幣。 |
| 停用多位元組字元支援 | 停用報表套裝的多位元組字元支援。如果您停用多位元組字元支援，系統會假設資料位於 `ISO-8859-1` 格式。 網頁必須在 charSet JavaScript 變數中指定其字元集。 <p>多位元組字元支援可使用 UTF-8 儲存報表套裝中的字元。系統收到報告時就會將您網頁資料的字元集轉換為 UTF-8 字元集，因此您可以在行銷報告中使用任何語言。聯絡您的帳戶管理員或客戶服務，以變更現有報表套裝的多位元組字元支援。 |

{style=&quot;table-layout:auto&quot;}
