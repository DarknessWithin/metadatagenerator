# 📄 SmartMeta: Automated Metadata Generation System

An intelligent document analysis system that automatically generates comprehensive metadata from various document formats using AI/GenAI technology.

---

## 🌟 Features

- **Multi-format Support**: PDF, DOCX, TXT, and image files (PNG, JPG, JPEG)
- **OCR Integration**: Extract text from scanned documents and images
- **AI-Powered Analysis**: Generate rich metadata using advanced language models
- **Web Interface**: User-friendly Streamlit application
- **Comprehensive Metadata**: Extract 15+ metadata fields including:
  - Title, Summary, Keywords
  - Document Category, Language, Sentiment
  - Named Entities (People, Organizations, Locations)
  - Content Features, Technical Level
  - And much more!

---

## 🚀 Quick Start

### Prerequisites

- Python 3.8 or higher
- Tesseract OCR installed on your system
- OpenRouter API key (for AI analysis)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/metadatagenerator.git
   cd metadatagenerator/metadatageneration
Install dependencies

bash
pip install -r requirements.txt

Install Tesseract OCR

Windows:
Download from: https://github.com/UB-Mannheim/tesseract/wiki
Install and note the installation path

macOS:

bash
Copy
Edit
brew install tesseract

Ubuntu/Debian:

bash
Copy
Edit
sudo apt update
sudo apt install tesseract-ocr

Configure .env file

```bash
# Create .env file
echo "OPENROUTER_API_KEY=your_api_key_here" > .env
```

Run the App

```bash
streamlit run app/mainfile.py
```
The application will open at http://localhost:8501

📁 Project Structure
```graphql
metadatageneration/
├── app/
│   ├── mainfile.py             # Streamlit frontend
│   └── temp/                   # Temporary file storage
├── backend/
│   ├── extractor.py            # Document text extraction logic
│   ├── ocr.py                  # OCR logic for images/PDFs
│   └── metadata_gen.py         # AI metadata generation via OpenRouter
├── .env                        # Your API key here
├── requirements.txt            # Python dependencies
└── README.md
```
