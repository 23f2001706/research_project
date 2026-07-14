# Privacy Assessment RAG

A Flask-based privacy analysis app that extracts text from PDFs, detects personal data, estimates privacy risk, and generates a GDPR-style assessment using Gemini.

## Source Location

This project is provided as a zip file. After unzipping it, you will find the `phd` folder, and the application code is inside that folder.

## How to Unzip

If you downloaded the project as a zip file:

- On macOS: double-click the zip file, or right-click it and choose `Open`.
- On Windows: right-click the zip file and choose `Extract All...`.
- After extraction, open the `phd` folder to access the code.

## Features

- Upload PDF documents for analysis
- Detect personal data such as names, emails, phone numbers, addresses, IDs, and embedded images
- Generate a risk score and assessment recommendation
- Produce a detailed markdown privacy report

## macOS Compatibility

The app is cross-platform and runs on macOS without code changes. The Flask app now uses portable path handling and safe filename sanitization, so uploads work consistently on macOS, Windows, and Linux.

## Prerequisites

- Python 3.10 or newer
- A Gemini API key in the `GOOGLE_API_KEY` environment variable

## Setup on macOS

From the project folder:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r req.txt
export GOOGLE_API_KEY="your_gemini_api_key_here"
```

If you want the API key to persist for future Terminal sessions, add the `export` line to your shell profile such as `~/.zshrc`.

## Run the app

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000
```

## Project Structure

- `app.py` - Flask application and document analysis logic
- `templates/index.html` - Frontend page
- `uploads/` - Temporary upload directory created automatically at runtime
- `req.txt` - Python dependencies

## Notes

- Only PDF files are supported.
- Uploaded files are deleted after processing.
- The app expects readable text inside the PDF for analysis.

## Troubleshooting

- If the app reports that `GOOGLE_API_KEY` is missing, confirm the environment variable is set in the same Terminal session used to run Flask.
- If `pip install` fails on macOS, make sure `python3` points to a recent Python installation and that the virtual environment is activated.
