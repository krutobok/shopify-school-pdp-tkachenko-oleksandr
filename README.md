# Shopify School PDP Tkachenko Oleksandr

This repository contains a custom Product Page implementation for a
Shopify store, built using **Shopify CLI** and **Liquid**.

## 🔗 Links

-   **Development Store:** \[Вставте посилання на магазин\]
-   **Store Password:** `[Вставте пароль]`
-   **GitHub Repository:** \[Вставте посилання на репозиторій\]

## 🛠 Technologies Used

-   **Shopify CLI**
-   **Liquid** 
-   **HTML / CSS** (Tailwind)
-   **JavaScript** (Vanilla ES6+)
-   **Swiper** 

## 🚀 How to Run Locally

1.  Clone the repository:

    ``` bash
    git clone [Вставте посилання на репозиторій]
    ```

2.  Navigate to the project folder:

    ``` bash
    cd [Назва вашої папки]
    ```

3.  Install dependencies:

    ``` bash
    npm install
    ```

4.  Start the development server:

    ``` bash
    shopify theme dev
    ```

5.  Open the provided preview URL in your browser.

## ✅ Implemented Sections & Features

The project implements a comprehensive product page experience with the
following sections:

-   **Main Product Section** -- core product details, image gallery, and
    purchase form\
-   **Banner with CTA** -- promotional banner with a call-to-action
    button\
-   **Recommended Products** -- "You may also like" block with related
    items\
-   **Reviews Block** -- customer testimonials section\
-   **Accordion** -- collapsible tabs for Description, Shipping, and
    Returns

## Bonus Features

### Sticky Add-to-Cart

-   Floating bar for Desktop & Mobile\
-   Appears only when the main "Add to Cart" button is out of view\
-   Includes product info, variant selectors, and purchase button

### Variant Image Change

-   Selecting a color variant updates the main gallery image
    automatically

### Scroll Gallery (Desktop)

**Sticky Gallery (Desktop):**
   - A modern gallery layout where the images remain fixed (sticky) on the left side while the user scrolls through the product details on the right. 

### Product Stock Indicator

Dynamic inventory status: - **In stock** -- high inventory\
- **Low stock** -- medium inventory\
- **Running out** -- critical inventory

### Size Guide (Metaobjects)

-   Modal popup powered by Shopify Metaobjects\
-   Content (images, tables) is loaded dynamically\
-   Depends on the assigned size standard

## Data Structure (Metafields & Metaobjects)

### 1. Product Metafields

  ---------------------------------------------------------------------------------
  Namespace              Key                  Type           Purpose
  ---------------------- -------------------- -------------- ----------------------
| `custom.related_colors` | List of Products | Links different products as color swatches. |
| `custom.product_note` | Single Line Text | Promotional text (e.g., "Safe Checkout") in the buy box. |
| `custom.product_notes` | Rich Text | Content for the "Description" accordion tab. |
| `custom.size_fit` | Rich Text | Content for the "Size & Fit" or details accordion tab. |
| `custom.returns_policy` | Rich Text | Content for the "Returns" accordion tab. |
| `custom.reviews_json` | JSON | Data structure containing customer reviews. |
| `custom.product_size_guide` | Metaobject Reference | Links the product to a specific `Size Guide`. |
  ---------------------------------------------------------------------------------

### 2. Metaobjects

**Type:** Size Standard (`size_standard`)

  Field Name    Key           Type               Purpose
  ------------- ------------- ------------------ ---------------------------
  Name          name          Single Line Text   Guide identifier
  Image         image         File (Image)       Visual size chart
  Description   description   Rich Text          HTML table with size grid
