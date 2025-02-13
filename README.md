# 🍽️ Plate Planner 📅🥗✨

## Description
A smart meal planning app that offers **personalized recipe suggestions**, **meal plans**, and **nutritional insights** based on user preferences. Features include ingredient-based recommendations, seasonal filters, weather-adaptive meals, and more! 🚀

## Features
- 🔐 User authentication
- 🛒 Ingredient-based recipe suggestions
- 📊 Real-time nutritional analysis
- 🔍 Filter recipes by season, occasion, type, meal category, time, and difficulty
- 🌦️ Weather-based meal recommendations

---

## 🚀 Run the App

### 1️⃣ Clone the Project
```sh
git clone https://github.com/sayam-1705/plate-planner.git
cd plate-planner-app
```

### 2️⃣ Install Dependencies
Navigate to the **backend** and **frontend** folders separately and install dependencies:
```sh
cd backend
npm install
cd ../frontend
npm install
```

### 3️⃣ Run the App Locally

1. Open the folder **"Smart Recipe Planner"** with **VS Code**
2. Open a new terminal and run the following commands:
   ```sh
   cd backend
   npm run start
   ```
3. Open another new terminal and run the following commands:
   ```sh
   cd frontend
   npm run dev
   ```
4. In the browser, enter: **http://localhost:5173/**

---

## 📌 API Documentation

### 🔹 User Endpoints

| Method | Route | Description | Request Parameters | Response |
|--------|-------|-------------|---------------------|----------|
| **POST** | `/user/register` | Register a new user | `name`, `email`, `pass`, `cPass` | `{ message: 'User Created', user: { name, email } }` |
| **POST** | `/user/login` | Log in a user | `email`, `pass` | `{ message: 'Login success', token: 'JWT token', user: { name, email } }` |
| **DELETE** | `/user/delete/example12345@gmail.com` | Delete a user profile | `Authorization: Bearer token`, `pass` | `{ message: 'User Deleted' }` |

### 🔹 Recipe Endpoints

| Method | Route | Description | Request Parameters | Response |
|--------|-------|-------------|---------------------|----------|
| **POST** | `/recipe/create-recipe` | Create a new recipe | `Authorization: Bearer token`, `name`, `image`, `ingredients`, `quantity`, `season`, `occasion`, `type`, `recipeType`, `time`, `difficulty`, `servings`, `instructions` | `{ recipe: { userId, name, image, ingredients, season, occasion, type, recipeType, time, difficulty, servings, nutritionPerServing, instructions } }` |
| **POST** | `/recipe/search` | Search recipes based on user request | `name / image / ingredients / season / occasion / type / recipeType / time / difficulty / servings / instructions` | `[recipes]` |
| **PUT** | `/recipe/update-recipe/{recipeId}` | Update a recipe | `Authorization: Bearer token`, `name / image / ingredients / season / occasion / type / recipeType / time / difficulty / servings / instructions` | `{ updated recipe }` |
| **POST** | `/recipe/delete-recipe/{recipeId}` | Delete a recipe | `Authorization: Bearer token` | `{ message: 'Recipe deleted successfully' }` |
| **POST** | `/recipe/weather-suggestions` | Get recipe suggestions based on weather | `lat`, `lon` | `{ temperature, weatherDescription, placeName, season, recipes }` |
| **POST** | `/recipe/get-recipe-by-userId` | Get recipes created by a user | `Authorization: Bearer token`, `userId` | `{ recipes }` |
| **GET** | `/recipe/get-recipe-by-id/{recipeId}` | Get a recipe by ID |  | `{ recipes }` |
| **GET** | `/recipe/get-recipes` | Get all recipes |  | `{ recipes }` |

---

## 👨‍💻 Contributing
Feel free to fork the repo, create a new branch, and submit a **pull request**! 🎉
