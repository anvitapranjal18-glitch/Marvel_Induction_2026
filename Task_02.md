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

### 5. Visual Evidence (Proof of Work)

#### A. Source Code Structure
*Below is a screenshot of the HTML and JavaScript implementation.*
![Source Code](./code.png) 
*(Note: Upload your code screenshot as 'code.png' to your GitHub repo)*

#### B. Functional User Interface
*The app successfully fetching and displaying live weather data.*
![App UI](./ui.png)
*(Note: Upload your app screenshot as 'ui.png' to your GitHub repo)*

#### C. API Network Response (Developer Tools)
*This proves the real-time data exchange between the browser and the API server.*
![Network Response](./network.png)
*(Note: Upload your network tab screenshot as 'network.png' to your GitHub repo)*

---

### 6. Challenges & Solutions
* **Challenge:** Handling invalid city names or API errors.
* **Solution:** Implemented a `try...catch` block in JavaScript to alert the user if a city is not found or if the network fails.
* **Challenge:** The temperature unit was default to Kelvin.
* **Solution:** Appended `&units=metric` to the API request to receive data in Celsius automatically.

---