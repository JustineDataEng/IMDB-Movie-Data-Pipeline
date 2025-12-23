#  IMDb Data Pipeline: Advanced Web Scraping & Extraction

## Project Overview
This project is a high-performance data extraction pipeline designed to harvest granular movie data from IMDb. It addresses the challenge of dynamic web content, specifically the "Load More" pagination that standard scrapers cannot handle. 

By automating browser interactions, this script builds a structured dataset (CSV) that includes deep financial metrics and production metadata, bridging the gap between raw web data and actionable insights.

## Technical Toolkit
* **Core Automation:** `Selenium` (Webdriver) simulates a real user to navigate the browser and click interactive elements.
* **Driver Management:** `webdriver_manager` handles the installation of the Chrome driver service automatically.
* **Data Parsing:** `BeautifulSoup` extracts specific text elements from raw HTML code for high precision.
* **Data Engineering:** `Pandas` structures the final dataset and handles the CSV exportation.
* **Advanced Logic:** `ActionChains` performs the automated clicking required to expand the dynamic movie list.

## Key Features & Engineering Logic
* **Dynamic List Expansion:** The script uses an automated loop to trigger the "See More" button, expanding the list to the desired dataset size before scraping.
* **Two-Phase Extraction:** 1. **List Scrape:** Captures basic info (Title, Year, Rating) from the expanded main list.
    2. **Deep-Dive Scrape:** Navigates into each individual movie URL to pull "hidden" data like Budget and Gross Worldwide revenue.
* **Robust Error Handling:** Every data point is wrapped in logic to assign `None` if data is missing, ensuring the pipeline never crashes on incomplete web pages.

##  Final Dataset Structure
The pipeline produces a structured CSV (`my_scraped_movies.csv`) containing:
* **Identification:** Movie Title, Release Year, and unique IMDb_ID.
* **Performance:** User Rating, Duration, and Plot Summary.
* **Financials:** Budget, Opening Weekend, and Cumulative Worldwide Gross.
* **Production:** Directors, Production Companies, Country of Origin, and Languages.

---
**Maintaining Precision:** This project demonstrates proficiency in automated workflow management and the ability to process messy, real-world web data into a production-ready format.
