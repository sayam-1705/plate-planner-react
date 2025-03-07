# 🎨 Plate Planner - Frontend Documentation

## 📌 Overview

The frontend of **Plate Planner** is built using **React.js** and **Vite**, providing a fast and optimized user experience. It offers an intuitive interface for meal planning, personalized recipe suggestions, and nutritional insights.

### 🚀 About Vite

Vite is a modern frontend build tool designed for speed and efficiency. It features instant server startup, on-demand compilation, and hot module replacement, making development seamless and performant.

---

## 🌐 Frontend Endpoints

| Path                 | Component                  | Description                                         |
| -------------------- | -------------------------- | --------------------------------------------------- |
| `/signup`            | `Signup`                   | User signup page                                    |
| `/signin`            | `Signin`                   | User login page                                     |
| `/`                  | `Home`                     | Landing page                                        |
| `/dashboard`         | `Dashboard` (Protected)    | User dashboard (requires authentication)            |
| `/update-recipe/:id` | `UpdateRecipe` (Protected) | Update an existing recipe (requires authentication) |
| `/create-recipe`     | `CreateRecipe` (Protected) | Create a new recipe (requires authentication)       |
| `/search-recipe`     | `SearchElements`           | Search for recipes                                  |

---

## 🛠️ Dependencies

- **axios**: Handles HTTP requests to communicate with the backend.
- **chart.js**: Renders graphical nutritional insights.
- **multer**: Handles file uploads, such as recipe images.
- **react**: Core library for building the user interface.
- **react-dom**: Enables React to interact with the DOM.
- **react-modal**: Provides a flexible modal component.
- **react-router-dom**: Enables client-side routing and navigation.

---

## 👨‍💻 Contributing

We welcome contributions! Fork the repo, create a new branch, and submit a pull request.

Happy Coding! 🚀
