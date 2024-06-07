# Search Result Scraper with Markdown Output Using FastAPI, SearXNG, and Browserless

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Description

This project provides a powerful web scraping tool that fetches search results and converts them into Markdown format using FastAPI, SearXNG, and Browserless. It includes the capability to use proxies for web scraping and handles HTML content conversion to Markdown efficiently.

## Features

- **FastAPI**: A modern, fast web framework for building APIs with Python.
- **SearXNG**: An open-source internet metasearch engine.
- **Browserless**: A web browser automation service.
- **Markdown Output**: Converts HTML content to Markdown format.
- **Proxy Support**: Utilizes proxies for secure and anonymous scraping.

## Prerequisites

Ensure you have the following installed:

- Python 3.11
- Virtualenv
- Docker (for searxng or browserless)

## Setup Instructions

1. **Clone the repository**:
    ```sh
    git clone https://github.com/your-username/search-result-scraper-markdown.git
    cd search-result-scraper-markdown
    ```

2. **Create and activate virtual environment**:
    ```sh
    virtualenv venv
    source venv/bin/activate
    ```

3. **Install dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

4. **Create a .env file** in the root directory with the following content:
    ```env
    SEARXNG_URL=http://localhost:8888
    BROWSERLESS_URL=http://localhost:3000
    TOKEN=BROWSERLESS_TOKEN
    PROXY_PROTOCOL=http
    PROXY_URL=your_proxy_url
    PROXY_USERNAME=your_proxy_username
    PROXY_PASSWORD=your_proxy_password
    PROXY_PORT=your_proxy_port
    REQUEST_TIMEOUT=300
    ```

5. **Run Docker containers for SearXNG and Browserless**:
    ```sh
    ./run-services.sh
    ```

6. **Start the FastAPI application**:
    ```sh
    uvicorn main:app --host 0.0.0.0 --port 8000
    ```

## Usage

### Search Endpoint

To perform a search query, send a GET request to the root endpoint `/` with the query parameters `q` (search query) and `num_results` (number of results).

Example:
```sh
curl "http://localhost:8000/?q=python&num_results=5"
```

### Fetch URL Content

To fetch and convert the content of a specific URL to Markdown, send a GET request to the `/r/{url:path}` endpoint.

Example:
```sh
curl "http://localhost:8000/r/https://example.com"
```

## Using Proxies

This project uses Geonode proxies for web scraping. You can use [my Geonode affiliate link](https://geonode.com/invite/47389) to get started with their proxy services.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

Essa Mamdani - [essamamdani.com](https://essamamdani.com)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgements

- [FastAPI](https://fastapi.tiangolo.com/)
- [SearXNG](https://github.com/searxng/searxng)
- [Browserless](https://www.browserless.io/)