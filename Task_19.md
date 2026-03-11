## **Task 19: Full-Stack Web Development — Express.js Resource Library**

### **Description**

The core objective of this task was to architect and implement a production-ready **Resource Library Web Application** using **Express.js** and **Node.js**. This project involved creating a system where users can browse a repository of technical articles and books while managing their personal accounts. The task focused on the **Model-View-Controller (MVC)** design pattern, secure user authentication using **Bcrypt**, and the implementation of a **RESTful API** to handle data persistence and dynamic UI rendering.

### **Detailed Process**

- **Server Architecture & Middleware Integration:** I initialized the project with `npm init` and structured the backend using a modular approach. I integrated several critical middleware packages to handle security and data parsing:

  - **`express.json()` & `urlencoded`:** To parse incoming request bodies from HTML forms.
  - **`express-session`:** To create a secure, server-side session for users, allowing them to stay logged in across different pages.
  - **`morgan`:** For HTTP request logging to assist in backend debugging.

- **Database Schema & CRUD Logic:** I designed the "Resource" model to store metadata for articles (Title, Author, PDF Link, Category). I then wrote the controller logic to handle the four primary CRUD actions:

  - **Create:** A secure admin route to upload new resource metadata.
  - **Read:** A public route that fetches all resources and displays them in a grid.
  - **Update/Delete:** Protected routes for modifying the library content.

- **Secure Authentication System:** I implemented a robust "Manage Your Account" feature. To protect user privacy, I never stored passwords in plain text. Instead, I used **Bcrypt** for password hashing:

  ```javascript
  // Hashing a password before saving to the database
  const hashedPassword = await bcrypt.hash(password, 10);
  ```

  I also implemented **Authorization Middleware** to protect certain routes. If a user tried to access the "Account Management" page without an active session, the server would automatically redirect them to the `/login` page.

- **Dynamic UI with Templating:** For the frontend, I used the **EJS (Embedded JavaScript)** templating engine. This allowed me to write standard HTML but inject data dynamically from the backend, such as displaying the user's name on the dashboard once they log in.

### **Technical Skills Gained**

- **🌐 RESTful API Development:** Mastering the design of endpoints (`GET`, `POST`, `PUT`, `DELETE`) that follow industry-standard naming and behavior conventions.
- **🔐 Cybersecurity Best Practices:** Implementing salting and hashing for passwords and using session cookies to prevent unauthorized access.
- **🏗️ MVC Design Pattern:** Learning to decouple the data logic (Models), the user interface (Views), and the application logic (Controllers) for cleaner, more scalable code.
- **📦 Full-Stack Integration:** Gaining the ability to connect a frontend UI to a backend server and a persistent database, creating a cohesive user experience.

---
