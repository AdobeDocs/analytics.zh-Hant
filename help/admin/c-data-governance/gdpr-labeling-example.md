---
description: 'null'
title: 標籤範例
uuid: a9a5b937-dbde-4f0f-a171-005ef4c79df9
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# 標籤範例

## 範例點擊資料

假設您有以下點擊資料：

* 第一行含有每個變數的標籤。
* 第二行是變數的名稱。如果變數具有 ID 標籤，則會在括號中包含指派的命名空間。
* 第三行之後是點擊資料。

| 標籤 | I2<br>ID-PERSON<br>DEL-PERSON<br>ACC-PERSON | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL | I2<br>DEL-PERSON<br>ACC-PERSON | I2<br>DEL-DEVICE<br>DEL-PERSON<br>ACC-ALL | I2<br>ID-DEVICE<br>DEL-DEVICE<br>ACC-ALL |
|---|---|---|---|---|---|
| **變數名稱&#x200B;**<br>**(命名空間)** | **MyProp1 **<br>**(user)** | **Visitor ID **<br>**(AAID)** | **MyEvar1** | **MyEvar2** | **MyEvar3 **<br>**(xyz)** |
| 點擊資料 | Mary | 77 | A | M | X |
|  | Mary | 88 | B | N | Y |
|  | Mary | 99 | C | O | Z |
|  | John | 77 | D | P | W |
|  | John | 88 | E | N | U |
|  | John | 44 | F | Q | V |
|  | John | 55 | G | R | X |
|  | Alice | 66 | A | N | Z |

## 範例存取請求

如果我提交存取請求，摘要檔案將會含有下表指出的值。請求可能只會傳回一個裝置檔案、一個人員檔案，或是每種檔案各一。唯有使用人員 ID 且 expandIds 設為 true 時，系統才會傳回兩個摘要檔案。

| API 值 | API 值 | 傳回的檔案類型 | 摘要存取檔案<br>中的資料 | 摘要存取檔案<br>中的資料 | 摘要存取檔案<br>中的資料 | 摘要存取檔案<br>中的資料 | 摘要存取檔案<br>中的資料 |
|--- |--- |--- |---|---|---|---|---|
| **命名空間/ID** | **expandIDs** |  | **MyProp1** | **訪客 ID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| AAID=77 | false | 裝置 | 變數不存在 | 77 | 變數不存在 | M、P | X、W |
| AAID=77 | true | 裝置 | 變數不存在 | 77 | 變數不存在 | M、P | X、W |
| user=Mary | false | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=Mary | true | 裝置 | 不存在 | 77、88 | 不存在 | N、P | U、W |
| user=MaryAAID=66 | true | 人員 | Mary | 77、88、99 | A、B、C | M、N、O | X、Y、Z |
| user=MaryAAID=66 | true | 裝置 | 不存在 | 66、77、88 | 不存在 | N、P | U、W、Z |
| xyz=X | false | 裝置 | 不存在 | 55、77 | 不存在 | M、R | X |
| xyz=X | true | 裝置 | 不存在 | 55、77 | 不存在 | M、P、R | W、X |

請注意，使用 cookie ID 時，expandIDs 的設定不會影響輸出。

## 範例刪除請求

將使用 API 值的刪除請求列示在表格的第一行，點擊表格的內容將會更新並看起來像這樣：

| AAID=77 expandIDs 值<br>不重要 | AAID=77 expandIDs 值<br>不重要 | AAID=77 expandIDs 值<br>不重要 | AAID=77 expandIDs 值<br>不重要 | AAID=77 expandIDs 值<br>不重要 |
|---|---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Mary | 42 | A | Privacy-7398 | Privacy-9152 |
| Mary | 88 | B | N | Y |
| Mary | 99 | C | O | Z |
| John | 42 | D | Privacy-1866 | Privacy-8216 |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE] 只有包含 AAID = 77 和 DEL-DEVICE 標籤的資料列儲存格會受到影響。

| user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false | user=Mary<br>expandIDs=false |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-0523 | 77 | Privacy-1866 | Privacy-3681 | X |
| Privacy-0523 | 88 | Privacy-2178 | Privacy-1975 | Y |
| Privacy-0523 | 99 | Privacy-9045 | Privacy-2864 | Z |
| John | 77 | D | P | W |
| John | 88 | E | N | U |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

> [!NOTE] 只有包含 user=Mary 和 DEL-PERSON 標籤的資料列儲存格會受到影響。另外，包含 A_ID 的變數實際上可能會是 prop 或 eVar，所以它的取代值可能會是開頭為「Privacy-」再加上隨機號碼 (GUID) 的字串，而不是將數值取代為其他隨機數值。

| user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true | user=Mary<br>expandIDs=true |
|--- |---|---|---|---|
| **MyProp1** | **AAID** | **MyEvar1** | **MyEvar2** | **MyEvar3** |
| Privacy-5782 | 09 | Privacy-0859 | Privacy-8183 | Privacy-9152 |
| Privacy-5782 | 16 | Privacy-6104 | Privacy-2911 | Privacy-6821 |
| Privacy-5782 | 83 | Privacy-2714 | Privacy-0219 | Privacy-4395 |
| John | 09 | D | Privacy-8454 | Privacy-8216 |
| John | 16 | E | Privacy-2911 | Privacy-2930 |
| John | 44 | F | Q | V |
| John | 55 | G | R | X |
| Alice | 66 | A | N | W |

請注意下列事項：

* 包含 `user=Mary` 和 `DEL-DEVICE` 或 `DEL-PERSON` 標籤的資料列儲存格會受到影響，如果包含 `user=Mary` 的資料列上，包含任何 Visitor ID 的資料列有加上 `DEL-DEVICE` 標籤的儲存格，也會受到影響。
* `MyEvar2`第四和第五行的 會更新，因為這些兩行包含的 Visitor ID 值與第一和第二行的值相同，因此 ID 擴增會將其納入裝置層級的刪除作業。
* 第二和第五行的 `MyEvar2` 值在刪除前後相符，不過在刪除後就不再符合最後一行的值 N，因為該資料列並未隨著刪除請求而更新。
* `MyEvar3` 在沒有 ID 擴增時的行為非常不同，因為沒有 ID 擴增就沒有相匹配的 `ID-DEVICES`。現在，前五個資料列的 `AAID` 均相符。
