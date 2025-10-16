# 🏠 Real Estate Web Scrapping

## 📌 Overview
The Real Estate Web Scraper is a UiPath automation solution designed to scrape real estate property listings from a zillow.com. The bot extracts important property details like price, location, type, and description from each listing. The collected data is then exported into an Excel file for further analysis or reporting. The automation also handles pagination, allowing it to scrape data from multiple pages of listings.

---

## 🎯 Objectives
The primary objectives of this automation are to:

- Capture the website URL from the user
- Scrape essential details of real estate listings (price, location, property type, etc.)
- Handle pagination to scrape multiple pages of listings
- Export the scraped data to an Excel file for easy analysis

---

## 🌟 Key Features

-	**City Input:** Users can enter the city name to check the properties listed.
-	**Property Listing Extraction:** Scrapes details like price, location, description, and more from each real estate listing.
-	**Pagination Handling:** Navigates through multiple pages of listings and extracts data from all pages.
-	**Data Export:** The scraped data is exported into an Excel file for easy review and analysis.
-	**Error Logging:** Logs each action, including website URL, extracted data, and any errors encountered during the scraping process.

---

## ⚙️ Technologies Used

-	UiPath Studio for automating the scraping process.
-	Google Chrome for web scraping using the Google search engine.
-	UiPath Web Scraping for extracting temperature and weather data from search results.
-	Excel for storing the scraped data.

---

## 🧪 Prerequisities

- UiPath Studio installed on your machine.
- Google Chrome browser for the web scraping process.
- Microsoft Excel for storing the scraped data.
- An active internet connection for web scraping.

---

## 🔎 Workflow Breakdown

1️⃣ **Input URL:**
- The bot starts by asking the user to input the city of the real estate website they wish to scrape.
- Action: Displays an input dialog to capture the website URL.
- Data Capture: Saves the URL in the WebsiteURL variable.

2️⃣ **Opening the Website:**
- The bot uses the Open Browser activity to open the specified website in a browser window.
- Action: Launches the website in Chrome (or another browser) to begin scraping the listings.

3️⃣ **Extracting Property Listings:**
- The bot scrapes the details of each property listing on the page using the Extract Structured Data activity.
- Action: Extracts key property details such as price, location, description, property type, and agent name (if available).

4️⃣ **Handling Pagination:**
- The bot checks for a "Next Page" button and clicks it to navigate to the next page of listings.
- Action: Uses a loop to navigate through all available pages, scraping data from each.

5️⃣ **Storing Data in Excel:**
- The scraped property data is stored in an Excel file using the Write Range activity.
- Action: Writes the scraped details to a structured Excel sheet, with each listing stored in its own row.

6️⃣ **Error Logging:**
- The bot includes error handling for any issues encountered during scraping.
- Action: Logs errors for debugging and ensures the process continues smoothly even if some listings or pages fail to load.

7️⃣ **Closing the Browser:**
- After all pages are processed, the bot closes the browser using the Close Application activity.
- Action: Closes the browser to complete the automation process.

---

## 🎨 Workflow Diagram

