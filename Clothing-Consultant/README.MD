# 🧥 Clothing Consultant

## 📌 Overview
The Clothing Consultant is a lightweight UiPath automation designed to classify weather conditions based on real-time temperature data. It prompts the user for a city name, fetches current weather via the OpenWeatherMap API, and returns a simple clothing recommendation: Too Hot, Too Cold, or Moderate.
This automation helps users make quick clothing decisions by evaluating temperature thresholds and displaying a clear message based on live weather data.

---

## 🎯 Objectives
The primary objectives of this automation are to:

- Capture city input from the user
- Retrieve current temperature using OpenWeatherMap API
- Extract and evaluate temperature
- Classify weather conditions into three states
- Display a clear message to guide clothing choice

---

## 🌟 Key Features

-	**City Input:** Users are prompted to enter the name of a city to check the weather.
-	**Weather Scraping:** Searches for the weather in the specified city on Google and retrieves key weather data.
-	**Temperature-Based Suggestions:** Depending on the temperature, the bot provides a recommendation for clothing or whether to carry rain gear.
-	**Logs:** Logs all actions including the city name, temperature, and weather conditions for debugging or reference.

---

## ⚙️ Technologies Used

-	UiPath Studio for automation.
-	Google Chrome for web scraping using the Google search engine.
-	UiPath Web Scraping for extracting temperature and weather data from search results.

---

## 🧪 Prerequisities

- UiPath Studio installed on your machine.
- Google Chrome browser for the web automation process.
- An active internet connection for web scraping.

---

## 🛠️ Setup Instructions

- Clone or download the project from this repository.
- Open the project in UiPath Studio.
- Ensure that you have the UiPath.WebAPI.Activities and UiPath.UIAutomation.Activities packages installed.
- Make sure your machine is connected to the internet for the web scraping functionality to work.
- Run the workflow from UiPath Studio by pressing Run.

---

## 🔂 Workflow Breakdown

❶ **Input Dialog:**
    o	The bot starts by asking the user to input the name of a city.
    o	Action: Displays a dialog titled "Get the weather" asking for the city name.
    o	Data Capture: Saves the input value in a variable CityName.

2️⃣ **Logging the City Name:**
    o	Logs the entered city name for reference.
    o	Action: Logs the city name using the Log Message activity.

3️⃣  **Opening Google Search:**
    o	The bot uses the Open Browser activity to launch Google Chrome and navigate to the Google homepage.
    o	Action: The bot types the query “Weather in <CityName>” into the search bar of Google.

4️⃣ **Performing Search:**
    o	The bot sends the Enter key to execute the search for weather in the specified city.
    o	Action: Uses the Send Hotkey activity to press the Enter key.

5️⃣ **Extracting Temperature Data:**
    o	The bot scrapes the temperature data from Google’s search result page.
    o	Action: Extracts the current temperature and stores it in the variable Temperature.

6️⃣ **Logging the Temperature:**
    o	Logs the temperature for reference and debugging.
    o	Action: Logs the value of Temperature.

7️⃣ **Extracting Weather Data:**
    o	The bot scrapes additional weather details (like weather condition, day of the week, etc.).
    o	Action: Extracts weather details and stores them in the variable Weather.

8️⃣ **Logging Weather Data:**
    o	Logs the full weather details for reference and debugging.
    o	Action: Logs the value of Weather.

9️⃣ **Weather Analysis:**
    o	Based on the retrieved weather and temperature, the bot checks:
      •	Rain Check: If it’s raining, it assigns rain gear.
      •	Cold Weather Check: If the temperature is low, it suggests warm clothing.
      •	Hot Weather Check: If the temperature is high, it suggests lighter clothing.
    o	Actions: Uses If-Else conditions to check these parameters and assigns relevant suggestions.

🔟 **Displaying Clothing Suggestion:**
    o	The bot displays a clothing suggestion based on the weather analysis.
    o	Action: The bot shows a message to the user with the clothing suggestion or rain gear advice.

---

## 📝 Sample Log Output
- City: New York
- Temperature: 16°C
- Weather: Clear
- Suggested Outfit: "The Temperature is 16 Degree Celsius. The weather is Clear. Bring a Light Jacket if you want"

---
