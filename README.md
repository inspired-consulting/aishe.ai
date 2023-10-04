# aishe core

## Setup
0. Copy .env.example to .env and modify content
1. Install `tesseract-ocr` for your system with apt etc
2. Install python deps: `pip3 install -r requirements.txt` or update current `pip install -r requirements.txt --upgrade`
3. Install chromium `pip install -q playwright beautifulsoup4 playwright install`
4. Create ngrok domain
5. Install [ngrok](https://ngrok.com/download)
6. Setup [ngrok agent auth](https://dashboard.ngrok.com/get-started/your-authtoken)
7. [Setup google access](https://python.langchain.com/docs/integrations/tools/google_search) to llm and add keys to .env
8. Setup langsmith in .env
8. Start fastapi: `uvicorn app:app --reload`
9. Start ngrok: `ngrok http --domain=DOMAIN 8000`, domain must be the same as the bot creation

## Issues
- Browser is not starting for webscraping, for example within the webpage_tool:
    - add to the browser launch parameters: `args=["--disable-gpu"]` -> `browser = await p.chromium.launch(headless=True, args=["--disable-gpu"])`
    - only observed with wsl2 systems

## Formatting
- `black FOLDER_NAME`

## Testing
tbd