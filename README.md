# 🕸️ Dhilshan's AI Web Scraper

A Streamlit-based web scraping application that uses a headless browser and AI to scrape and parse web content from any public website. The project integrates browser automation with intelligent parsing powered by [Ollama](https://ollama.com) (LLaMA 3.1 via Langchain).

## 🚀 Features

- 🔗 **Scrape Any Website**: Enter a URL, and the app scrapes the body content of the page using Selenium with a Scraping Browser (SBR) proxy.
- 🧼 **Clean DOM Content**: Extracts and cleans the `<body>` content by removing scripts, styles, and unnecessary tags.
- 💬 **Ask Anything**: Describe what you want from the scraped content, and the AI model will parse and extract it for you.
- 🧠 **Powered by LLaMA 3.1**: Uses `langchain` with `langchain_ollama` for accurate and context-aware parsing.
- 🌐 **Captcha-Handling**: Automatically waits for CAPTCHA resolution if present using SBR's solving mechanism.

---

## 🛠️ Tech Stack

- [Streamlit](https://streamlit.io/) – Frontend UI
- [Selenium](https://www.selenium.dev/) – Browser automation
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/) – HTML parsing
- [Langchain](https://www.langchain.com/) – Prompt chaining and AI orchestration
- [Ollama](https://ollama.com) – Local LLM inference with LLaMA 3.1
- [Python Dotenv](https://pypi.org/project/python-dotenv/) – Manage environment variables

---

## 📦 Installation

1. **Clone the repo**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

## Requirements

- streamlit
- langchain
- langchain_ollama
- selenium
- beautifulsoup4
- lxml
- html5lib
- python-dotenv


🧠 How It Works
1. Scraping the Website
The app connects to a Scraping Browser using a proxy (SBR). Once the page is loaded and any CAPTCHA is solved, the HTML content is extracted.

driver.get(website)
driver.execute("executeCdpCommand", {"cmd": "Captcha.waitForSolve", ...})

2. Cleaning the Content
All <script> and <style> elements are stripped out, and clean text is extracted from the <body> tag using BeautifulSoup.

3. Splitting & Parsing
Large DOM content is split into chunks and passed into an LLM chain using langchain and langchain_ollama, with strict prompt instructions to only extract exactly what was asked.
