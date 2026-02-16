# Async Web Crawler

A high-performance, asynchronous web crawler built with Python that efficiently extracts structured data from websites. This project demonstrates advanced Python programming techniques including async/await patterns, concurrent programming, and robust error handling.

## 🚀 Features

- **Asynchronous Crawling**: Utilizes `aiohttp` for non-blocking HTTP requests with configurable concurrency limits
- **Intelligent Content Extraction**: Parses HTML using BeautifulSoup4 to extract H1 headings, first paragraphs, outgoing links, and image URLs
- **CSV Report Generation**: Produces structured CSV reports with semicolon-separated lists for multi-value fields
- **Domain-Scoped Crawling**: Respects domain boundaries to stay within the target website
- **Duplicate Prevention**: Normalizes URLs to avoid crawling the same page multiple times
- **Comprehensive Testing**: Unit tests covering all core functions with edge cases
- **Production-Ready**: Includes proper error handling, logging, and resource management

## 🛠️ Technical Skills Demonstrated

### Core Technologies
- **Python 3.13+**: Modern Python with type hints and async features
- **aiohttp**: Asynchronous HTTP client for high-performance web requests
- **BeautifulSoup4**: HTML parsing and content extraction
- **asyncio**: Python's asynchronous programming framework
- **CSV Module**: Native Python CSV handling with proper encoding

### Advanced Concepts
- **Concurrent Programming**: Semaphore-based concurrency control
- **Async Context Managers**: Proper resource management with `__aenter__`/`__aexit__`
- **URL Normalization**: Robust URL parsing and deduplication
- **Thread-Safe Data Structures**: Async locks for shared state management
- **Error Handling**: Comprehensive exception handling with graceful degradation
- **Memory Management**: Efficient data structures and garbage collection awareness

### Software Engineering Practices
- **Modular Architecture**: Clean separation of concerns across multiple modules
- **Unit Testing**: Comprehensive test suite with edge cases and mocking
- **Configuration Management**: Command-line argument parsing and validation
- **Documentation**: Clear code comments and professional README
- **Version Control**: Git-based development with proper .gitignore

## 📋 Requirements

- Python 3.13 or higher
- Dependencies listed in `pyproject.toml`

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/async-web-crawler.git
cd async-web-crawler
```

2. Install dependencies:
```bash
pip install -e .
```

## 🚀 Usage

Run the crawler with the following command:

```bash
python main.py <base_url> <max_concurrency> <max_pages>
```

### Parameters

- `base_url`: The starting URL to begin crawling (e.g., `https://example.com`)
- `max_concurrency`: Maximum number of concurrent requests (recommended: 5-10)
- `max_pages`: Maximum number of pages to crawl (recommended: 100-1000)

### Example

```bash
python main.py https://blog.example.com 5 100
```

This will crawl `blog.example.com` with up to 5 concurrent requests and stop after 100 pages.

## 📊 Output

The crawler generates a `report.csv` file with the following columns:

- `page_url`: The URL of the crawled page
- `h1`: The main heading (H1) of the page
- `first_paragraph`: The first paragraph of content
- `outgoing_link_urls`: Semicolon-separated list of all outgoing links
- `image_urls`: Semicolon-separated list of all image URLs

## 🏗️ Architecture

### Core Components

1. **main.py**: Entry point with argument parsing and orchestration
2. **crawl.py**: Core crawling logic with AsyncCrawler class
3. **csv_report.py**: CSV generation and data formatting
4. **test_crawl.py**: Comprehensive unit test suite

### AsyncCrawler Class Design

The `AsyncCrawler` class implements several advanced patterns:

- **Semaphore-based Concurrency**: Limits concurrent requests to prevent overwhelming servers
- **URL Normalization**: Converts URLs to canonical form for deduplication
- **Domain Filtering**: Ensures crawling stays within the target domain
- **Task Management**: Tracks and cancels tasks when limits are reached
- **Resource Management**: Proper cleanup of HTTP sessions and async tasks

### Performance Optimizations

- **Connection Pooling**: aiohttp's built-in connection reuse
- **Lazy Evaluation**: Only processes HTML when content-type is valid
- **Early Termination**: Stops crawling when page limits are reached
- **Memory Efficiency**: Processes pages in streaming fashion

## 🧪 Testing

Run the test suite:

```bash
python -m unittest test_crawl.py
```

The test suite covers:
- URL normalization edge cases
- HTML parsing with various structures
- Link and image extraction
- Error handling scenarios

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Add tests for new functionality
4. Ensure all tests pass
5. Submit a pull request

## 📄 License

MIT License - see LICENSE file for details

## 👨‍💻 Author

Your Name - [your.email@example.com](mailto:your.email@example.com)

---

*This project showcases expertise in asynchronous Python programming, web scraping techniques, and software engineering best practices.*
