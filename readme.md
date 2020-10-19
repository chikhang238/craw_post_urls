# Crawling HTML of chotot.com
This code is only used for crawling HTML of chotot by using webdriver, bs4 and rabbitmq, it also simulates a mouse to click to a button that is required to show a phone number.

## Pre-conditions:
- Install Python 3, pip
- Install successfully elasticsearch.
- Install successfully rabbitmq.
- Download geckodriver.
- If you are not familiar with them or have not installed them yet, please follow many public tutorials.
- Virtualenv (optional)

## Installation
```bash
pip install requirements.txt
```

## Usage
- Set GECKODRIVER in line 26 of crawl.py.
- Firstly, you need to run worker.py for waiting the queue:
```bash
python worker.py
```

- You can control the number of urls you would like to crawl by modifying NUM_URLS in line 24 of crawl.py.
- You can modify SAVE_TO_ES in line 25 of crawl.py to True for saving data to Elasticsearch after crawling.
- Otherwise, you can comment lines 162-163 (crawl.py) for unlimited number of urls.
- Then run send to send links to queue:
```bash
python send.py
```
- You can switch from Firefox to Chrome, please follow the instructions from tutorials.

- phone_number.py is just used for retreiving phone number which is hidden, you may run it by:
```bash
python phone_number.py
```
