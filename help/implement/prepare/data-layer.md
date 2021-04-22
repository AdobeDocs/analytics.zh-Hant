---
title: 建立資料層
description: 瞭解 Analytics 實施中的資料層是什麼，以及如何用來對映 Adobe Analytics 中的變數。
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '479'
ht-degree: 100%

---

# 建立資料層

資料層是網站上 JavaScript 物件的架構，包含實施內的所有變數值。可讓您在實施中進行更深入的控制及更輕鬆的維護。

## 必要條件

[建立解決方案設計文件](solution-design.md) - 貴組織必須符合追蹤要求。確保在前往找組織內的開發團隊之前，先使用解決方案設計文件做好準備。

## 工作流程

使用資料層實施 Adobe Analytics 時，通常會依照下列步驟操作：

1. **與您的網站開發團隊合作實施資料層**：您的網站開發團隊主要負責確保資料層物件填入正確的值。請與您的網站開發團隊一起檢閱此頁面，確保團隊之間的期望相同。

   >[!NOTE]
   >
   > 可選擇遵循 Adobe 建議的資料層規格。如果您已有資料層，或選擇不遵循 Adobe 的規格，請確定貴組織對於需遵循的規格有共識。
1. **使用瀏覽器主控台驗證資料層**：建立資料層後，可以使用任何瀏覽器的開發人員主控台來驗證資料層是否正常運作。您可以使用 `F12` 鍵，在大部分的瀏覽器中開啟開發人員主控台。範例變數值應為 `digitalData.page.pageInfo.pageID`。
1. **使用 Adobe Experience Platform Launch 將資料層物件對應至 Launch 資料元素**：在 Launch 中建立資料元素，並將它們對應至資料層中羅列的 JavaScript 屬性。
1. **在 Launch 中使用 Adobe Analytics 擴充功能，將資料元素對應至 Analytics 變數**：依循解決方案設計文件，將每個資料元素指派給適當的 Analytics 變數。

## 規格

Adobe 建議遵循[客戶體驗數位資料社群小組](https://www.w3.org/community/custexpdata/)所提出的[客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf)。請透過下列章節瞭解資料層元素與 Adobe Analytics 互動的方式。

建議使用的整體資料層物件是 `digitalData`。下列範例列出較完整的資料層 JSON 物件並提供範例值：

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

使用[客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf)報表，取得每個物件和子物件的詳細資訊。並非所有網站都使用全部物件，例如，如果您托管一個新聞網站，您就不可能使用 `digitalData.product` 物件陣列。

資料層可擴展；如果貴組織有特定的需求，您可以在資料層中加入物件以符合這些需求。

## 設定資料層值

資料層通常會產生伺服器端，並參考用來建立網站內容的相同物件。根據貴組織[解決方案設計文件](solution-design.md)中設定的追蹤要求，建立網站的資料層。

## 後續步驟

[將資料層物件對應至資料元素](../launch/layer-to-elements.md)：在 Adobe Experience Platform Launch 中使用您網站的資料層。
