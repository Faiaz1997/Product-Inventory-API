# Product Inventory Management API

This is a CRUD-based RESTful API for Product Inventory management built with Node.js, Express.js, and MongoDB. It allows users to create, read, update, and delete products.

## Features

- Create a new product
- Retrieve all products or a single product by ID
- Update product details
- Delete a product
- Pagination, sorting, and filtering
- Basic authentication with JWT

## Technologies Used

- Node.js
- Express.js
- MongoDB & Mongoose
- dotenv for environment variables
- cors for enabling CORS
- body-parser for handling JSON requests
- nodemon for development
- jsonwebtoken for authentication

## Getting Started

### Prerequisites

- Node.js and npm installed on your machine.
- MongoDB installed locally or a MongoDB Atlas account.

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd product-inventory-api
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory and add your MongoDB connection string:
   ```ini
   MONGO_URI=your-mongodb-connection-string
   PORT=5000
   JWT_SECRET=your-secret-key
   ```
4. Start the server:
   ```bash
   npm run dev
   ```
5. For production:
   ```bash
   npm start
   ```

## API Endpoints

### Base URL
```
http://localhost:5000/api
```

### Authentication
1. **POST /api/auth/login**  
   Authenticate a user and receive a JWT token.  
   Example Request Body:
   ```json
   {
     "username": "admin",
     "password": "password"
   }
   ```

### Product Endpoints

1. **GET /api/products**  
   Retrieve all products with optional pagination, sorting, and filtering.  
   Example Query Parameters:
   ```
   ?category=Electronics&sortBy=price&order=asc&page=1&limit=10
   ```

2. **GET /api/products/:id**  
   Retrieve a specific product by its ID.

3. **POST /api/products**  
   Create a new product.  
   Example Request Body:
   ```json
   {
     "name": "Wireless Headphones",
     "price": 49.99,
     "category": "Electronics",
     "stock": 25,
     "description": "Bluetooth over-ear headphones with noise cancellation"
   }
   ```

4. **PUT /api/products/:id**  
   Update a product by its ID.  
   Example Request Body:
   ```json
   {
     "price": 59.99,
     "stock": 30
   }
   ```

5. **DELETE /api/products/:id**  
   Delete a product by its ID.

## Testing the API

### Using Browser
- You can test GET endpoints by navigating to `http://localhost:5000/api/products`.

### Using Postman
- Use Postman or any API testing tool to test POST, PUT, and DELETE endpoints by setting the proper HTTP method and providing the JSON data in the request body.

## Deployment
- You can deploy the API on platforms like Render, Vercel, or Railway.

## License
This project is licensed under the MIT License.
