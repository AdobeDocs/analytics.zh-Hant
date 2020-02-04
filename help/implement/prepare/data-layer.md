---
title: 建立資料層
description: 瞭解 Analytics 實施中的資料層是什麼，以及如何用來對映 Adobe Analytics 中的變數。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 建立資料層

資料層是網站上JavaScript物件的架構，包含您實作中使用的所有變數值。 它可讓您在實作中提供更佳的控制與更輕鬆的維護。

## 必備條件

[建立解決方案設計檔案](solution-design.md) -您的組織必須符合追蹤需求。 在與組織中的開發團隊接洽之前，請務必準備好解決方案設計檔案。

## 工作流程

使用資料層實作Adobe Analytics通常會遵循下列步驟：

1. **與您的網站開發團隊合作，實作資料層**:您的網站開發團隊主要負責確保資料層物件填入正確的值。 請與您的網站開發團隊一起檢閱此頁面，以確保團隊之間的期望相符。
   > [!NOTE] 依照Adobe建議的資料層規格進行選擇。 如果您已有資料層，或選擇不依循Adobe的規格，請確定您的組織會依循要遵循的規格。
2. **使用瀏覽器主控台驗證您的資料層**:建立資料層後，您就可以使用任何瀏覽器的開發人員主控台來驗證其是否運作。 您可以使用金鑰，在大部分的瀏覽器中開啟開發人員 `F12` 主控台。 範例變數值應為 `digitalData.page.pageInfo.pageID`。
3. **使用Adobe Experience Platform Launch將資料層物件對應至Launch資料元素**:在Launch中建立資料元素，並將它們對應至資料層中概述的JavaScript屬性。
4. **使用Launch中的Adobe Analytics擴充功能，將資料元素對應至Analytics變數**:在解決方案設計檔案後，將每個資料元素指派給適當的Analytics變數。

## 規格

Adobe建議遵循客 [戶體驗數位資料社群小組](https://www.w3.org/2013/12/ceddl-201312.pdf) ( [Customer Experience Digital Data Community Group)概述的客戶體驗數位資料層](https://www.w3.org/community/custexpdata/)。 請使用下列章節來瞭解資料層元素與Adobe Analytics的互動方式。

建議使用的總體資料層對象是 `digitalData`。 下列範例會列出較完整的資料層JSON物件，其中包含範例值：

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
            subCategory1: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product1: {
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    },
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
    event1: {
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    component1: {
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    },
    user1: {
        segment: "Premium membership",
        profile1: {
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
        }
    },
    privacy: {
        accessCategories1: {
            categoryName: "Default",
            domains: "adobedtm.com"
        }
    },
    version: "1.0"
}
```

使用「 [客戶體驗數位資料層](https://www.w3.org/2013/12/ceddl-201312.pdf) 」報表，以取得每個物件和子物件的詳細資訊。 並非所有網站都使用所有物件；例如，如果您托管新聞網站，則您不太可能使用該物 `digitalData.product` 件。

資料層是可擴展的；如果您的組織有特定的需求，您可以在資料層中加入物件，以符合這些需求。

## 設定資料層值

資料層通常會產生伺服器端，並參照用來建立網站內容的相同物件。 根據組織解決方案設計檔案中設定的追蹤需求，建立網站的 [資料層](solution-design.md)。
