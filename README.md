# Books-to-scrape--web-scraping-using-python
# Books to Scrape Web Scraping Project

## Overview

This project demonstrates how to scrape book information from the [Books to Scrape](https://books.toscrape.com/) website using Python.

The goal was to collect information about all books listed on the website and organize the results into a pandas DataFrame for further analysis.

## Tools Used

* Python
* Requests
* BeautifulSoup
* Pandas
* urllib.parse

## What I Scraped

For each book, I collected:

* **Category**
* **Title**
* **Price**
* **Availability**

The final dataset contains **1,000 books and 4 columns**.

## Web Scraping Process

### 1. Request the Website

I used `requests` to download the HTML from the Books to Scrape website.

### 2. Parse the HTML

I used BeautifulSoup to parse the HTML and locate the information I needed.

### 3. Find Book Categories

I located the category links in the website's sidebar and extracted their URLs.

### 4. Scrape Each Category

For each category, I visited its webpage and found the books using:

```python
article.product_pod
```

### 5. Handle Multiple Pages

Some categories contain multiple pages of books.

I used a `while` loop to follow the website's **Next** button:

```python
while current_url:
```

The scraper continued to the next page until there was no longer a Next button.

### 6. Extract Book Information

For each book, I extracted:

```text
Title
Price
Availability
```

I also stored the category the book belonged to.

### 7. Create a DataFrame

All scraped information was stored in a list of dictionaries and converted into a pandas DataFrame.

```python
books_df = pd.DataFrame(all_books)
```

## Final Dataset

The resulting dataset contains:

| Column       | Description               |
| ------------ | ------------------------- |
| Category     | Book category             |
| Title        | Book title                |
| Price        | Book price                |
| Availability | Number of books available |

**Dataset size:** 1,000 rows × 4 columns

## Key Concepts Learned

Through this project, I practiced:

* Sending HTTP requests with `requests`
* Parsing HTML with BeautifulSoup
* Finding HTML elements using tags and classes
* Extracting text and attributes from HTML
* Working with relative URLs using `urljoin()`
* Using loops to scrape multiple categories
* Using `while` loops to handle pagination
* Storing scraped data in Python dictionaries
* Creating a pandas DataFrame from scraped data
* Debugging web scraping code

## Conclusion

This project provided practice with the basic workflow of web scraping:

**Request → Parse → Find → Extract → Store → Repeat**

The scraper successfully collected all 1,000 books from the Books to Scrape website and organized the information into a structured pandas DataFrame.
