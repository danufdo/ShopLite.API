# ShopLite API – ASP.NET Core Web API

This is the backend API for the **ShopLite E-Commerce Application**. This API is built using **ASP.NET Core Web API** and connects to a **MySQL database**. The API provides product management and cart management endpoints for the Next.js frontend.

---

# 🧱 Tech Stack

* ASP.NET Core Web API
* Entity Framework Core
* MySQL Database
* Pomelo MySQL Provider
* Swagger (API Testing)

---

# 📁 Project Structure

```
ShopLite.API
│
├── Controllers
│   ├── ProductsController.cs
│   └── CartController.cs
│
├── Data
│   └── AppDbContext.cs
│
├── Models
│   ├── Product.cs
│   └── CartItem.cs
│
├── Migrations
│
├── Program.cs
├── appsettings.json
└── ShopLite.API.csproj
```

---

# ⚙️ Setup Instructions

## 1. Clone the Repository

```
git clone https://github.com/your-username/shoplite-api.git
cd shoplite-api
```

## 2. Install Dependencies

```
dotnet restore
```

## 3. Configure MySQL Database

Open `appsettings.json` and update the connection string:

```json
"ConnectionStrings": {
  "DefaultConnection": "server=localhost;port=3306;database=shoplite;user=root;password=yourpassword;"
}
```

## 4. Run Database Migrations

```
dotnet ef migrations add InitialCreate
dotnet ef database update
```

This will create the database and tables automatically.

## 5. Run the API

```
dotnet run
```

Swagger UI:

```
https://localhost:5001/swagger
```

---

# 🔗 API Endpoints

## Products

| Method | Endpoint      | Description      |
| ------ | ------------- | ---------------- |
| GET    | /api/products | Get all products |
| POST   | /api/products | Add new product  |

### Example Product JSON

```json
{
  "name": "iPhone 14",
  "price": 1200,
  "image": "https://example.com/iphone.jpg",
  "category": "Electronics"
}
```

---

## Cart

| Method | Endpoint       | Description           |
| ------ | -------------- | --------------------- |
| GET    | /api/cart      | Get cart items        |
| POST   | /api/cart      | Add item to cart      |
| DELETE | /api/cart/{id} | Remove item from cart |

### Example Cart JSON

```json
{
  "productId": 1,
  "quantity": 1
}
```

---

# 🌐 Frontend Connection

Your Next.js frontend should connect to this API using:

```
https://localhost:5001/api
```

Example:

```
GET https://localhost:5001/api/products
POST https://localhost:5001/api/cart
```

---

# 🛠️ Future Improvements

* JWT Authentication
* Order Management
* User Accounts
* Payment Integration
* Docker Support
* CI/CD Pipeline
* Kubernetes Deployment

---

# 👨‍💻 Author

Developed as a **Full Stack + DevOps Portfolio Project** using:

* Next.js Frontend
* ASP.NET Core Web API
* MySQL Database
* Docker & Kubernetes (Planned)

---

# 📄 License

This project is for educational and portfolio purposes.
