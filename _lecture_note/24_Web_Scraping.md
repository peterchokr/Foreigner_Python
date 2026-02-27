# Chapter 24. Web Scraping

---

## 📚 Learning Objectives

After completing this chapter, you will understand web scraping technology and be able to automatically collect data from websites. You will be able to extract and analyze various types of web data such as news articles, product information, and weather information using Python.

이번 장을 마치면 여러분은 웹 스크래핑 기술을 활용하여 웹사이트에서 데이터를 자동으로 수집할 수 있습니다. 뉴스 기사, 상품 정보, 날씨 등 다양한 웹 데이터를 파이썬으로 추출하고 분석할 수 있게 됩니다.

---

## 1️⃣ What is Web Scraping? (웹 스크래핑이란?)

Web scraping is a technique to automatically collect data from websites. Instead of manually copying and pasting information one by one, you can write a Python program to extract data much more efficiently and accurately.

웹 스크래핑(Web Scraping)은 웹사이트에서 데이터를 자동으로 수집하는 기술입니다. 수작업으로 정보를 복사하고 붙여넣는 대신, 프로그램을 이용해 훨씬 더 효율적이고 정확하게 데이터를 추출할 수 있습니다.

### Why Do We Need Web Scraping? (웹 스크래핑이 왜 필요할까?)

Consider the difference between manual data collection and web scraping. When you collect data manually, you must visit each website, find the information, copy it, and paste it into a spreadsheet one item at a time. This is time-consuming and error-prone. Web scraping automates this entire process, allowing you to collect hundreds or thousands of items in seconds with perfect accuracy.

수작업으로 데이터를 수집하려면 각 웹사이트를 방문하고, 정보를 찾아 복사해서 스프레드시트에 붙여넣는 작업을 반복해야 합니다. 이것은 매우 시간이 오래 걸리고 실수하기 쉽습니다. 웹 스크래핑을 사용하면 이 전체 과정을 자동화하여 몇 초 안에 수백 개 또는 수천 개의 항목을 완벽한 정확도로 수집할 수 있습니다.

```
Manual Data Collection          Web Scraping
━━━━━━━━━━━━━━━━━━━━━━━━━     ━━━━━━━━━━━━━━━━━━━━━━━━━
1. Visit website               1. Run Python script
2. Copy product info           2. Enjoy your coffee ☕
3. Paste into Excel            3. Data collected!
4. Go to next page
5. Repeat... (100 products)    Time: A few seconds
                               Accuracy: 100% ✅
Time: Several hours 😫
Accuracy: Error-prone ❌
```

### Real-World Applications (실생활 활용 예시)

Web scraping has many practical applications across different industries. Let's look at some common use cases where web scraping makes a real difference.

웹 스크래핑은 다양한 산업에서 많은 실용적인 응용 분야가 있습니다. 웹 스크래핑이 실제로 큰 역할을 하는 몇 가지 일반적인 사용 사례를 살펴봅시다.

```
🛒 Shopping & E-commerce
- Compare product prices across multiple stores
- Monitor inventory availability
- Analyze customer reviews and ratings

📰 News & Information
- Collect news headlines and stories
- Track weather forecasts
- Monitor exchange rates

📊 Data Analysis & Research
- Real estate price tracking
- Stock market information
- Social media trends analysis
```

쇼핑과 전자상거래 분야에서는 여러 상점의 상품 가격을 비교하고, 재고 가용성을 모니터링하고, 고객 리뷰를 분석할 수 있습니다.

뉴스와 정보 분야에서는 뉴스 헤드라인과 기사를 수집하고, 날씨를 추적하고, 환율을 모니터링할 수 있습니다.

데이터 분석 및 연구 분야에서는 부동산 가격을 추적하고, 주식 정보를 모니터링하고, 소셜 미디어 트렌드를 분석할 수 있습니다.

### Web Scraping vs Web Crawling (웹 스크래핑 vs 웹 크롤링)

It's important to understand the difference between web scraping and web crawling, as these terms are sometimes used interchangeably.

Web scraping focuses on extracting specific data from one or more web pages. You identify the elements you need (like product prices or headlines) and extract just that information.

Web crawling, on the other hand, is a broader process where a program systematically explores and indexes entire websites, following links from page to page, much like search engines do.

웹 스크래핑과 웹 크롤링의 차이를 이해하는 것이 중요합니다. 이 두 용어가 때때로 혼용되기도 합니다.

웹 스크래핑은 하나 또는 여러 웹페이지에서 특정 데이터(가격, 제목 등)를 추출하는 것에 초점을 맞춥니다.

반면 웹 크롤링은 검색 엔진처럼 웹사이트 전체를 체계적으로 탐색하고 링크를 따라가며 인덱싱하는 광범위한 프로세스입니다.

---

## 2️⃣ Installing Required Libraries (라이브러리 설치)

To perform web scraping in Python, we need to install two essential third-party libraries. These libraries handle the technical aspects of downloading web pages and parsing their content. Open your terminal or command prompt and execute the installation commands below.

파이썬에서 웹 스크래핑을 하려면 두 가지 필수 라이브러리를 설치해야 합니다. 이 라이브러리들은 웹페이지 다운로드와 콘텐츠 파싱의 기술적 측면을 처리합니다. 터미널이나 명령 프롬프트를 열고 다음 설치 명령어를 실행하세요.

```bash
pip install requests
pip install beautifulsoup4
```

### Library Functions (라이브러리 역할)

Once installed, you can import these libraries into your Python scripts:

설치 후에는 파이썬 스크립트에서 이 라이브러리들을 임포트할 수 있습니다:

```python
import requests              # Download web pages (웹페이지 다운로드)
from bs4 import BeautifulSoup  # Analyze HTML (HTML 분석하기)
```

**requests library**: This library is responsible for downloading web pages from the internet. It handles the communication with web servers and returns the HTML content. You provide a URL, and requests retrieves the page content for you. It also manages response status codes, headers, and other HTTP-related information.

**BeautifulSoup library**: This library parses and analyzes HTML content. Once you have the HTML of a web page, BeautifulSoup helps you navigate through the structure and extract specific elements. It provides convenient methods to find tags, extract text, and access attributes.

**requests 라이브러리**: 이 라이브러리는 인터넷에서 웹페이지를 다운로드하는 역할을 합니다. 웹 서버와의 통신을 처리하고 HTML 콘텐츠를 반환합니다. URL을 제공하면 requests가 페이지 콘텐츠를 검색합니다. 또한 응답 상태 코드, 헤더 및 기타 HTTP 관련 정보를 관리합니다.

**BeautifulSoup 라이브러리**: 이 라이브러리는 HTML 콘텐츠를 파싱하고 분석합니다. 웹페이지의 HTML을 얻으면 BeautifulSoup은 구조를 탐색하고 특정 요소를 추출하는 데 도움을 줍니다. 태그를 찾고, 텍스트를 추출하고, 속성에 접근하는 편리한 메서드들을 제공합니다.

---

## 3️⃣ Understanding HTML Basics (HTML 기초 이해)

Web pages are created using HTML (Hypertext Markup Language), a markup language that structures content using tags and elements. To scrape data effectively, you need to understand how HTML is organized. Once you understand the structure, you'll know how to identify and extract the specific information you need.

웹페이지는 HTML(Hypertext Markup Language)로 만들어져 있으며, 이는 태그와 요소를 사용하여 콘텐츠를 구조화하는 마크업 언어입니다. 웹 스크래핑을 효과적으로 하려면 HTML이 어떻게 조직되어 있는지 이해해야 합니다. 구조를 이해하면 필요한 특정 정보를 식별하고 추출하는 방법을 알게 됩니다.

### Basic HTML Structure (HTML의 기본 구조)

A typical HTML document has a standard structure. The `<html>` tag is the root element that contains everything. Inside it are `<head>` and `<body>` sections. The head contains metadata like the page title, while the body contains the visible content that users see.

일반적인 HTML 문서는 표준 구조를 가집니다. `<html>` 태그는 모든 것을 포함하는 루트 요소입니다. 그 안에는 `<head>`와 `<body>` 섹션이 있습니다. head는 페이지 제목과 같은 메타데이터를 포함하고, body는 사용자가 볼 수 있는 시각적 콘텐츠를 포함합니다.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Page Title</title>
</head>
<body>
    <h1>Large Heading</h1>
    <p>Paragraph content</p>
    <a href="https://example.com">Link</a>
    <img src="image.jpg">
</body>
</html>
```

### HTML Tag Structure (주요 HTML 태그)

HTML uses tags to mark up content. Each tag consists of an opening tag, content, and a closing tag. The opening tag starts with `<`, the tag name, and ends with `>`. The closing tag is similar but includes a forward slash before the tag name.

HTML은 태그를 사용하여 콘텐츠를 표시합니다. 각 태그는 시작 태그, 콘텐츠, 종료 태그로 구성됩니다. 시작 태그는 `<`, 태그 이름, `>`으로 끝납니다. 종료 태그는 비슷하지만 태그 이름 앞에 슬래시가 포함됩니다.

```
Tag Structure
<tag_name>content</tag_name>
   ↑        ↑         ↑
opening  content   closing
  tag              tag

Examples:
<h1>This is a heading</h1>
<p>This is a paragraph</p>
<a href="url">Link text</a>
```

태그 구조는 다음과 같습니다:

```
<태그이름>내용</태그이름>
   ↑      ↑       ↑
시작태그 내용  종료태그

예시:
<h1>제목입니다</h1>
<p>문단입니다</p>
<a href="url">링크</a>
```

### Commonly Used Tags (자주 사용하는 태그)

When scraping websites, you'll encounter many different HTML tags. Here are the most common ones you need to know:

웹사이트를 스크래핑할 때 다양한 HTML 태그를 접하게 됩니다. 다음은 알아야 할 가장 일반적인 것들입니다:

- `<h1>` ~ `<h6>`: Headings of different levels (다양한 수준의 제목)
- `<p>`: Paragraph text (문단)
- `<a>`: Links, accessed via href attribute (링크, href 속성을 통해 접근)
- `<img>`: Images, accessed via src attribute (이미지, src 속성을 통해 접근)
- `<div>`: Container division for grouping elements (요소를 그룹화하기 위한 컨테이너)
- `<span>`: Inline element for styling text (텍스트 스타일링을 위한 인라인 요소)
- `<ul>`, `<li>`: Unordered lists and list items (비정렬 목록과 목록 항목)

### Classes and IDs (클래스와 ID)

HTML elements can be identified and styled using class and id attributes. These attributes are crucial for web scraping because they help you target specific elements precisely. A class attribute can be shared by multiple elements, making it useful for grouping similar items. An id attribute should be unique within a page, making it useful for identifying single, specific elements.

HTML 요소들은 class와 id 속성을 사용하여 식별하고 스타일을 지정할 수 있습니다. 이 속성들은 웹 스크래핑에서 특정 요소를 정확하게 대상으로 삼는 데 도움이 되므로 매우 중요합니다. class 속성은 여러 요소가 공유할 수 있어서 유사한 항목을 그룹화하는 데 유용합니다. id 속성은 페이지 내에서 고유해야 하므로 단일의 특정 요소를 식별하는 데 유용합니다.

```html
<div class="product">Product Item</div>
<div id="main">Main Content</div>
```

---

## 4️⃣ Your First Web Scraping Project (첫 번째 웹 스크래핑)

Now that you understand the basics of HTML, let's start with a hands-on project using a simple HTML file. This approach is better than working with real websites at first because you can control the HTML structure and focus on learning the scraping techniques without worrying about network issues or changing website structures.

이제 HTML의 기본을 이해했으니, 간단한 HTML 파일을 사용하여 실습 프로젝트를 시작합시다. 이 방식은 실제 웹사이트로 작업하는 것보다 좋습니다. HTML 구조를 제어할 수 있고 네트워크 문제나 변경되는 웹사이트 구조를 걱정하지 않으면서 스크래핑 기술에 집중할 수 있기 때문입니다.

### Creating a Sample HTML File (실습용 HTML 파일 만들기)

Open your text editor and create a file. Copy the following HTML code and save it as `sample.html`. This will be our practice dataset.

텍스트 편집기를 열고 파일을 만드세요. 다음 HTML 코드를 복사하여 `sample.html`로 저장하세요. 이것이 우리의 연습 데이터셋이 될 것입니다.

**sample.html:**

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Web Scraping Practice</title>
</head>
<body>
    <h1>Python Book List</h1>
  
    <div class="book">
        <h2>Python Basics</h2>
        <p class="author">Author: Kim Chulsu</p>
        <p class="price">Price: 20,000 won</p>
    </div>
  
    <div class="book">
        <h2>Advanced Python</h2>
        <p class="author">Author: Park Young-hee</p>
        <p class="price">Price: 25,000 won</p>
    </div>
  
    <div class="book">
        <h2>Data Analysis</h2>
        <p class="author">Author: Lee Min-su</p>
        <p class="price">Price: 30,000 won</p>
    </div>
</body>
</html>
```

### Reading and Parsing HTML (HTML 파일 읽고 파싱하기)

Now that we have an HTML file, we need to read it and parse it using BeautifulSoup. When you read an HTML file, it becomes a string. BeautifulSoup takes that string and converts it into a structured object that you can navigate and search through.

이제 HTML 파일을 읽고 BeautifulSoup을 사용하여 파싱해야 합니다. HTML 파일을 읽으면 문자열이 됩니다. BeautifulSoup은 그 문자열을 구조화된 객체로 변환하여 탐색하고 검색할 수 있게 합니다.

```python
from bs4 import BeautifulSoup

# Read HTML file (HTML 파일 읽기)
with open('sample.html', 'r', encoding='utf-8') as file:
    html = file.read()

# Create BeautifulSoup object (BeautifulSoup 객체 생성)
soup = BeautifulSoup(html, 'html.parser')

# Get heading (제목 가져오기)
title = soup.find('h1')
print(title.text)  # Python Book List
```

**Output (실행 결과):**

```
Python Book List
```

---

## 5️⃣ Finding Tags (태그 찾기)

BeautifulSoup provides several powerful methods to find and navigate HTML elements. These methods are the foundation of web scraping. Understanding how to use `find()` and `find_all()` correctly will enable you to extract any data from HTML.

BeautifulSoup은 HTML 요소를 찾고 탐색하기 위한 여러 강력한 메서드를 제공합니다. 이 메서드들은 웹 스크래핑의 기초입니다. `find()`와 `find_all()`을 올바르게 사용하는 방법을 이해하면 HTML에서 모든 데이터를 추출할 수 있습니다.

### Using find() - Finding the First Element (첫 번째 하나만)

The `find()` method searches for the first element that matches your criteria and returns it. If no match is found, it returns None. This is useful when you're looking for a specific unique element on a page, such as a page title or a single featured product.

`find()` 메서드는 기준과 일치하는 첫 번째 요소를 검색하여 반환합니다. 일치하는 것이 없으면 None을 반환합니다. 페이지 제목이나 단일 특집 상품과 같이 페이지의 특정 고유 요소를 찾을 때 유용합니다.

```python
from bs4 import BeautifulSoup

with open('sample.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find first h2 tag (첫 번째 h2 태그 찾기)
first_book = soup.find('h2')
print(first_book.text)  # Python Basics

# Find first element with 'author' class (첫 번째 .author 클래스 찾기)
first_author = soup.find(class_='author')
print(first_author.text)  # Author: Kim Chulsu
```

⚠️ **Important Note**: `class` is a reserved keyword in Python, so BeautifulSoup uses the syntax `class_='classname'` to avoid conflicts. Note the underscore after 'class'.

⚠️ **중요**: `class`는 파이썬 예약어이므로, BeautifulSoup에서는 충돌을 피하기 위해 `class_='클래스명'` 문법을 사용합니다. 'class' 다음의 언더스코어에 주목하세요.

### Using find_all() - Finding All Matching Elements (모두 찾기)

The `find_all()` method finds all elements that match your criteria and returns them as a list. This is the most common method for web scraping because you typically want to extract multiple items of the same type from a page, such as all products in a category or all articles on a news page.

`find_all()` 메서드는 기준과 일치하는 모든 요소를 찾아 리스트로 반환합니다. 이것은 웹 스크래핑에서 가장 일반적인 메서드입니다. 왜냐하면 일반적으로 카테고리의 모든 상품이나 뉴스 페이지의 모든 기사와 같이 페이지에서 같은 타입의 여러 항목을 추출하기를 원하기 때문입니다.

```python
from bs4 import BeautifulSoup

with open('sample.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find all h2 tags (모든 h2 태그 찾기)
all_books = soup.find_all('h2')
for book in all_books:
    print(book.text)
```

**Output (실행 결과):**

```
Python Basics
Advanced Python
Data Analysis
```

### Finding Elements by Class (클래스로 찾기)

You can search for elements using their class name. This is very practical because developers often use class attributes to group related elements. By searching for a class, you can easily extract all items of a particular type, even if they're scattered throughout the HTML.

클래스 이름을 사용하여 요소를 검색할 수 있습니다. 이것은 개발자들이 관련 요소들을 그룹화하기 위해 자주 class 속성을 사용하므로 매우 실용적입니다. class로 검색하면 HTML 전체에 산재되어 있더라도 특정 타입의 모든 항목을 쉽게 추출할 수 있습니다.

```python
from bs4 import BeautifulSoup

with open('sample.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find all div elements with 'book' class (book 클래스를 가진 모든 div 찾기)
books = soup.find_all('div', class_='book')

print(f"Total: {len(books)} books")

for book in books:
    title = book.find('h2').text
    author = book.find(class_='author').text
    price = book.find(class_='price').text
  
    print(f"\nTitle: {title}")
    print(f"{author}")
    print(f"{price}")
```

**Output (실행 결과):**

```
Total: 3 books

Title: Python Basics
Author: Kim Chulsu
Price: 20,000 won

Title: Advanced Python
Author: Park Young-hee
Price: 25,000 won

Title: Data Analysis
Author: Lee Min-su
Price: 30,000 won
```

---

## 6️⃣ Extracting Attributes (속성 가져오기)

HTML elements often have attributes that contain important information. For example, `<a>` tags have `href` attributes that contain URLs, and `<img>` tags have `src` attributes that point to image files. Learning to extract these attributes is essential because much of the useful data in web scraping comes from attributes rather than just the text content of elements.

HTML 요소들은 종종 중요한 정보를 포함하는 속성을 가집니다. 예를 들어, `<a>` 태그는 URL을 포함하는 `href` 속성을 가지고, `<img>` 태그는 이미지 파일을 가리키는 `src` 속성을 가집니다. 이 속성들을 추출하는 것을 배우는 것이 필수적입니다. 왜냐하면 웹 스크래핑의 많은 유용한 데이터는 요소의 텍스트 콘텐츠보다는 속성에서 나오기 때문입니다.

### Creating a Sample HTML File (실습용 HTML 파일 만들기)

Create a new file named `links.html` with links and images:

링크와 이미지가 있는 `links.html`라는 새 파일을 만드세요:

**links.html:**

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Link Collection</title>
</head>
<body>
    <h1>Useful Websites</h1>
  
    <a href="https://www.python.org">Official Python Site</a>
    <a href="https://www.github.com">GitHub</a>
    <a href="https://stackoverflow.com">Stack Overflow</a>
  
    <h2>Images</h2>
    <img src="logo.png" alt="Logo">
</body>
</html>
```

### Extracting Links (링크 추출하기)

To extract links from a web page, we find all `<a>` tags and access their `href` attributes. The `.get()` method retrieves an attribute value, or you can use bracket notation like `.['href']`. The `.get()` method is safer because it returns None if the attribute doesn't exist, rather than raising an error.

웹페이지에서 링크를 추출하려면 모든 `<a>` 태그를 찾고 `href` 속성에 접근합니다. `.get()` 메서드는 속성 값을 검색하거나 `.['href']`와 같은 대괄호 표기법을 사용할 수 있습니다. `.get()` 메서드는 속성이 없을 때 오류를 발생시키지 않고 None을 반환하므로 더 안전합니다.

```python
from bs4 import BeautifulSoup

with open('links.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find all links (모든 링크 찾기)
links = soup.find_all('a')

print("Website List:")
print("=" * 50)

for link in links:
    text = link.text
    url = link.get('href')  # Or use link['href']
    print(f"{text}: {url}")
```

**Output (실행 결과):**

```
Website List:
==================================================
Official Python Site: https://www.python.org
GitHub: https://www.github.com
Stack Overflow: https://stackoverflow.com
```

### Extracting Image Information (이미지 정보 추출하기)

Similar to extracting links, we can extract image information by finding all `<img>` tags and accessing their attributes. The `src` attribute contains the image file path, and the `alt` attribute contains the description text. These are useful for organizing images or building image galleries.

링크를 추출하는 것과 유사하게, 모든 `<img>` 태그를 찾고 속성에 접근하여 이미지 정보를 추출할 수 있습니다. `src` 속성은 이미지 파일 경로를 포함하고, `alt` 속성은 설명 텍스트를 포함합니다. 이들은 이미지를 조직하거나 이미지 갤러리를 구축하는 데 유용합니다.

```python
from bs4 import BeautifulSoup

with open('links.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find all images (모든 이미지 찾기)
images = soup.find_all('img')

for img in images:
    src = img.get('src')
    alt = img.get('alt')
    print(f"Image: {src}")
    print(f"Description: {alt}")
```

---

## 7️⃣ Scraping Real Websites (실제 웹사이트 스크래핑)

Now that you've mastered the basics with local HTML files, we can move to scraping actual websites on the internet. The process is similar, but instead of reading a file, we use the requests library to download the web page. We then parse the HTML just as before.

이제 로컬 HTML 파일로 기본을 마스터했으니, 인터넷의 실제 웹사이트를 스크래핑하는 것으로 넘어갈 수 있습니다. 프로세스는 유사하지만, 파일을 읽는 대신 requests 라이브러리를 사용하여 웹페이지를 다운로드합니다. 그 후 이전과 마찬가지로 HTML을 파싱합니다.

### Downloading Web Pages (웹페이지 다운로드)

The requests library makes downloading web pages very simple. You provide a URL, and it returns the page content along with metadata about the response, such as the status code. The status code tells you whether the request was successful or if there was an error. A status code of 200 means success.

requests 라이브러리는 웹페이지를 다운로드하는 것을 매우 간단하게 만듭니다. URL을 제공하면 페이지 콘텐츠와 상태 코드와 같은 응답에 대한 메타데이터를 반환합니다. 상태 코드는 요청이 성공했는지 또는 오류가 있었는지 알려줍니다. 상태 코드 200은 성공을 의미합니다.

```python
import requests
from bs4 import BeautifulSoup

# Download web page (웹페이지 가져오기)
url = "https://example.com"
response = requests.get(url, verify=False)

# Check response (응답 확인)
if response.status_code == 200:
    print("✓ Web page downloaded successfully!")
    html = response.text
  
    # Parse HTML (HTML 파싱)
    soup = BeautifulSoup(html, 'html.parser')
  
    # Get heading (제목 가져오기)
    title = soup.find('h1')
    if title:
        print(f"Title: {title.text}")
else:
    print(f"❌ Error: {response.status_code}")
```

**HTTP Status Codes (HTTP 상태 코드):**

Understanding status codes is important for debugging web scraping issues:

상태 코드를 이해하는 것은 웹 스크래핑 문제를 디버깅하는 데 중요합니다:

- **200**: Success - The page was retrieved successfully (성공 - 페이지가 성공적으로 검색됨)
- **404**: Not Found - The URL doesn't exist (찾을 수 없음 - URL이 존재하지 않음)
- **403**: Forbidden - You don't have permission to access this page (금지됨 - 이 페이지에 접근할 권한이 없음)
- **500**: Server Error - The web server encountered an error (서버 오류 - 웹 서버에 오류 발생)

---

## 8️⃣ Practical Example: Collecting News Headlines (실전 예제: 뉴스 헤드라인 수집)

Now let's work through a complete practical example: collecting news headlines from a website. This example demonstrates the entire web scraping workflow from downloading to parsing to storing data.

이제 웹사이트에서 뉴스 헤드라인을 수집하는 완전한 실전 예제를 살펴봅시다. 이 예제는 다운로드부터 파싱까지 데이터 저장까지의 전체 웹 스크래핑 워크플로우를 보여줍니다.

### Creating Sample Data (실습용 HTML 파일 만들기)

First, create a file named `news.html` that simulates a news website:

먼저 뉴스 웹사이트를 시뮬레이션하는 `news.html` 파일을 만드세요:

**news.html:**

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>News Site</title>
</head>
<body>
    <h1>Today's News</h1>
  
    <div class="news-item">
        <h2 class="headline">Python Ranked Most Popular Programming Language</h2>
        <p class="date">2024-01-15</p>
        <p class="summary">Python topped the 2024 developer survey, beating Java and JavaScript.</p>
        <a href="news1.html" class="more">Read More</a>
    </div>
  
    <div class="news-item">
        <h2 class="headline">AI Technology Revolutionizes Medical Field</h2>
        <p class="date">2024-01-14</p>
        <p class="summary">Artificial intelligence significantly improves disease diagnosis accuracy.</p>
        <a href="news2.html" class="more">Read More</a>
    </div>
  
    <div class="news-item">
        <h2 class="headline">Electric Vehicle Market Projected to Grow 30% This Year</h2>
        <p class="date">2024-01-13</p>
        <p class="summary">Global electric vehicle sales are expected to increase significantly.</p>
        <a href="news3.html" class="more">Read More</a>
    </div>
</body>
</html>
```

### Scraping Headlines (헤드라인 스크래핑)

Now write a Python script to extract headline information. This script demonstrates how to find multiple news items, extract data from each one, and organize it in a structured way.

이제 헤드라인 정보를 추출하는 파이썬 스크립트를 작성하세요. 이 스크립트는 여러 뉴스 항목을 찾고, 각각에서 데이터를 추출하고, 구조화된 방식으로 정리하는 방법을 보여줍니다.

```python
from bs4 import BeautifulSoup

# Read HTML file (HTML 파일 읽기)
with open('news.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Find all news items (모든 뉴스 항목 찾기)
news_items = soup.find_all('div', class_='news-item')

print("=" * 70)
print("📰 News Headlines")
print("=" * 70)

for i, item in enumerate(news_items, 1):
    headline = item.find('h2', class_='headline').text
    date = item.find('p', class_='date').text
    summary = item.find('p', class_='summary').text
    link = item.find('a', class_='more').get('href')
  
    print(f"\n[{i}] {headline}")
    print(f"    Date: {date}")
    print(f"    Summary: {summary}")
    print(f"    Link: {link}")

print("\n" + "=" * 70)
```

**Output (실행 결과):**

```
======================================================================
📰 News Headlines
======================================================================

[1] Python Ranked Most Popular Programming Language
    Date: 2024-01-15
    Summary: Python topped the 2024 developer survey, beating Java and JavaScript.
    Link: news1.html

[2] AI Technology Revolutionizes Medical Field
    Date: 2024-01-14
    Summary: Artificial intelligence significantly improves disease diagnosis accuracy.
    Link: news2.html

[3] Electric Vehicle Market Projected to Grow 30% This Year
    Date: 2024-01-13
    Summary: Global electric vehicle sales are expected to increase significantly.
    Link: news3.html

======================================================================
```

### Saving to CSV File (CSV 파일로 저장)

To make the data more useful, we should save it to a file. CSV (Comma-Separated Values) is a common format for storing tabular data. The following script scrapes news data and saves it to a CSV file that you can open in Excel or other spreadsheet applications.

데이터를 더 유용하게 만들기 위해 파일로 저장해야 합니다. CSV(Comma-Separated Values)는 표 형식 데이터를 저장하는 일반적인 형식입니다. 다음 스크립트는 뉴스 데이터를 스크래핑하여 Excel 또는 다른 스프레드시트 애플리케이션에서 열 수 있는 CSV 파일로 저장합니다.

```python
from bs4 import BeautifulSoup
import csv

# Read HTML file (HTML 파일 읽기)
with open('news.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Collect news data (뉴스 데이터 수집)
news_data = []
news_items = soup.find_all('div', class_='news-item')

for item in news_items:
    headline = item.find('h2', class_='headline').text
    date = item.find('p', class_='date').text
    summary = item.find('p', class_='summary').text
  
    news_data.append({
        'Headline': headline,
        'Date': date,
        'Summary': summary
    })

# Save to CSV file (CSV 파일로 저장)
with open('news_data.csv', 'w', newline='', encoding='utf-8-sig') as file:
    fieldnames = ['Headline', 'Date', 'Summary']
    csv_writer = csv.DictWriter(file, fieldnames=fieldnames)
  
    csv_writer.writeheader()
    csv_writer.writerows(news_data)

print(f"✓ {len(news_data)} news articles saved to news_data.csv!")
```

⚠️ **Note on Encoding**: The `encoding='utf-8-sig'` parameter is important when working with Korean text. It ensures that the CSV file displays correctly in Excel without showing garbled characters.

⚠️ **인코딩에 대한 주의**: `encoding='utf-8-sig'` 매개변수는 한글 텍스트를 다룰 때 중요합니다. CSV 파일이 Excel에서 문자가 깨지지 않고 올바르게 표시되도록 보장합니다.

---

## 9️⃣ Practical Example: Collecting Product Information (실전 예제: 상품 정보 수집)

Let's work through another practical example that's commonly used in e-commerce: collecting product information. This example shows how to extract numerical data and perform basic calculations on scraped data.

전자상거래에서 흔히 사용되는 또 다른 실전 예제인 상품 정보 수집을 살펴봅시다. 이 예제는 숫자 데이터를 추출하고 스크래핑된 데이터에 대해 기본 계산을 수행하는 방법을 보여줍니다.

### Creating Sample Product Data (실습용 HTML 파일)

Create a file named `products.html` that contains product information:

상품 정보를 포함하는 `products.html` 파일을 만드세요:

**products.html:**

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Product List</title>
</head>
<body>
    <h1>Computer Products</h1>
  
    <div class="product">
        <h3 class="name">Wireless Mouse</h3>
        <p class="price">35,000 won</p>
        <p class="rating">⭐⭐⭐⭐⭐ (4.5)</p>
        <p class="stock">Stock: 15 items</p>
    </div>
  
    <div class="product">
        <h3 class="name">Mechanical Keyboard</h3>
        <p class="price">120,000 won</p>
        <p class="rating">⭐⭐⭐⭐ (4.2)</p>
        <p class="stock">Stock: 8 items</p>
    </div>
  
    <div class="product">
        <h3 class="name">27-inch Monitor</h3>
        <p class="price">350,000 won</p>
        <p class="rating">⭐⭐⭐⭐⭐ (4.8)</p>
        <p class="stock">Stock: 3 items</p>
    </div>
  
    <div class="product">
        <h3 class="name">Webcam</h3>
        <p class="price">80,000 won</p>
        <p class="rating">⭐⭐⭐⭐ (4.0)</p>
        <p class="stock">Stock: 20 items</p>
    </div>
</body>
</html>
```

### Scraping Product Information (상품 정보 스크래핑)

This script demonstrates a more complex scraping task that involves extracting numbers from text and performing calculations. We'll use regular expressions to extract just the numeric values from the text.

이 스크립트는 텍스트에서 숫자를 추출하고 계산을 수행하는 더 복잡한 스크래핑 작업을 보여줍니다. 정규표현식을 사용하여 텍스트에서 숫자 값만 추출합니다.

```python
from bs4 import BeautifulSoup
import csv
import re

# Read HTML file (HTML 파일 읽기)
with open('products.html', 'r', encoding='utf-8') as file:
    html = file.read()

soup = BeautifulSoup(html, 'html.parser')

# Collect product information (상품 정보 수집)
products = []
product_items = soup.find_all('div', class_='product')

print("=" * 70)
print("🛒 Product Information")
print("=" * 70)

for item in product_items:
    name = item.find('h3', class_='name').text
    price_text = item.find('p', class_='price').text
    rating_text = item.find('p', class_='rating').text
    stock_text = item.find('p', class_='stock').text
  
    # Extract numbers only (숫자만 추출)
    price = int(re.sub(r'[^0-9]', '', price_text))
    rating = float(re.findall(r'\d+\.\d+', rating_text)[0])
    stock = int(re.findall(r'\d+', stock_text)[0])
  
    products.append({
        'Product Name': name,
        'Price': price,
        'Rating': rating,
        'Stock': stock
    })
  
    print(f"\nProduct: {name}")
    print(f"Price: {price:,} won")
    print(f"Rating: {rating}")
    print(f"Stock: {stock} items")
  
    # Warn about low stock (재고 부족 경고)
    if stock < 10:
        print("⚠️  Low Stock!")

# Save to CSV file (CSV 파일로 저장)
with open('products_data.csv', 'w', newline='', encoding='utf-8-sig') as file:
    fieldnames = ['Product Name', 'Price', 'Rating', 'Stock']
    csv_writer = csv.DictWriter(file, fieldnames=fieldnames)
  
    csv_writer.writeheader()
    csv_writer.writerows(products)

print("\n" + "=" * 70)
print(f"✓ {len(products)} products saved to products_data.csv!")

# Statistics (통계)
total_value = sum(p['Price'] * p['Stock'] for p in products)
avg_rating = sum(p['Rating'] for p in products) / len(products)

print(f"\n📊 Statistics:")
print(f"Total Inventory Value: {total_value:,} won")
print(f"Average Rating: {avg_rating:.2f}")
```

---

## 🔟 Ethics and Legal Considerations in Web Scraping (웹 스크래핑 윤리와 법)

Web scraping is a powerful tool, but like any powerful tool, it must be used responsibly. There are legal and ethical considerations you must understand before scraping websites. Always remember that just because you can scrape something doesn't mean you should.

웹 스크래핑은 강력한 도구이지만, 다른 강력한 도구처럼 책임감 있게 사용해야 합니다. 웹사이트를 스크래핑하기 전에 이해해야 할 법적 및 윤리적 고려사항이 있습니다. 뭔가를 스크래핑할 수 있다는 것이 반드시 해야 한다는 뜻은 아니라는 것을 항상 기억하세요.

### Important Guidelines (⚠️ 주의사항)

**✅ Things You Can Do (해도 되는 것):**

- Scrape publicly available information (공개된 정보 수집)
- Follow robots.txt guidelines and respect the website's scraping policies (robots.txt를 따르고 웹사이트의 스크래핑 정책 존중)
- Use appropriate delays between requests to avoid overloading servers (서버 부담을 주지 않도록 요청 사이에 적절한 지연 사용)
- Use scraped data for personal projects and learning purposes (개인 프로젝트와 학습 목적으로 스크래핑 데이터 사용)

**❌ Things You Cannot Do (하면 안 되는 것):**

- Collect copyrighted content without permission (저작권이 있는 콘텐츠 무단 수집)
- Scrape personal information (개인정보 수집)
- Make excessive requests that overload servers (서버에 부하를 주는 대량 요청)
- Bypass login systems to access private information (로그인이 필요한 정보 무단 수집)
- Use scraped data for commercial purposes without permission (수집한 데이터를 허락 없이 상업적 이용)

### Checking robots.txt (robots.txt 확인)

Every website can have a `robots.txt` file that specifies which parts of the website can be scraped. Always check this file before scraping. The robots.txt file is located at the root of the website.

모든 웹사이트는 웹사이트의 어느 부분을 스크래핑할 수 있는지 지정하는 `robots.txt` 파일을 가질 수 있습니다. 스크래핑 전에 항상 이 파일을 확인하세요. robots.txt 파일은 웹사이트의 루트에 위치합니다.

```
https://example.com/robots.txt

User-agent: *
Disallow: /admin/        # Scraping forbidden (수집 금지)
Disallow: /private/      # Scraping forbidden (수집 금지)
Allow: /public/          # Scraping allowed (수집 허용)
```

### Setting Request Delays (요청 간격 설정)

When scraping multiple pages, always include delays between requests. This is both polite and necessary. Making too many requests in a short time can slow down the website for other users or even crash the server.

여러 페이지를 스크래핑할 때 항상 요청 사이에 지연을 포함하세요. 이것은 예의이자 필요합니다. 짧은 시간에 너무 많은 요청을 하면 다른 사용자의 웹사이트 속도를 낮추거나 서버를 다운시킬 수도 있습니다.

```python
import requests
import time

urls = ['url1', 'url2', 'url3']

for url in urls:
    response = requests.get(url)
    # Process data... (데이터 처리...)
  
    time.sleep(2)  # Wait 2 seconds between requests (요청 사이 2초 대기)
```

### Legal Responsibility (법적 책임)

Web scraping itself is not illegal. However, what you do with the data you scrape can be illegal. The terms of service of a website matter, so always read them carefully before scraping. When in doubt, contact the website owner for permission.

웹 스크래핑 자체는 불법이 아닙니다. 하지만 스크래핑한 데이터를 사용하는 방식이 불법일 수 있습니다. 웹사이트의 이용약관이 중요하므로, 스크래핑 전에 항상 주의 깊게 읽으세요. 확신이 없으면 웹사이트 소유자에게 허락을 구하세요.

- Web scraping itself is not illegal (웹 스크래핑 자체는 불법이 아닙니다)
- However, the way you use the data can be problematic (하지만 데이터 사용 방식이 문제가 될 수 있습니다)
- Always check website terms of service before commercial use (상업적 이용 전 반드시 웹사이트 이용약관 확인)
- Use scraped data only for personal learning (스크래핑 데이터를 개인 학습용으로만 사용하세요)

---

## 📝 Key Concepts Summary (핵심 개념 정리)

Understanding the fundamental workflow of web scraping will help you apply it to any website. The basic process is always the same, regardless of what data you're trying to extract.

웹 스크래핑의 기본 워크플로우를 이해하면 모든 웹사이트에 이를 적용할 수 있습니다. 추출하려는 데이터가 무엇이든 기본 프로세스는 항상 동일합니다.

### Basic Workflow (기본 구조)

The web scraping process follows these four essential steps:

웹 스크래핑 프로세스는 다음 네 가지 필수 단계를 따릅니다:

```python
import requests
from bs4 import BeautifulSoup

# Step 1: Download the web page (단계 1: 웹페이지 다운로드)
response = requests.get(url)
html = response.text

# Step 2: Parse HTML (단계 2: HTML 파싱)
soup = BeautifulSoup(html, 'html.parser')

# Step 3: Find desired elements (단계 3: 원하는 요소 찾기)
elements = soup.find_all('tag', class_='classname')

# Step 4: Extract data (단계 4: 데이터 추출)
for element in elements:
    text = element.text
    link = element.get('href')
```

### Key Methods (주요 메서드)

These are the essential methods you need for web scraping:

웹 스크래핑에 필요한 필수 메서드들입니다:

- **`find()`**: Finds the first matching element (첫 번째 일치하는 요소 찾기)
- **`find_all()`**: Finds all matching elements and returns a list (모든 일치하는 요소를 찾고 리스트 반환)
- **`.text`**: Extracts the text content of an element (요소의 텍스트 콘텐츠 추출)
- **`.get('attribute')`**: Gets the value of a specific attribute (특정 속성의 값 가져오기)

### Important Considerations (주의사항)

Remember these key points when scraping:

스크래핑할 때 이 주요 사항들을 기억하세요:

- Check robots.txt before scraping (스크래핑 전 robots.txt 확인)
- Set appropriate delays between requests (요청 사이에 적절한 지연 설정)
- Set User-Agent headers to identify your program (프로그램을 식별하기 위해 User-Agent 헤더 설정)
- Always handle exceptions with try-except blocks (항상 try-except 블록으로 예외 처리)

---

## 💡 Practice Assignments (실습 과제)

### Assignment 1: Book Information Collector (과제 1: 도서 목록 수집기)

**Objective**: Collect book information from an HTML file and save it to a CSV file.

**목표**: HTML 파일에서 도서 정보를 수집하여 CSV 파일로 저장하세요.

**Step 1: Prepare Sample Data (1단계: 샘플 데이터 준비)**

Create a file named `books.html`:

`books.html` 파일을 만드세요:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Book List</title>
</head>
<body>
    <h1>Programming Books</h1>
  
    <div class="book">
        <h3 class="title">Python Complete Guide</h3>
        <p class="author">Author: Kim Python</p>
        <p class="publisher">Publisher: Coding Press</p>
        <p class="price">28,000 won</p>
        <p class="pages">450 pages</p>
    </div>
  
    <div class="book">
        <h3 class="title">JavaScript Basics</h3>
        <p class="author">Author: Lee JavaScript</p>
        <p class="publisher">Publisher: Web Development Press</p>
        <p class="price">25,000 won</p>
        <p class="pages">380 pages</p>
    </div>
  
    <div class="book">
        <h3 class="title">Data Science Introduction</h3>
        <p class="author">Author: Park Data</p>
        <p class="publisher">Publisher: AI Press</p>
        <p class="price">32,000 won</p>
        <p class="pages">520 pages</p>
    </div>
</body>
</html>
```

**Step 2: Requirements (2단계: 요구사항)**

1. Extract all book information (title, author, publisher, price, page count)
2. Extract numbers from price and pages fields
3. Display book information in table format on console
4. Save to `books_data.csv`

**Step 3: Expected Output (3단계: 예상 출력)**

```
======================================================================
📚 Book List
======================================================================

[1] Python Complete Guide
    Author: Kim Python
    Publisher: Coding Press
    Price: 28,000 won
    Pages: 450 pages

[2] JavaScript Basics
    Author: Lee JavaScript
    Publisher: Web Development Press
    Price: 25,000 won
    Pages: 380 pages

[3] Data Science Introduction
    Author: Park Data
    Publisher: AI Press
    Price: 32,000 won
    Pages: 520 pages

======================================================================
Total 3 books

✓ Saved to books_data.csv!
```

---

### Assignment 2: Weather Information Collector (과제 2: 날씨 정보 수집기)

**Objective**: Collect weekly weather information from an HTML file and perform statistical calculations.

**목표**: HTML 파일에서 주간 날씨 정보를 수집하여 통계 계산을 수행하세요.

**Step 1: Create Sample Data (1단계: 샘플 데이터 준비)**

Create a file named `weather.html`:

`weather.html` 파일을 만드세요:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Weekly Weather</title>
</head>
<body>
    <h1>Seoul Weekly Weather</h1>
  
    <div class="day">
        <p class="date">2024-01-15 (Monday)</p>
        <p class="weather">Clear</p>
        <p class="temp">High 5°C / Low -2°C</p>
        <p class="humidity">Humidity: 45%</p>
    </div>
  
    <div class="day">
        <p class="date">2024-01-16 (Tuesday)</p>
        <p class="weather">Cloudy</p>
        <p class="temp">High 3°C / Low -4°C</p>
        <p class="humidity">Humidity: 60%</p>
    </div>
  
    <div class="day">
        <p class="date">2024-01-17 (Wednesday)</p>
        <p class="weather">Snow</p>
        <p class="temp">High 0°C / Low -6°C</p>
        <p class="humidity">Humidity: 75%</p>
    </div>
  
    <div class="day">
        <p class="date">2024-01-18 (Thursday)</p>
        <p class="weather">Clear</p>
        <p class="temp">High 6°C / Low -1°C</p>
        <p class="humidity">Humidity: 40%</p>
    </div>
</body>
</html>
```

**Step 2: Requirements (2단계: 요구사항)**

1. Extract all weather information (date, weekday, weather, high/low temp, humidity)
2. Extract numbers from temperature and humidity fields
3. Calculate weekly average temperature
4. Calculate weather statistics by type
5. Save to `weather_data.csv`

**Step 3: Expected Output (3단계: 예상 출력)**

```
======================================================================
🌤️  Seoul Weekly Weather
======================================================================

[Monday] 2024-01-15
  Weather: Clear
  Temperature: High 5°C / Low -2°C
  Humidity: 45%

[Tuesday] 2024-01-16
  Weather: Cloudy
  Temperature: High 3°C / Low -4°C
  Humidity: 60%

...

======================================================================
📊 Weekly Statistics

Average High Temperature: 3.5°C
Average Low Temperature: -3.2°C
Average Humidity: 55.0%

Weather by Type:
  Clear: 2 days
  Cloudy: 1 day
  Snow: 1 day

✓ Saved to weather_data.csv!
```

---

## ✅ Quiz (퀴즈)

### [Beginner] Question 1

Which library is used to download web pages?

웹페이지를 가져오는 라이브러리는?

1. BeautifulSoup
2. requests
3. csv
4. pandas

### [Intermediate] Question 2

Which library is used to parse HTML?

HTML을 파싱하는 라이브러리는?

1. requests
2. csv
3. BeautifulSoup
4. json

### [Intermediate] Question 3

Which method finds only the first matching element?

첫 번째로 일치하는 요소만 찾는 메서드는?

1. find_all()
2. find()
3. search()
4. locate()

### [Advanced] Question 4

Which method is used to get the value of an element's attribute?

요소의 속성 값을 가져오는 메서드는?

1. get_attr()
2. attr()
3. get()
4. ['attribute']

### [Advanced] Question 5

Which function is used to add delays between requests?

요청 사이에 지연을 추가하는 함수는?

1. time.wait()
2. time.delay()
3. time.sleep()
4. time.pause()

---

## 🔑 Quiz Answers and Explanations (퀴즈 정답 및 해설)

**Answer 1: 2**

The requests library is specifically designed to download content from websites. You use it with `response = requests.get(url)` to retrieve the HTML content of a web page.

requests 라이브러리는 웹사이트에서 콘텐츠를 다운로드하기 위해 특별히 설계되었습니다. `response = requests.get(url)`을 사용하여 웹페이지의 HTML 콘텐츠를 검색합니다.

**Answer 2: 3**

BeautifulSoup is the library specifically for parsing and analyzing HTML structures. It allows you to navigate through HTML and extract specific elements and their data.

BeautifulSoup은 HTML 구조를 파싱하고 분석하기 위한 라이브러리입니다. HTML을 탐색하고 특정 요소와 데이터를 추출할 수 있습니다.

**Answer 3: 2**

The `find()` method returns only the first element that matches the search criteria. If you need all matching elements, use `find_all()` instead.

`find()` 메서드는 검색 기준과 일치하는 첫 번째 요소만 반환합니다. 모든 일치하는 요소가 필요하면 대신 `find_all()`을 사용하세요.

**Answer 4: 3**

The `get()` method retrieves the value of an element's attribute. For example, `link.get('href')` gets the URL from an `<a>` tag. You can also use bracket notation: `link['href']`.

`get()` 메서드는 요소의 속성 값을 검색합니다. 예를 들어, `link.get('href')`는 `<a>` 태그에서 URL을 가져옵니다. 대괄호 표기법도 사용할 수 있습니다: `link['href']`.

**Answer 5: 3**

The `time.sleep()` function pauses the program for a specified number of seconds. This is essential for responsible web scraping to avoid overloading servers with too many rapid requests.

`time.sleep()` 함수는 프로그램을 지정된 시간(초)만큼 일시 중지합니다. 이것은 너무 많은 빠른 요청으로 서버에 부하를 주지 않도록 하기 위해 책임감 있는 웹 스크래핑에 필수입니다.

---

Thank you for your attention.   
Cho Jeonghyun ([peterchokr@gmail.com](mailto:peterchokr@gmail.com)). Yeungnam University College

"Produced in collaboration with Claude and Gemini."
