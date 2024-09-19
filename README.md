# Learn-GraphQL

In Shopify, both the GraphQL Admin API and the GraphQL Storefront API are used to interact with store data, but they serve different purposes and have distinct scopes. Here are the key differences:

### 1. **Purpose and Scope:**
   - **GraphQL Admin API:**
     - This API is used by merchants or app developers to manage a store's internal operations.
     - It provides access to sensitive and administrative data like orders, products, customers, inventory, shipping, and shop settings.
     - Suitable for tasks like product management, order fulfillment, and inventory tracking.
   - **GraphQL Storefront API:**
     - This API is intended for customer-facing interactions.
     - It allows public access to a store’s product data, collections, customer accounts, and checkout processes, but without exposing sensitive data.
     - Used to build custom storefronts, mobile apps, or headless e-commerce solutions.

### 2. **Access Permissions:**
   - **GraphQL Admin API:**
     - Requires **authentication** with an OAuth token generated for private or public apps.
     - Only merchants or app developers with proper permissions can use this API.
     - Exposes sensitive information like customer addresses, orders, and fulfillment details.
   - **GraphQL Storefront API:**
     - More open and is designed for **public access** with a storefront token.
     - Does **not** allow access to sensitive data like order or customer information unless it's related to the logged-in customer session (e.g., customer-specific data during checkout).

### 3. **Rate Limits:**
   - **GraphQL Admin API:**
     - Has higher rate limits for merchants and apps because it handles backend and operational tasks that may require large amounts of data.
     - Rate limit: 1,000 cost units per second for API calls.
   - **GraphQL Storefront API:**
     - Has lower rate limits because it’s designed to be used on the public-facing side where user requests should be optimized.
     - Rate limit: 50 cost units per second per Storefront token.

### 4. **Use Cases:**
   - **GraphQL Admin API:**
     - Manage products, customers, orders, and other backend operations.
     - Suitable for building custom apps for merchants to control various aspects of their store.
     - Examples: Adding new products, updating product inventory, fulfilling orders.
   - **GraphQL Storefront API:**
     - Display products, collections, and other storefront data to customers.
     - Used for building custom storefronts, fetching product and collection information, and handling customer logins or checkouts.
     - Examples: Show product listings, allow customers to add items to a cart, create a checkout process.

### 5. **Data Visibility:**
   - **GraphQL Admin API:**
     - Full access to store data, including order histories, payment transactions, and private customer information.
   - **GraphQL Storefront API:**
     - Limited to public data (e.g., products, collections) and the current user's checkout or customer session data.
     - Cannot access private order details or sensitive customer information unless linked to a customer session.

### Summary:
- **Admin API** is for **internal store management** (products, orders, customers, inventory).
- **Storefront API** is for **public-facing operations** (displaying products, handling checkouts).
