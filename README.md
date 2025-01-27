# Amazon Product Scraper

This is a Python script that scrapes product details from an Amazon product page. The script extracts key details such as the product title, price, rating, number of reviews, and availability status, and saves the data into a CSV file.

## Features

- Extracts the following product details from an Amazon product page:
  - Product title
  - Price
  - Rating
  - Number of reviews
  - Availability status
- Appends the extracted data into an `out.csv` file.
- Provides an easy-to-use function for scraping any Amazon product page by providing the URL.

## Prerequisites

- Python 3.x
- Install the required Python libraries:
  - `requests` for making HTTP requests to Amazon pages.
  - `BeautifulSoup` (from the `bs4` library) for parsing HTML content.
  - `lxml` for fast and efficient HTML parsing.

To install the required libraries, you can run the following command:

```bash
pip install requests beautifulsoup4 lxml
```

## How to Use

1. **Clone this repository** to your local machine:
   ```bash
   git clone https://github.com/NiyatiP10/Scraping-Amazon-Product-Information-using-Beautiful-Soup.git
   cd Scraping-Amazon-Product-Information-using-Beautiful-Soup
   ```

2. **Run the script** by providing the URL of the Amazon product you want to scrape:

   ```bash
   python Scraping-Amazon-Product-Information-using-Beautiful-Soup.py
   ```

   For example, you can use:
   ```bash
   python Scraping-Amazon-Product-Information-using-Beautiful-Soup.py https://www.amazon.com/dp/B08CFSZLQ4
   ```

   This will append the product details into an `out.csv` file located in the same directory as the script.

## Script Breakdown

- **`main(URL)`**: 
  The main function that takes an Amazon product URL as an argument, sends a GET request to the webpage, and scrapes the product details.
  
  The function handles the following:
  - Scrapes the **product title** using the ID `productTitle`.
  - Scrapes the **price** using the ID `priceblock_ourprice`.
  - Scrapes the **rating** and **review count** using their respective classes.
  - Scrapes the **availability status** using the `availability` ID.

  All the scraped data is written into `out.csv`.

- **`out.csv`**: 
  This file will contain the extracted data, with each product's details written as a new line. The columns are:
  - Product Title
  - Price
  - Rating
  - Number of Reviews
  - Availability

## Example Output (`out.csv`)

```csv
Product Title, Price, Rating, Number of Reviews, Availability
"Some Product Title", "$19.99", "4.5 out of 5 stars", "2000 ratings", "In Stock"
```

## Notes

- The script currently supports scraping for individual Amazon product pages.
- If any element (such as price, title, or rating) is not found on the product page, "NA" will be used as a placeholder in the CSV file.

## Contributing

Feel free to open an issue or submit a pull request if you'd like to contribute to this project.
