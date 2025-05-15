# Labl-IT
# Food Label Analyzer

A web application that analyzes food product labels and ingredients using AI to provide detailed nutritional insights and health recommendations.

---

## Features
- Extract product and image data from Blinkit URLs
- Analyze ingredients and nutritional content using AI (Google Gemini, Mistral)
- Provide health insights and safety classifications from FDA, IARC, and other databases
- OCR support for food label images
- User-friendly React interface with Material UI, Tailwind, and Radix UI
- Real-time analysis results with tabbed and recent analyses view

---

## Tech Stack

### Frontend
- React + Vite
- Material UI, Tailwind CSS, Radix UI
- Lottie for animations

### Backend
- Python 3.10+
- Flask (API)
- Flask-CORS
- Selenium (web scraping)
- Google Gemini Pro, Mistral AI
- Pandas, Pillow, OpenCV, Tesseract (OCR)

---

## Directory Structure & Key Files

```
foodlabel/
├── api.py                # Flask API server
├── analyze.py            # Main product/ingredient analysis logic
├── blinkit.py            # Blinkit scraping utilities
├── ocr.py                # OCR and image preprocessing
├── googli.py             # Google Custom Search for ingredient info
├── daily_values.py       # FDA daily values reference
├── prompts.py            # AI prompt templates
├── requirements.txt      # Python dependencies
├── pyproject.toml        # Poetry project config
├── tests.py              # Backend unit tests
├── tests/                # (empty/init)
├── data/                 # Reference CSVs (FDA, IARC, etc.)
├── frontend/             # React frontend app
│   ├── src/
│   │   ├── App.jsx, main.jsx, App.css, index.css
│   │   ├── pages/RecentsPage.jsx
│   │   ├── components/ProductAnalyzer.jsx, Navigation.jsx, ui/
│   │   ├── lib/utils.js
│   │   └── assets/ (images, animations)
│   ├── public/
│   ├── package.json, tailwind.config.js, vite.config.js
│   └── ...
└── ...
```

### Data Directory
- `data/FDA--SCOGS.csv`, `data/monographs.csv`, etc.: Reference databases for ingredient safety and classification.

### Frontend Highlights
- `ProductAnalyzer.jsx`: Main UI for product analysis and results
- `RecentsPage.jsx`: View recent analyses (localStorage)
- `components/ui/`: Custom UI primitives (tabs, popover, card, etc.)

---

## Setup & Installation

### Prerequisites
- Python 3.10 or higher
- Node.js 18 or higher
- Chrome WebDriver (for Selenium)
- Google Gemini API key, Mistral API key, Google Custom Search API key

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd foodlabel
```

### 2. Backend Setup
- Install Poetry (if not installed):
  ```bash
  curl -sSL https://install.python-poetry.org | python3 -
  ```
- Install dependencies:
  ```bash
  poetry install
  ```
- Create a `.env` file in the root with:
  ```env
  GEMINI_API_KEY=your_gemini_api_key
  MISTRAL_API_KEY=your_mistral_api_key
  CHROMEDRIVER_PATH=path_to_chromedriver
  GOOGLE_CUSTOM_SEARCH_API_KEY=your_google_api_key
  GOOGLE_CUSTOM_SEARCH_ENGINE_ID=your_search_engine_id
  ```

### 3. Frontend Setup
```bash
cd frontend
npm install
```

---

## Running the Application

### 1. Start the backend server:
```bash
poetry run flask run
```

### 2. Start the frontend development server:
```bash
cd frontend
npm run dev
```

### 3. Open [http://localhost:5173](http://localhost:5173) in your browser

---

## Usage

1. Enter a Blinkit product URL or upload a food label image
2. Click "Analyze" to process the product
3. View extracted information, nutritional analysis, and safety insights
4. Recent analyses are saved locally and can be revisited

---

## Testing

- Run backend unit tests:
  ```bash
  poetry run python tests.py
  ```

---

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## License

[MIT](LICENSE)
