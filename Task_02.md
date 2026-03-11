## Task 2: API Integration & Application Development {#task-2}

### 1. Objective

To understand how Application Programming Interfaces (APIs) allow different software systems to communicate and to build a functional web interface that fetches real-time data.

### 2. What is an API?

An **API (Application Programming Interface)** is a set of rules that allows one bridge to talk to another.

- **Request:** My app asks the OpenWeather server: "What is the temperature in London?"
- **Response:** The server sends back a JSON file with the numbers.

### 3. The Tech Stack

- **Language:** HTML/JavaScript (or Python/Flask).
- **API Provider:** OpenWeatherMap API.
- **Data Format:** JSON (JavaScript Object Notation).

### 4. Implementation Steps

1.  **API Key Generation:** Registered on OpenWeatherMap to get a unique security key.
2.  **The Fetch Call:** Used the `fetch()` function in JavaScript to send a URL request:
    `https://api.openweathermap.org/data/2.5/weather?q={CITY}&appid={API_KEY}`
3.  **Data Parsing:** Extracted specific values like `main.temp` and `weather[0].description` from the big block of data returned.
4.  **UI Rendering:** Used DOM manipulation to display the temperature and weather icons on the screen.

---

### 5. Visual Evidence (Photos)

> **[INSERT PHOTO 3: Screenshot of your Code (The Fetch function)]**

> **[INSERT PHOTO 4: Screenshot of your finished Weather App UI]**

### 6. Challenges & Solutions

- **Challenge:** The temperature was originally in Kelvin (e.g., 298.15K).
- **Solution:** Added `&units=metric` to the API URL to get Celsius automatically.

---
