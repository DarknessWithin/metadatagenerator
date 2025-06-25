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
Windows-Specific Paths
Update these paths in backend/ocr.py and extractor.py
  ```python
pytesseract.pytesseract.tesseract_cmd = r"C:\Program Files\Tesseract-OCR\tesseract.exe"
POPPLER_PATH = r"C:\poppler-24.08.0\Library\bin"
```
📋 Supported Formats
| Format  | Description              | Supported Features                 |
| ------- | ------------------------ | ---------------------------------- |
| PDF     | Portable Document Format | Text extraction + OCR (if scanned) |
| DOCX    | Microsoft Word Document  | Structured text extraction         |
| TXT     | Plain Text File          | Raw text handling                  |
| PNG/JPG | Image Formats            | OCR-based text extraction          |

🤖 AI Models (via OpenRouter)
Supports the following models:

meta-llama/llama-3-8b-instruct (default)

openai/gpt-3.5-turbo

anthropic/claude-3-haiku

google/gemini-pro

mistralai/mistral-7b-instruct

To switch models, change in metadata_gen.py:
```python
model = "openai/gpt-3.5-turbo"
```
📊 Metadata Fields Extracted
Title, Summary, Keywords

Language, Sentiment, Category

Named Entities (People, Orgs, Locations)

Sections Present, Important Dates

Intended Audience, Reading Time

Presence of Charts, Tables, Images

Bullet Point Summary, Tags

🧪 Testing
Example usage from backend modules:
```python
# Test extraction
from backend.extractor import extract_text
print(extract_text("sample.pdf"))

# Test OCR
from backend.ocr import extract_text_from_image
print(extract_text_from_image("sample.png"))

# Test metadata generation
from backend.metadata_gen import generate_metadata
print(generate_metadata("your text"))
```
🚀 Deployment
Local
```bash
streamlit run app/mainfile.py --server.port 8501
```
Streamlit Cloud
Push to GitHub

Go to https://share.streamlit.io

Link your repo and add OPENROUTER_API_KEY as a secret

Docker (optional)
```Dockerfile
FROM python:3.9-slim
RUN apt update && apt install -y tesseract-ocr poppler-utils
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
EXPOSE 8501
CMD ["streamlit", "run", "app/mainfile.py", "--server.port=8501", "--server.address=0.0.0.0"]
```
🐞 Troubleshooting
| Issue                 | Fix                                   |
| --------------------- | ------------------------------------- |
| Tesseract not found   | Install & set path in code            |
| `fitz` module missing | `pip install PyMuPDF`                 |
| API key errors (401)  | Check `.env` file                     |
| Streamlit not opening | Ensure you're not in bare script mode |

🤝 Contribution
Fork the repo

Create a new branch

Commit changes

Push and open a pull request ✅

📜 License
MIT License. See LICENSE.

👨‍💻 Author
Tanishq Sharma
🎓 BTech @ IIT Roorkee
📫 112005tani@gmail.com
🌐 github.com/DarknessWithin

Built with ❤️ using Python, Streamlit, OCR, and GenAI.

