# Handwriting Teacher

An adaptive handwriting practice app that uses OCR and sequence alignment to track your progress and generate personalized practice sentences.

## How It Works

1. **Get a sentence** - GPT-5.5 generates a practice sentence weighted toward letters you struggle with
2. **Write it** - Draw on the canvas or upload a photo of your handwriting
3. **Get feedback** - EasyOCR reads your writing, Biopython's sequence alignment scores accuracy
4. **Improve** - Character mastery grid updates, new sentences focus on weak letters

## Tech Stack

- **Backend**: Flask, EasyOCR, Biopython (pairwise sequence alignment), OpenAI GPT-4
- **Frontend**: Vanilla JS, p5.js for drawing canvas
- **ML**: EasyOCR for handwriting recognition

## Setup

```bash
# Clone and enter directory
git clone https://github.com/1441087236-360/Paideia.git
cd handwriting-teacher

# Create virtual environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env and add your OpenAI API key

# Run the app
python app.py
```

This app is configured to run EasyOCR on CPU only, so it does not require NVIDIA GPU support.

Visit `http://localhost:5123`

## Deployment

Docker:
```bash
docker build -t handwriting-teacher .
docker run -p 5123:5123 -e OPENAI_API_KEY=your_key handwriting-teacher
```

Or deploy directly to Railway/Render with the included Dockerfile.


