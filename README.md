# Shopify School PDP Tkachenko Oleksandr

This repository contains a custom Product Page implementation for a
Shopify store, built using **Shopify CLI** and **Liquid**.

## Links

-   **Development Store:** https://tkachenko-oleksandr-test-store.myshopify.com/products/nike-air-max-plus-white?preview_theme_id=184300896565
-   **Store Password:** nowvol
-   **GitHub Repository:** https://github.com/krutobok/shopify-school-pdp-tkachenko-oleksandr

## Technologies Used

-   **Shopify CLI**
-   **Liquid** 
-   **HTML / CSS** (Tailwind)
-   **JavaScript** (Vanilla ES6+)
-   **Swiper** 

## How to Run Locally

1.  Clone the repository:

    ``` bash
    git clone https://github.com/krutobok/shopify-school-pdp-tkachenko-oleksandr.git
    ```

2.  Navigate to the project folder:

    ``` bash
    cd shopify-school-pdp-tkachenko-oleksandr
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

## Implemented Sections & Features

The project implements a comprehensive product page experience with the
following sections:

-   **Main Product Section** -- core product details, image gallery, and
    purchase form
-   **Banner with CTA** -- promotional banner with a call-to-action
    button
-   **Recommended Products** -- "You may also like" block with related
    items
-   **Reviews Block** -- customer testimonials section
-   **Accordion** -- collapsible tabs for Description, Shipping, and
    Returns

## Bonus Features

### Sticky Add-to-Cart

-   Floating bar for Desktop & Mobile
-   Appears only when the main "Add to Cart" button is out of view
-   Includes product info, variant selectors, and purchase button

### Variant Image Change

-   Selecting a color variant updates the main gallery image
    automatically

### Sticky Gallery (Desktop):
   - A modern gallery layout where the images remain fixed (sticky) on the left side while the user scrolls through the product details on the right. 

### Product Stock Indicator

Dynamic inventory status: - **In stock** -- high inventory
- **Low stock** -- medium inventory
- **Running out** -- critical inventory

### Size Guide (Metaobjects)

-   Modal popup powered by Shopify Metaobjects
-   Content (images, tables) is loaded dynamically
-   Depends on the assigned size standard

## Data Structure (Metafields & Metaobjects)

### 1. Product Metafields
| Namespace & Key | Type | Purpose |
| :--- | :--- | :--- |
| `custom.related_colors` | List of Products | Links different products as color swatches. |
| `custom.product_note` | Single Line Text | Promotional text (e.g., "Safe Checkout") in the buy box. |
| `custom.product_notes` | Rich Text | Content for the "Description" accordion tab. |
| `custom.size_fit` | Rich Text | Content for the "Size & Fit" or details accordion tab. |
| `custom.returns_policy` | Rich Text | Content for the "Returns" accordion tab. |
| `custom.reviews_json` | JSON | Data structure containing customer reviews. |
| `custom.product_size_guide` | Metaobject Reference | Links the product to a specific `Size Guide`. |
  ---------------------------------------------------------------------------------

### 2. Metaobjects
The size chart system is built using two related metaobjects to create a dynamic table.
#### Type 1: Size Guide (size_guide)
Functions as the "Parent" object that groups rows together.
| Field Name | Key | Type | Purpose |
| :--- | :--- | :--- | :--- |
| **Title** | `title` | Single Line Text | Internal name of the guide (e.g., "Men's Shoes"). |
| **Rows** | `rows` | List of Metaobjects | References multiple `Size Standard` objects to build the table rows. |
  #### Type 2: Size Standard (size_standard)
  | Field Name | Key | Type | Purpose |
| :--- | :--- | :--- | :--- |
| **Title** | `title` | Single Line Text | Internal row identifier. |
| **Display Title** | `display_title` | Single Line Text | The visible row header (e.g., "US Size"). |
| **Size Columns** | *various* | Single Line Text | Fields for specific sizes (e.g., `Size EU 35.5`, `Size UK 6`). |
