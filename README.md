This project is a simple prototype for the shopify-store-front-api. Link to examples built by shopify: https://github.com/Shopify/storefront-api-examples

###
The two api's that will be used on the backend are:
1) Admin API (using graphQL)
  - Orders API (sales channel)

  - Checkout API (sales channel)

  - Analytics API (They could use this to write custom reports! Shopify has a custom query language!)
    - Report API
     -- Important Fields:
      - category
      - name
      - shopify_ql (custom query language)
    - Shopify Query Language
      - Schemas
        - Sales
        - Payments
        - Taxes
        - Visits
        - Customers

  - Products API 
    - Collect: Relationship between a product and custom collection. For every product in a collection the collect tracks the id of both the product and collection. A single product can have multiple connects allowing it to be in multiple collections
    - Collection: A grouping of products. Ex collection would be gummies. The two type are smart or custom. We may be able to put the vendor name in a collection and differntiate based on that?
    - Products: We want to use tags for each vendor. Can be added to a custom collection or smart collection.
      -- Important fields:
        - Options (customer property types) max 3 options
        - Product type
        - images (can have multiple)
        - body_html
        - tags (can be used to filter/search) up to 250 tags per product
        - variants (different versions of same product this is where all the data like price and inventory is kept)
    - Product Variants: Think of it as an implementation of a product
      --Importants fields
        - image_id
        - inventory_item_id
        - inventory_quantity
        - price
        - product_id
        - sku (unique_id needed for fufillment service)
        - taxable
        - tax_code (Avalara Ava Tax)
    - Product Image
    - Custom Collection: Allows admin to manually add products to collections
    - Smart Collection: 
  
  - Customers APIs
    - Customer API: A customer can have multiple addresses. A customer can also have custom tags.
    - Customer Address API
    - CustomerSavedSearch: Allows the admin to cache results from queries about customers
  
  - Inventory APIs:
    - InventoryItem: Represents a physical item irl with info about the good. Has a 1:1 relationship with product variants
    - InventoryLevel: Get or update amount of inventory. 1:1 relationship with items and location
    - Location: In this case only one location (grasshopprs)
  
  - Order APIs:
    - Abandonded checkouts: Incomplete checkouts. Use to allow customers to continue checkout later
    - DraftOrder: Allows admins to make orders for customers (support for letting customers call in and admins finishing order)
    - OrderAPI: Contains the customers cart
    - Order Risk: Fraud analysis
    - Refund API

  - Checkout APIs (Sales Channel)
  
  - Fulfillment APIs: Will be used to set order statuses from the vendor side

  -Store Properties API:
  

  
  - Events Webhook (Can have hooks to pretty much anything)




Questions:
- Should users be able to place orders on out of stock items.
- What are the tax codes for CBD products?
- Is the shopify dashboard good enough or do they want a custom one?
- What kind of fraud protection do you want to start with?
