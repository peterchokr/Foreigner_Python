# Chapter 24: Web Scraping — Practice Problems

---

## 📝 Multiple Choice Questions

---

### 🟢 Beginner

**Problem 1.** What is web scraping?

① Technique for building websites  
② **Technique for automatically collecting data from websites**  
③ Technique for designing websites  
④ Technique for managing web servers  

---

**Problem 2.** What library is used to download web pages?

① `beautifulsoup4`  
② `requests`  
③ `selenium`  
④ `scrapy`  

---

**Problem 3.** What library is used to parse (analyze) HTML?

① `requests`  
② `csv`  
③ `BeautifulSoup`  
④ `json`  

---

**Problem 4.** Which of the following is NOT an HTML tag?

① `<h1>`  
② `<p>`  
③ `<div>`  
④ `<print>`  

---

**Problem 5.** What is the correct code to create a BeautifulSoup object?

① `BeautifulSoup(html)`  
② `BeautifulSoup(html, 'html.parser')`  
③ `BeautifulSoup.parse(html)`  
④ `BeautifulSoup.read(html)`  

---

**Problem 6.** What HTML attribute applies the same style to multiple elements?

① `id`  
② `name`  
③ `class`  
④ `style`  

---

**Problem 7.** What does HTTP status code 200 mean?

① Page not found  
② Server error  
③ Access denied  
④ **Success**  

---

### 🟡 Intermediate

**Problem 8.** What code finds only the first `<h2>` tag?

① `soup.find_all('h2')`  
② `soup.find('h2')`  
③ `soup.get('h2')`  
④ `soup.select('h2')`  

---

**Problem 9.** What code finds all `<div>` tags with a specific class?

① `soup.find_all('div', class='product')`  
② `soup.find_all('div', class_='product')`  
③ `soup.find_all('div', className='product')`  
④ `soup.find_all('div', cls='product')`  

---

**Problem 10.** How to extract the URL from `<a href="https://example.com">Link</a>`?

① `link.text`  
② `link.get('href')`  
③ `link.url`  
④ `link.get('src')`  

---

**Problem 11.** How to extract the text ("Link") from an `<a>` tag?

① `link.get('text')`  
② `link.value`  
③ `link.text`  
④ `link.content`  

---

**Problem 12.** How to add delay between requests to reduce server load?

① `wait(2)`  
② `time.sleep(2)`  
③ `pause(2)`  
④ `delay(2)`  

---

### 🔴 Advanced

**Problem 13.** Why is `class_='author'` used in this code?

```python
soup.find(class_='author')
```

① `class` is not an HTML attribute  
② **`class` is a Python reserved keyword**  
③ It's BeautifulSoup's syntax rule  
④ To distinguish case sensitivity  

---

**Problem 14.** How to extract only numbers from price string "35,000"?

```python
import re
price_text = "35,000"
```

① `int(price_text)`  
② `price_text.strip('0')`  
③ `int(re.sub(r'[^0-9]', '', price_text))`  
④ `float(price_text)`  

---

**Problem 15.** Why set User-Agent when web scraping?

① To hide IP address  
② **To avoid being blocked as a bot**  
③ To increase download speed  
④ To improve code readability  

---

## 📝 Short Answer Questions

---

### 🟢 Beginner

**Problem 16.** Explain what web scraping is and give real-world examples.

---

**Problem 17.** What is the difference between requests and BeautifulSoup?

---

**Problem 18.** Explain HTML structure and common tags.

---

### 🟡 Intermediate

**Problem 19.** Explain the difference between `find()` and `find_all()` with examples.

```python
# find() - returns first match
first = soup.find('h2')

# find_all() - returns all matches
all_items = soup.find_all('h2')
```

---

**Problem 20.** How to handle errors and missing elements when scraping?

---

### 🔴 Advanced

**Problem 21.** Write code for complete web scraping application with data processing.

```python
import requests
from bs4 import BeautifulSoup
import csv
import time

# Fetch page
response = requests.get('https://example.com')

# Parse HTML
soup = BeautifulSoup(response.content, 'html.parser')

# Extract data
products = []
for item in soup.find_all('div', class_='product'):
    name = item.find('h2').text
    price = item.find('span', class_='price').text
    products.append({'name': name, 'price': price})

# Save to CSV
with open('products.csv', 'w', newline='') as f:
    writer = csv.DictWriter(f, fieldnames=['name', 'price'])
    writer.writeheader()
    writer.writerows(products)
```

---

## 💻 Hands-On Problems

---

### 🟢 Beginner

**Problem 22.** Fetch a webpage and display its title.

> Use requests to download HTML, parse with BeautifulSoup, extract title.

Output example:

```
=== Webpage Title ===
URL: https://example.com
Status Code: 200
Page Title: Example Domain
```

---

**Problem 23.** Extract all links from a webpage.

> Find all `<a>` tags and display their URLs and text.

Output example:

```
=== Links Found ===
1. Home (https://example.com/)
2. About (https://example.com/about)
3. Contact (https://example.com/contact)
Total: 3 links
```

---

### 🟡 Intermediate

**Problem 24.** Scrape product data from a page and save to CSV.

> Extract products with names and prices, save to CSV file.

Output example:

```
=== Product Scraping ===
Products Found: 5
- Product A: $29.99
- Product B: $39.99
- Product C: $49.99

Saved to: products.csv
```

---

**Problem 25.** Extract data with filtering and processing.

> Scrape prices, clean data, calculate statistics.

Output example:

```
=== Price Analysis ===
Original: 35,000원  → Cleaned: 35000
Original: 42,500원  → Cleaned: 42500
Average: 38750
Highest: 42500
Lowest: 35000
```

---

### 🔴 Advanced

**Problem 26.** Create complete web scraping pipeline with error handling.

> Multi-page scraping, data validation, CSV export, error handling.

Output example:

```
=== Web Scraping Pipeline ===
Page 1: 10 items scraped
Page 2: 10 items scraped
Page 3: 10 items scraped

Total: 30 items
Processing:
- Removed duplicates: 2
- Invalid entries: 1
- Valid entries: 27

Exported to: data.csv
Processing Time: 15.3 seconds
```

---
---

# 🔑 Answer Key and Explanations

---

## 📝 Multiple Choice Answers

---

### 🟢 Beginner

**Problem 1. Answer: ② Automatically collecting data from websites**

Core definition of web scraping.

---

**Problem 2. Answer: ② `requests`**

requests library downloads HTML content.

---

**Problem 3. Answer: ③ `BeautifulSoup`**

BeautifulSoup parses HTML structure.

---

**Problem 4. Answer: ④ `<print>`**

`print` is not a valid HTML tag.

---

**Problem 5. Answer: ② `BeautifulSoup(html, 'html.parser')`**

Correct syntax with parser specification.

---

**Problem 6. Answer: ③ `class`**

class attribute applies styles to multiple elements.

---

**Problem 7. Answer: ④ Success**

HTTP 200 = successful response.

---

### 🟡 Intermediate

**Problem 8. Answer: ② `soup.find('h2')`**

find() returns single first match.

---

**Problem 9. Answer: ② `soup.find_all('div', class_='product')`**

Use class_ (underscore) to avoid Python keyword conflict.

---

**Problem 10. Answer: ② `link.get('href')`**

get() method retrieves attribute values.

---

**Problem 11. Answer: ③ `link.text`**

.text property gets element text content.

---

**Problem 12. Answer: ② `time.sleep(2)`**

time.sleep() pauses execution.

---

### 🔴 Advanced

**Problem 13. Answer: ② `class` is a Python reserved keyword**

class_ used to avoid syntax conflict.

---

**Problem 14. Answer: ③ `int(re.sub(r'[^0-9]', '', price_text))`**

Regex removes non-numeric characters.

---

**Problem 15. Answer: ② To avoid being blocked as a bot**

User-Agent makes requests appear human.

---

## 📝 Short Answer Key

---

### 🟢 Beginner

**Problem 16. Model Answer:**

Web scraping = automatically collecting data from websites.

Examples: product prices, job listings, news articles.

---

**Problem 17. Model Answer:**

requests = downloads HTML  
BeautifulSoup = parses HTML structure

---

**Problem 18. Model Answer:**

HTML = markup language with tags.

Common: `<h1>` title, `<p>` paragraph, `<a>` link, `<div>` container.

---

### 🟡 Intermediate

**Problem 19. Model Answer:**

find() = first match only  
find_all() = all matching elements as list

---

**Problem 20. Model Answer:**

Use try-except, check element existence before accessing.

---

### 🔴 Advanced

**Problem 21. Model Answer:**

Complete scraping: fetch → parse → extract → process → save.

---

## 💻 Hands-On Solutions

---

### 🟢 Beginner

**Problem 22. Model Answer:**

```python
import requests
from bs4 import BeautifulSoup

url = 'https://example.com'
response = requests.get(url)

print(f"=== Webpage Title ===")
print(f"URL: {url}")
print(f"Status Code: {response.status_code}")

soup = BeautifulSoup(response.content, 'html.parser')
title = soup.find('title')
print(f"Page Title: {title.text if title else 'Not found'}")
```

---

**Problem 23. Model Answer:**

```python
import requests
from bs4 import BeautifulSoup

url = 'https://example.com'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')

links = soup.find_all('a')

print("=== Links Found ===")
for i, link in enumerate(links, 1):
    href = link.get('href')
    text = link.text
    print(f"{i}. {text} ({href})")
print(f"Total: {len(links)} links")
```

---

### 🟡 Intermediate

**Problem 24. Model Answer:**

```python
import requests
from bs4 import BeautifulSoup
import csv

url = 'https://example.com'
response = requests.get(url)
soup = BeautifulSoup(response.content, 'html.parser')

products = []
for item in soup.find_all('div', class_='product'):
    name = item.find('h2').text
    price = item.find('span', class_='price').text
    products.append({'name': name, 'price': price})

with open('products.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.DictWriter(f, fieldnames=['name', 'price'])
    writer.writeheader()
    writer.writerows(products)

print(f"=== Product Scraping ===")
print(f"Products Found: {len(products)}")
for p in products:
    print(f"- {p['name']}: {p['price']}")
print(f"Saved to: products.csv")
```

---

**Problem 25. Model Answer:**

```python
import re

prices_raw = ["35,000", "42,500", "38,000", "45,000", "37,000"]

print("=== Price Analysis ===")
prices_clean = []
for price in prices_raw:
    clean = int(re.sub(r'[^0-9]', '', price))
    prices_clean.append(clean)
    print(f"Original: {price} → Cleaned: {clean}")

average = sum(prices_clean) / len(prices_clean)
print(f"Average: {average:.0f}")
print(f"Highest: {max(prices_clean)}")
print(f"Lowest: {min(prices_clean)}")
```

---

### 🔴 Advanced

**Problem 26. Model Answer:**

```python
import requests
from bs4 import BeautifulSoup
import csv
import time

def scrape_products(base_url, num_pages=3):
    all_products = []
    
    for page in range(1, num_pages + 1):
        url = f"{base_url}?page={page}"
        response = requests.get(url)
        soup = BeautifulSoup(response.content, 'html.parser')
        
        products = []
        for item in soup.find_all('div', class_='product'):
            try:
                name = item.find('h2').text
                price = item.find('span', class_='price').text
                products.append({'name': name, 'price': price})
            except:
                continue
        
        all_products.extend(products)
        print(f"Page {page}: {len(products)} items scraped")
        time.sleep(1)  # Delay between requests
    
    return all_products

# Scrape
url = 'https://example.com'
products = scrape_products(url, 3)

# Validation
duplicates = len(products) - len(set(str(p) for p in products))
invalid = 0

# Save
with open('data.csv', 'w', newline='', encoding='utf-8') as f:
    writer = csv.DictWriter(f, fieldnames=['name', 'price'])
    writer.writeheader()
    writer.writerows(products)

print(f"\n=== Results ===")
print(f"Total: {len(products)} items")
print(f"Removed duplicates: {duplicates}")
print(f"Invalid entries: {invalid}")
print(f"Valid entries: {len(products) - duplicates - invalid}")
print(f"Exported to: data.csv")
```

---

Professor Cho Jeonghyun (peterchokr@gmail.com)  
Yeungnam University College.
