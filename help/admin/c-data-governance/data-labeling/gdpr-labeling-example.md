---
description: 顯示如何為點擊資料、存取請求、刪除請求的資料加上標籤的範例
title: 加上標籤範例
feature: Data Governance
exl-id: 9bea8636-c79c-4998-8952-7c66d31226e3
source-git-commit: f135138de15f3fc788e637128daeb064d0d453af
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 95%

---

# 加上標籤範例

## 點擊資料範例 {#hit}

假設您有以下點擊資料：

* 第一行含有每個變數的標籤。
* 第二行是變數的名稱。如果變數具有 ID 標籤，則會在括號中包含指派的命名空間。
* 第三行之後是點擊資料。

| 標籤 | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **變數名稱** <br> **(命名空間)** | **MyProp1** <br> **(user)** | **訪客 ID** <br> **(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3** <br> **(xyz)** |
| 點擊資料 | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## 範例存取請求 {#access}

如果我提交存取請求，摘要檔案將會含有下表指出的值。請求可能只會傳回一個裝置檔案、一個人員檔案，或是每種檔案各一。唯有使用人員 ID 且 expandIds 設為 true 時，系統才會傳回兩個摘要檔案。

<table>
  <tr>
    <th colspan="2" style="text-align:center">API 值</th>
    <th rowspan="2">傳回的<br>檔案類型</th>
    <th colspan="5" style="text-align:center">摘要存取檔案中的資料</th>
  </tr>
  <tr>
    <th>命名空間/ID</th>
    <th>expandIDs</th>
    <th>MyProp1</th>
    <th>訪客 ID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>false</td>
    <td>裝置</td>
    <td>不存在</td>
    <td>77</td>
    <td>不存在</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td>AAID=77</td>
    <td>true</td>
    <td>裝置</td>
    <td>不存在</td>
    <td>77</td>
    <td>不存在</td>
    <td>M、P</td>
    <td>X、W</td>
  </tr>
  <tr>
    <td>user=Mary</td>
    <td>false</td>
    <td>人員</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary</td>
    <td rowspan="2">true</td>
    <td>人員</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>裝置</td>
    <td>不存在</td>
    <td>77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W</td>
  </tr>
  <tr>
    <td rowspan="2">user=Mary<br>AAID=66</td>
    <td rowspan="2">true</td>
    <td>人員</td>
    <td>Mary</td>
    <td>77、88、99</td>
    <td>A、B、C</td>
    <td>M、N、O</td>
    <td>X、Y、Z</td>
  </tr>
  <tr>
    <td>裝置</td>
    <td>不存在</td>
    <td>66、77、88</td>
    <td>A、B、C</td>
    <td>N、P</td>
    <td>U、W、Z</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>false</td>
    <td>裝置</td>
    <td>不存在</td>
    <td>55、77</td>
    <td>不存在</td>
    <td>M、R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>xyz=X</td>
    <td>true</td>
    <td>裝置</td>
    <td>不存在</td>
    <td>55、77</td>
    <td>不存在</td>
    <td>M、P、R</td>
    <td>W、X</td>
  </tr>
</table>

請注意，使用 cookie ID 時，expandIDs 的設定不會影響輸出。

## 刪除請求範例 {#delete}

由於表格第一列中有使用 API 值的刪除請求，點擊表格的內容將會更新並看起來像這樣：

<table>
  <tr>
    <th colspan="5" style="text-align:center">AAID=77 <br>(expandIDs 值不重要)</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Mary</td>
    <td>42</td>
    <td>A</td>
    <td>Privacy-7398</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>88</td>
    <td>B</td>
    <td>N</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Mary</td>
    <td>99</td>
    <td>C</td>
    <td>O</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>42</td>
    <td>D</td>
    <td>Privacy-1866</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
> 只有包含 AAID = 77 和 DEL-DEVICE 標籤的資料列儲存格會受到影響。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=false</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>77</td>
    <td>Privacy-1866</td>
    <td>Privacy-3681</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>88</td>
    <td>Privacy-2178</td>
    <td>Privacy-1975</td>
    <td>Y</td>
  </tr>
  <tr>
    <td>Privacy-0523</td>
    <td>99</td>
    <td>Privacy-9045</td>
    <td>Privacy-2864</td>
    <td>Z</td>
  </tr>
  <tr>
    <td>John</td>
    <td>77</td>
    <td>D</td>
    <td>P</td>
    <td>W</td>
  </tr>
  <tr>
    <td>John</td>
    <td>88</td>
    <td>E</td>
    <td>N</td>
    <td>U</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

>[!NOTE]
>
> 只有包含 user=Mary 和 DEL-PERSON 標籤的資料列儲存格會受到影響。此外，實際上，包含 A_ID 的變數可能是 prop 或 eVar。 其取代值會是開頭為「Privacy-」、後接隨機數字 (GUID) 的字串，而非將數值取代為不同的隨機數值。

<table>
  <tr>
    <th colspan="5" style="text-align:center">user=Mary<br>expandIDs=true</th>
  </tr>
  <tr>
    <th>MyProp1</th>
    <th>AAID</th>
    <th>MyEvar1</th>
    <th>MyEvar2</th>
    <th>MyEvar3</th>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>09</td>
    <td>Privacy-0859</td>
    <td>Privacy-8183</td>
    <td>Privacy-9152</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>16</td>
    <td>Privacy-6104</td>
    <td>Privacy-2911</td>
    <td>Privacy-6821</td>
  </tr>
  <tr>
    <td>Privacy-5782</td>
    <td>83</td>
    <td>Privacy-2714</td>
    <td>Privacy-0219</td>
    <td>Privacy-4395</td>
  </tr>
  <tr>
    <td>John</td>
    <td>09</td>
    <td>D</td>
    <td>Privacy-8454</td>
    <td>Privacy-8216</td>
  </tr>
  <tr>
    <td>John</td>
    <td>16</td>
    <td>E</td>
    <td>Privacy-2911</td>
    <td>Privacy-2930</td>
  </tr>
  <tr>
    <td>John</td>
    <td>44</td>
    <td>F</td>
    <td>Q</td>
    <td>V</td>
  </tr>
  <tr>
    <td>John</td>
    <td>55</td>
    <td>G</td>
    <td>R</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Alice</td>
    <td>66</td>
    <td>A</td>
    <td>N</td>
    <td>Z</td>
  </tr>
</table>

請注意下列事項：

* 包含 `user=Mary` 和 `DEL-PERSON` 標籤的資料列上的儲存格會受到影響。
* 由於 ID 擴充的緣故，包含 `AAID=77`、`AAID=88` 或 `AAID=99` (也就是包含 `user=Mary` 的資料列上的 AAID 值) 和 `DEL-DEVICE` 標籤的資料列上的儲存格會受到影響。 其中包括在 `user=Mary` 的資料列上有 `DEL-DEVICE` 標籤的儲存格。 這會導致有 `DEL-DEVICE` 標籤 (AAID、MyEvar2 和 MyEvar3) 的資料列 4 和 5 (以及資料列 1-3) 中的儲存格被混淆。
* expandIDs 設定不會擴充到呼叫來包含 `user=Mary` 時 MyEvar3 (`X`、`Y` 和 `Z`) 中存在的值 (MyEvar3 有 ID-DEVICE 標籤)。 ExpandIDs 只會擴充以包含 `user=Mary` 的資料列上的訪客 ID (此範例中為 AAID，也包括 ECID)。 因此，最後兩個資料列 (包含 `X` 和 `Z` 的 MyEvar3 值) 則不受影響。
* `MyEvar2` 第四和第五行的會更新，因為這些資料列包含相同的訪客ID值(`77` 和 `88`)，與第一和第二列的相同。 因此，ID 擴增會將其納入裝置層級的刪除作業。
* 第二列和第五列的 `MyEvar2` 值符合刪除前和刪除後的值。不過在刪除後，這些不再符合最後一列的 `N` 值，因為該列並未隨著刪除要求而更新。
* `MyEvar3` 在沒有 ID 擴增時的行為非常不同，因為沒有 ID 擴增就沒有相匹配的 `ID-DEVICES`。現在，前五個資料列的 `AAID` 均相符。
