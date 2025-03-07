# 🍽️ Plate Planner - Backend Documentation

## 📌 Overview

The backend of **Plate Planner** is built using **Node.js** with **Express.js** as the web framework. It connects to a **MongoDB** database using **Mongoose** and provides a REST API for user authentication, recipe management, and weather-based recipe recommendations.

---

## 🛠️ Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```env
PORT=5000
DB=mongodb+srv://your_mongo_connection_string
SECRET_KEY=your_secret_key
WEATHER_API_KEY=your_weather_api_key
EDAMAM_API_KEY=your_edamam_api_key
EDAMAM_APP_ID=your_edamam_app_id
```

Replace the placeholders with actual values before running the application.

---

## 📌 API Documentation

### 🔹 User Endpoints

| Method     | Route                  | Description           | Request Parameters                    | Response                                                                  |
| ---------- | ---------------------- | --------------------- | ------------------------------------- | ------------------------------------------------------------------------- |
| **POST**   | `/user/register`       | Register a new user   | `name`, `email`, `pass`, `cPass`      | `{ message: 'User Created', user: { name, email } }`                      |
| **POST**   | `/user/login`          | Log in a user         | `email`, `pass`                       | `{ message: 'Login success', token: 'JWT token', user: { name, email } }` |
| **DELETE** | `/user/delete/{email}` | Delete a user profile | `Authorization: Bearer token`, `pass` | `{ message: 'User Deleted' }`                                             |

### 🔹 Recipe Endpoints

| Method     | Route                                 | Description                             | Request Parameters                                                                                                                                          | Response                                                                                                                                              |
| ---------- | ------------------------------------- | --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| **POST**   | `/recipe/create-recipe`               | Create a new recipe                     | `Authorization: Bearer token`, `name`, `image`, `ingredients`, `season`, `occasion`, `type`, `recipeType`, `time`, `difficulty`, `servings`, `instructions` | `{ recipe: { userId, name, image, ingredients, season, occasion, type, recipeType, time, difficulty, servings, nutritionPerServing, instructions } }` |
| **POST**   | `/recipe/search`                      | Search recipes based on user request    | `name / image / ingredients / season / occasion / type / recipeType / time / difficulty / servings / instructions`                                          | `[recipes]`                                                                                                                                           |
| **PUT**    | `/recipe/update-recipe/{recipeId}`    | Update a recipe                         | `Authorization: Bearer token`, `name / image / ingredients / season / occasion / type / recipeType / time / difficulty / servings / instructions`           | `{ updated recipe }`                                                                                                                                  |
| **DELETE** | `/recipe/delete-recipe/{recipeId}`    | Delete a recipe                         | `Authorization: Bearer token`                                                                                                                               | `{ message: 'Recipe deleted successfully' }`                                                                                                          |
| **POST**   | `/recipe/weather-suggestions`         | Get recipe suggestions based on weather | `lat`, `lon`                                                                                                                                                | `{ temperature, weatherDescription, placeName, season, recipes }`                                                                                     |
| **POST**   | `/recipe/get-recipe-by-userId`        | Get recipes created by a user           | `Authorization: Bearer token`, `userId`                                                                                                                     | `{ recipes }`                                                                                                                                         |
| **GET**    | `/recipe/get-recipe-by-id/{recipeId}` | Get a recipe by ID                      | -                                                                                                                                                           | `{ recipes }`                                                                                                                                         |
| **GET**    | `/recipe/get-recipes`                 | Get all recipes                         | -                                                                                                                                                           | `{ recipes }`                                                                                                                                         |

---

## 🛠️ Dependencies

### 📦 Main Dependencies

- **axios**: Handles HTTP requests for fetching data from APIs.
- **bcrypt**: Encrypts user passwords for secure storage.
- **bcryptjs**: Alternative library for hashing passwords.
- **cors**: Enables Cross-Origin Resource Sharing (CORS) for handling requests from different origins.
- **dotenv**: Loads environment variables from a `.env` file.
- **express**: Web framework for building the backend server.
- **jsonwebtoken**: Implements authentication using JSON Web Tokens (JWT).
- **mongoose**: Handles MongoDB database operations through an Object Data Modeling (ODM) tool.
- **multer**: Middleware for handling file uploads (e.g., recipe images).

### 🔧 Development Dependencies

- **nodemon**: Automatically restarts the server during development when file changes are detected.

---

## 🔒 Authentication

- **JWT (JSON Web Token)** is used for authentication.
- Users receive a token upon successful login, which must be included in the `Authorization` header for protected routes.

---

## 📄 Error Handling

API responses return appropriate HTTP status codes:

- `200 OK`: Successful requests.
- `400 Bad Request`: Invalid input or missing parameters.
- `401 Unauthorized`: Invalid or missing authentication token.
- `404 Not Found`: Resource not found.
- `500 Internal Server Error`: Unexpected server error.

---

## 👨‍💻 Contributing

We welcome contributions! Feel free to fork the repo, create a new branch, and submit a pull request.

Happy Coding! 🚀
