# Restaurant-Food-Ordering-System
![Node.js](https://img.shields.io/badge/Node.js-16.x-green.svg)
![Express.js](https://img.shields.io/badge/Express.js-4.x-blue.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-6.x-brightgreen.svg)

This is a robust backend server for a food delivery application, built with Node.js, Express, and MongoDB. It provides a complete set of RESTful APIs to handle user authentication, restaurant management, food items, categories, and order processing.

The application features a clear separation of concerns, with distinct modules for routes, controllers, and models, making it scalable and easy to maintain. It includes JWT-based authentication and role-based access control to secure the endpoints.

## Key Features

* **User Authentication**: Secure user registration and login system using **JSON Web Tokens (JWT)**.
* **Password Security**: Passwords are encrypted using **bcryptjs** before being stored.
* **Role-Based Access Control**: Differentiates between regular users (`client`) and `admin`, with specific routes protected by admin middleware.
* **CRUD Functionality**: Complete Create, Read, Update, and Delete operations for:
    * Restaurants
    * Food Items
    * Food Categories
    * User Profiles
* **Order Management**: API endpoints to place new orders and for admins to update the status of an order (e.g., "preparing", "on the way", "delivered").
* **Profile Management**: Users can view their profile, update their information, and reset their password.

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

* **Node.js** (v14 or higher)
* **npm**
* **MongoDB** (local instance or a cloud service like MongoDB Atlas)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Install NPM packages:**
    ```sh
    npm install
    ```

3.  **Set up environment variables:**
    Create a `.env` file in the root directory and add the following variables. Use `.env.example` as a template.

    ```env
    # Port for the server to run on
    PORT=8080

    # MongoDB Connection String
    MONGO_URL=mongodb://localhost:27017/foodapp

    # JWT Secret Key for signing tokens
    JWT_SECRET=your_jwt_secret_key
    ```

4.  **Start the server:**
    ```sh
    npm run server
    ```
    The server will start on the port you specified in your `.env` file (e.g., `http://localhost:8080`).

## API Endpoints

Here is a summary of the available API endpoints.

| Method | Endpoint | Description | Protected |
| :--- | :--- | :--- | :--- |
| **POST** | `/api/v1/auth/register` | Register a new user. | No |
| **POST** | `/api/v1/auth/login` | Log in an existing user. | No |
| **GET** | `/api/v1/user/getUser` | Get the current user's profile. | Yes |
| **PUT** | `/api/v1/user/updateUser` | Update user profile information. | Yes |
| **POST** | `/api/v1/user/updatePassword`| Update the user's password. | Yes |
| **GET** | `/api/v1/resturant/getAll` | Get a list of all restaurants. | No |
| **POST**| `/api/v1/resturant/create` | Create a new restaurant. | Yes |
| **GET** | `/api/v1/food/getAll` | Get a list of all food items. | No |
| **POST** | `/api/v1/food/placeorder` | Place a new food order. | Yes |
| **POST** | `/api/v1/food/orderStatus/:id`| Update the status of an order. | Yes (Admin) |

