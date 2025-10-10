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

- 🌍 Real-time weather data retrieval for any city
- 🌡️ Temperature-based clothing recommendations
- ☔ Weather condition analysis (rain, cold, etc.)
- 👕 Smart outfit suggestions based on weather conditions
- 🤖 Automated web scraping of weather information

---

## ⚙️ How It Works

- Prompts the user to input a city name
- Uses web automation to retrieve current weather data for the specified location
- Extracts temperature and precipitation details
- Applies predefined classification rules:
- Temperature < 10°C → Recommends winter clothing
- Temperature > 27°C → Recommends summer clothing
- Rain detected → Suggests raincoat or umbrella
- Generates clothing recommendations based on the analyzed weather conditions

---

## 🧪 Usage

- Run the Main.xaml workflow in UiPath Studio
- Enter your city name when prompted
- Allow the automation to fetch and process weather data
- View clothing suggestions tailored to the current conditions

---
