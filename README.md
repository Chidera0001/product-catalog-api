# Product Catalog API

A RESTful API for a product catalog system that powers e-commerce platforms. This API provides endpoints for managing products, categories, inventory, and reporting.

## Features

- **Product Management**: CRUD operations for products with support for variants
- **Category Management**: Organize products into hierarchical categories
- **Inventory Management**: Track stock levels and inventory movements
- **Search & Filtering**: Advanced search and filtering capabilities
- **Collections**: Group products into collections for easier discovery
- **Reporting**: Generate reports for low stock, inventory value, and more

## Tech Stack

- Node.js
- Express.js
- MongoDB (with Mongoose ORM)
- Swagger for API documentation

## Prerequisites

- Node.js (v14+ recommended)
- MongoDB (v4+ recommended)
- npm or yarn

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd product-catalog-api
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory
   - Add the following variables:
     ```
     PORT=3000
     MONGODB_URI=mongodb://localhost:27017/product_catalog
     NODE_ENV=development
     ```

4. Start the server:
   ```bash
   npm run dev
   ```

## API Documentation

Once the server is running, you can access the Swagger API documentation at:
```
http://localhost:3000/api-docs
```

## API Endpoints

### Products

- `GET /api/products` - Get all products with filtering and pagination
- `GET /api/products/:id` - Get a specific product by ID
- `GET /api/products/slug/:slug` - Get a specific product by slug
- `POST /api/products` - Create a new product
- `PUT /api/products/:id` - Update a product
- `DELETE /api/products/:id` - Delete a product
- `GET /api/products/search` - Search products by name, description, etc.
- `GET /api/products/collection/:collection` - Get products by collection
- `GET /api/products/:id/variants` - Get variants for a product
- `POST /api/products/:id/variants` - Add a variant to a product

### Categories

- `GET /api/categories` - Get all categories
- `GET /api/categories/:id` - Get a specific category
- `POST /api/categories` - Create a new category
- `PUT /api/categories/:id` - Update a category
- `DELETE /api/categories/:id` - Delete a category

### Inventory

- `POST /api/inventory/update` - Update inventory for a variant
- `GET /api/inventory/levels` - Get current inventory levels
- `GET /api/inventory/transactions` - Get all inventory transactions
- `GET /api/inventory/product/:productId` - Get inventory transactions for a product
- `GET /api/inventory/variant/:variantId` - Get inventory transactions for a variant

### Reports

- `GET /api/reports/low-stock` - Get low stock report
- `GET /api/reports/inventory-value` - Get inventory value report
- `GET /api/reports/inventory-movements` - Get inventory movements report
- `GET /api/reports/catalog-stats` - Get catalog statistics

## Data Models

### Product
- Basic information (name, description, SKU)
- Pricing (basePrice, compareAtPrice)
- Categorization (categories, collections, tags)
- Media (images)
- SEO metadata
- Variants management

### Variant
- Product reference
- Variant attributes (size, color, etc.)
- Pricing
- Inventory management
- Dimensions and weight

### Category
- Hierarchical structure
- Name and description
- Slug for SEO-friendly URLs

### Inventory Transaction
- Track stock movements
- Support different transaction types (stock in, stock out, adjustments)
- Maintain audit trail with timestamps and user references

## Error Handling

The API provides consistent error responses with appropriate HTTP status codes:

- `400 Bad Request` - Input validation errors
- `404 Not Found` - Resource not found
- `500 Internal Server Error` - Server-side errors

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the ISC License.