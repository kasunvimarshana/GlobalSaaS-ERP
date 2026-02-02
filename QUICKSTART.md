# Quick Start Guide - GlobalSaaS-ERP

## 🚀 Getting Started in 5 Minutes

### Prerequisites
- PHP 8.2 or higher
- Composer
- SQLite (default) or MySQL/PostgreSQL
- Node.js 18+ (for frontend, coming soon)

### Step 1: Clone and Setup
```bash
# Clone the repository
git clone https://github.com/kasunvimarshana/GlobalSaaS-ERP.git
cd GlobalSaaS-ERP/backend

# Install dependencies (already done in this environment)
composer install

# Setup environment
cp .env.example .env
php artisan key:generate

# Run migrations
php artisan migrate

# (Optional) Seed sample data
php artisan db:seed
```

### Step 2: Start the Server
```bash
php artisan serve
# Server will start at http://localhost:8000
```

### Step 3: Test the API

#### Register a User
```bash
curl -X POST http://localhost:8000/api/v1/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "tenant_id": 1,
    "name": "John Doe",
    "email": "john@example.com",
    "password": "password123",
    "password_confirmation": "password123"
  }'
```

#### Login and Get Token
```bash
curl -X POST http://localhost:8000/api/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "john@example.com",
    "password": "password123"
  }'

# Save the token from response
TOKEN="your-token-here"
```

#### Create a Product
```bash
curl -X POST http://localhost:8000/api/v1/inventory/products \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Laptop Dell XPS 15",
    "category": "Electronics",
    "brand": "Dell",
    "unit": "pcs",
    "cost_price": 1200.00,
    "selling_price": 1500.00,
    "track_stock": true,
    "min_stock_level": 5,
    "reorder_level": 10
  }'
```

#### Add Stock
```bash
curl -X POST http://localhost:8000/api/v1/inventory/stock/add \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "branch_id": 1,
    "product_id": 1,
    "quantity": 50,
    "unit_cost": 1200.00,
    "notes": "Initial stock"
  }'
```

#### Check Stock Balance
```bash
curl -X GET "http://localhost:8000/api/v1/inventory/stock/balance?product_id=1&branch_id=1" \
  -H "Authorization: Bearer $TOKEN"
```

## 📋 Available API Endpoints

### Authentication
- `POST /api/v1/auth/register` - Register new user
- `POST /api/v1/auth/login` - Login
- `GET /api/v1/auth/me` - Get current user
- `POST /api/v1/auth/logout` - Logout
- `POST /api/v1/auth/refresh` - Refresh token

### Products
- `GET /api/v1/inventory/products` - List products
- `POST /api/v1/inventory/products` - Create product
- `GET /api/v1/inventory/products/{id}` - Get product
- `PUT /api/v1/inventory/products/{id}` - Update product
- `DELETE /api/v1/inventory/products/{id}` - Delete product
- `GET /api/v1/inventory/products/search?term=laptop` - Search
- `GET /api/v1/inventory/products/low-stock` - Low stock alert
- `POST /api/v1/inventory/products/bulk-import` - Bulk import

### Stock Management
- `GET /api/v1/inventory/stock/balance` - Check balance
- `POST /api/v1/inventory/stock/add` - Add stock
- `POST /api/v1/inventory/stock/remove` - Remove stock
- `POST /api/v1/inventory/stock/transfer` - Transfer stock
- `POST /api/v1/inventory/stock/adjust` - Adjust stock
- `GET /api/v1/inventory/stock/available-batches` - Get batches
- `POST /api/v1/inventory/stock/pick` - Pick using FIFO/FEFO
- `GET /api/v1/inventory/stock/movement-history` - View history

## 🎯 Common Use Cases

### Use Case 1: Receive Goods from Supplier
```bash
# 1. Create product (if not exists)
curl -X POST http://localhost:8000/api/v1/inventory/products \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "iPhone 15 Pro",
    "sku": "IPH15PRO",
    "cost_price": 999.00,
    "selling_price": 1299.00
  }'

# 2. Add stock
curl -X POST http://localhost:8000/api/v1/inventory/stock/add \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "branch_id": 1,
    "product_id": 1,
    "quantity": 100,
    "unit_cost": 999.00,
    "reference_type": "purchase_order",
    "reference_id": 1001
  }'
```

### Use Case 2: Sell Product (Issue Stock)
```bash
# Remove stock for sale
curl -X POST http://localhost:8000/api/v1/inventory/stock/remove \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "branch_id": 1,
    "product_id": 1,
    "quantity": 1,
    "reference_type": "sales_order",
    "reference_id": 2001
  }'
```

### Use Case 3: Transfer Between Branches
```bash
# Transfer stock from branch 1 to branch 2
curl -X POST http://localhost:8000/api/v1/inventory/stock/transfer \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "from_branch_id": 1,
    "to_branch_id": 2,
    "product_id": 1,
    "quantity": 10,
    "notes": "Transfer to new branch"
  }'
```

### Use Case 4: Stock Reconciliation
```bash
# Adjust stock to match physical count
curl -X POST http://localhost:8000/api/v1/inventory/stock/adjust \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "branch_id": 1,
    "product_id": 1,
    "target_balance": 95,
    "notes": "Physical count reconciliation"
  }'
```

### Use Case 5: FIFO/FEFO Picking
```bash
# Pick stock using FEFO (First Expiry First Out)
curl -X POST http://localhost:8000/api/v1/inventory/stock/pick \
  -H "Authorization: Bearer $TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "product_id": 1,
    "quantity": 5,
    "branch_id": 1,
    "strategy": "FEFO",
    "reference_type": "sales_order",
    "reference_id": 3001
  }'
```

## 🔧 Development

### Run Tests
```bash
php artisan test
```

### Clear Cache
```bash
php artisan config:clear
php artisan cache:clear
php artisan route:clear
```

### View Routes
```bash
php artisan route:list
php artisan route:list --path=api
```

### Database
```bash
# Fresh migration
php artisan migrate:fresh

# Rollback
php artisan migrate:rollback

# Check migration status
php artisan migrate:status
```

## 📚 Project Structure

```
backend/
├── app/
│   ├── Core/                    # Core infrastructure
│   ├── Models/                  # Core models (User)
│   ├── Modules/                 # Feature modules
│   │   ├── IAM/                 # Identity & Access
│   │   ├── Tenancy/             # Multi-tenancy
│   │   ├── Organization/        # Orgs & Branches
│   │   ├── Inventory/           # Inventory mgmt
│   │   └── Pricing/             # Pricing engine
│   └── Http/
│       └── Controllers/Api/     # API controllers
├── database/
│   ├── migrations/              # 18 migrations
│   └── seeders/                 # Database seeders
├── routes/
│   ├── api.php                  # API routes
│   └── web.php                  # Web routes
└── tests/                       # Test files
```

## 🆘 Troubleshooting

### Issue: "Class not found"
```bash
composer dump-autoload
```

### Issue: "SQLSTATE connection refused"
Check `.env` database settings:
```
DB_CONNECTION=sqlite
# OR for MySQL
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=erp_db
DB_USERNAME=root
DB_PASSWORD=
```

### Issue: "Route not found"
```bash
php artisan route:clear
php artisan config:clear
```

### Issue: "Unauthenticated"
Make sure you include the Bearer token:
```bash
-H "Authorization: Bearer YOUR_TOKEN_HERE"
```

## 📞 Support

- Documentation: See FINAL_IMPLEMENTATION_SUMMARY.md
- Issues: GitHub Issues
- Email: support@example.com

## 🎉 Success!

You're now ready to start building on top of this solid ERP foundation!

Next steps:
1. ✅ Backend API is ready
2. 🚧 Build Vue.js frontend
3. 🚧 Add more modules (CRM, POS, etc.)
4. 🚧 Deploy to production

Happy coding! 🚀
