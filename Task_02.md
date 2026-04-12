# Task 2: API Integration & Application Development

---

### 1. Objective
To understand how Application Programming Interfaces (APIs) allow different software systems to communicate and to build a functional web interface that fetches real-time data.

### 2. What is an API?
An **API (Application Programming Interface)** acts as a digital bridge between two applications. 
* **The Request:** My web app sends a URL containing a city name and a security key to the OpenWeatherMap server.
* **The Response:** The server processes the request and sends back structured data (JSON) containing temperature, humidity, and weather conditions.

### 3. The Tech Stack
* **Frontend:** HTML5 and CSS3 for the user interface.
* **Scripting:** JavaScript (using the `fetch()` API for asynchronous data retrieval).
* **API Provider:** OpenWeatherMap API.
* **Data Format:** JSON (JavaScript Object Notation).

---

### 4. Implementation Steps
1.  **API Key Generation:** Registered on OpenWeatherMap to obtain a unique API key for authentication.
2.  **Logic Development:** Created an `async` function in JavaScript to handle the API call.
3.  **Endpoint Configuration:** Constructed a dynamic URL: 
    `https://api.openweathermap.org/data/2.5/weather?q={CITY}&appid={API_KEY}&units=metric`
4.  **Data Parsing:** Extracted specific values like `data.main.temp` and `data.weather[0].description` to display on the UI.

---



#### A. Source Code Structure
*Below is the HTML and JavaScript implementation across multiple segments.*
![Code Part 1](https://raw.githubusercontent.com/anvitapranjal18-glitch/Marvel_Induction_2026/main/code1.png)
![Code Part 2](https://raw.githubusercontent.com/anvitapranjal18-glitch/Marvel_Induction_2026/main/code2.png)

#### B. Functional User Interface
*The app successfully fetching and displaying live weather data.*
![App UI](https://raw.githubusercontent.com/anvitapranjal18-glitch/Marvel_Induction_2026/main/weather_app.png)


---

